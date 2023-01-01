- # Part 1 - Introduction
    - ## Your first component
        - ## Adding data
            - A component that just renders some static markup isn't very interesting. Let's add some data.
            - First, add a script tag to your component and declare a name variable:
            - ```javascript
<script>
	let name = 'Svelte';
</script>

<h1>Hello world!</h1>```
            - Then, we can refer to name in the markup:
            - ```javascript
<h1>Hello {name}!</h1>```
            - Inside the curly braces, we can put any JavaScript we want. Try changing name to name.toUpperCase() for a shoutier greeting.
            - ```javascript
<h1>Hello {name.toUpperCase()}!</h1>```
        - ### Dynamic Attributes
            - ## Shorthand attributes
                - It's not uncommon to have an attribute where the name and value are the same, like src={src}. Svelte gives us a convenient shorthand for these cases:
                - ```javascript
- <img {src} alt="A man dances." />
```
        - ## Styling
            - Just like in HTML, you can add a <style> tag to your component. Let's add some styles to the <p> element:
            - ```javascript
<p>This is a paragraph.</p>

<style>	p {
		color: purple;
		font-family: 'Comic Sans MS', cursive;
		font-size: 2em;
	}</style>```
            - Importantly, these rules are __scoped to the component__. You won't accidentally change the style of <p> elements elsewhere in your app, as we'll see in the next step
        - ## Nested Components
            - It would be impractical to put your entire app in a single component. Instead, we can import components from other files and include them in our markup.
            - Add a <script> tag that imports Nested.svelte...
            - ```javascript
- <script>
	import Nested from './Nested.svelte';
</script>
```
            - ...and include a <Nested /> component:
            - ```javascript
- <p>This is a paragraph.</p><Nested />
```
            - Notice that even though Nested.svelte has a <p> element, the styles from App.svelte don't leak in.
            - Component names are always capitalised, to distinguish them from HTML elements.
        - ## HTML Tags
            - Ordinarily, strings are inserted as plain text, meaning that characters like < and > have no special meaning.
            - But sometimes you need to render HTML directly into a component. For example, the words you're reading right now exist in a markdown file that gets included on this page as a blob of HTML.
            - In Svelte, you do this with the special {@html ...} tag:
            - ```javascript
<p>{@html string}</p>```
            - Svelte doesn't perform any sanitization of the expression inside {@html ...} before it gets inserted into the DOM. In other words, if you use this feature it's critical that you manually escape HTML that comes from sources you don't trust, otherwise you risk exposing your users to XSS attacks.
        - ## Assignments
            - At the heart of Svelte is a powerful system of __reactivity__ for keeping the DOM in sync with your application state — for example, in response to an event.
            - To demonstrate it, we first need to wire up an event handler (we'll learn more about these [later](https://learn.svelte.dev/tutorial/dom-events)):
            - ```javascript
- <button on:click={increment}>
```
            - Inside the increment function, all we need to do is change the value of count:
            - ```javascript
function increment() {
	count += 1;}```
            - Svelte 'instruments' this assignment with some code that tells it the DOM will need to be updated.
        - ## Declarations
            - Svelte automatically updates the DOM when your component's state changes. Often, some parts of a component's state need to be computed from __other__ parts (such as a fullname derived from a firstname and a lastname), and recomputed whenever they change.
            - For these, we have __reactive declarations__. They look like this:
            - ```javascript
let count = 0;$: doubled = count * 2;```
            - Don't worry if this looks a little alien. It's [valid](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/label) (if unconventional) JavaScript, which Svelte interprets to mean 're-run this code whenever any of the referenced values change'. Once you get used to it, there's no going back.
            - Let's use doubled in our markup:```javascript 
            - ```javascript
<button>...</button>

<p>{count} doubled is {doubled}</p>```
            - Of course, you could just write {count * 2} in the markup instead — you don't have to use reactive values. Reactive values become particularly valuable (no pun intended) when you need to reference them multiple times, or you have values that depend on __other__ reactive values.
        - ## Statements
            - We're not limited to declaring reactive __values__ — we can also run arbitrary __statements__ reactively. For example, we can log the value of count whenever it changes:
            - ```javascript
let count = 0;

$: console.log(`the count is ${count}`);```
            - You can easily group statements together with a block:
            - ```javascript
$: {
	console.log(`the count is ${count}`);
	alert(`I SAID THE COUNT IS ${count}`);}```
            - You can even put the $: in front of things like if blocks:
            - ```javascript
$: if (count >= 10) {
	alert('count is dangerously high!');
	count = 0;}```
        - ## Updating Arrays and Objects
            - 
                - [🔗](https://learn.svelte.dev/tutorial/declaring-props)
                - Because Svelte's reactivity is triggered by assignments, using array methods like push and splice won't automatically cause updates. For example, clicking the 'Add a number' button doesn't currently do anything.
                - One way to fix that is to add an assignment that would otherwise be redundant:
                - ```javascript
function addNumber() {
	numbers.push(numbers.length + 1);
	numbers = numbers;}```
                - But there's a more idiomatic solution:
                - ```javascript
function addNumber() {
	numbers = [...numbers, numbers.length + 1];}```
                - You can use similar patterns to replace pop, shift, unshift and splice.
                - Assignments to __properties__ of arrays and objects — e.g. obj.foo += 1 or array[i] = x — work the same way as assignments to the values themselves.
                - ```javascript
function addNumber() {
	numbers[numbers.length] = numbers.length + 1;}```
                - A simple rule of thumb: the name of the updated variable must appear on the left hand side of the assignment. For example this...
                - ```javascript
- const foo = obj.foo;
foo.bar = 'baz';
```
                - ...won't trigger reactivity on obj.foo.bar, unless you follow it up with obj = obj.
        - # Props
        - ## Declaring Props
            - So far, we've dealt exclusively with internal state — that is to say, the values are only accessible within a given component.
            - In any real application, you'll need to pass data from one component down to its children. To do that, we need to declare __properties__, generally shortened to 'props'. In Svelte, we do that with the export keyword. Edit the Nested.svelte component:
            - ```javascript
<script>
	export let answer;
</script>```
            - Just like $:, this may feel a little weird at first. That's not how export normally works in JavaScript modules! Just roll with it for now — it'll soon become second nature.
        - ## Default Values
            - We can easily specify default values for props in Nested.svelte:
            - ```javascript
<script>
	export let answer = 'a mystery';
</script>```
            - If we now add a second component __without__ an answer prop, it will fall back to the default:
            - ```javascript
- <Nested answer={42}/><Nested/>
```
        - ## Spread Props
            - If you have an object of properties, you can 'spread' them onto a component instead of specifying each one:
            - ```javascript
<PackageInfo {...pkg}/>```
            - Conversely, if you need to reference all the props that were passed into a component, including ones that weren't declared with export, you can do so by accessing $$props directly. It's not generally recommended, as it's difficult for Svelte to optimise, but it's useful in rare cases.
        - ## If blocks
            - HTML doesn't have a way of expressing __logic__, like conditionals and loops. Svelte does.
            - To conditionally render some markup, we wrap it in an if block:
            - ```javascript
- {#if user.loggedIn}
	<button on:click={toggle}>
		Log out
	</button>
  {/if}

{#if !user.loggedIn}
	<button on:click={toggle}>
		Log in
	</button>
 {/if}
```
            - Try it — update the component, and click on the buttons.
            - # Pick up here next time: [Logic / Else blocks • Svelte Tutorial](https://learn.svelte.dev/tutorial/else-blocks)
            - 
            - 
