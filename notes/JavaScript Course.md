- # New JavaScript Course - Advanced Stuff
- 
- # Advanced Concepts
    - ## Prototype Chain
        - Objects are everything that is not a primitive. Written like:
            - ```javascript
const animal = {
  dna: 123,
  legs: {
    front: 2, back: 2
  },
  sleep() {
    console.log('zzz')
  },
};

const p1 = Object.getPrototypeOf()



Here is where you'll see it - 

const animal = {
  dna: 'ATCG',
};

const dog = {
  face: '🐺',
}

Object.setPrototypeOf(dog, animal);

Object.getPrototypeOf(dog) === animal; // true

Object.getPrototypeOf(animal) === Object.prototype; // true

Object.getPrototypeOf(Object.prototype) === null; // true```
            - ![](local-asset://Geaux-Notes/NitAjAUle7.png)
            - The [prototype chain](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Inheritance_and_the_prototype_chain)
 is a mechanism that allows objects to inherit properties and methods 
from other objects. Every object can have exactly one prototype object. 
That prototype object can also have a prototype object, and so on, 
creating a chain of inheritied properties and methods. The end of this 
chain is called the null prototype.
            - In general, you don’t need to think about the prototype chain when 
doing everyday JavaScript development. However, it is important to 
understand how it works because it’s the basis for the class keyword and essential knowledge as you dive deeper into the language.
            - In the example below, we see how an dog can inherit properties from 
the animal object, which itself inherits properties from the root Object.prototype.
    - ## Destructuring
        - Work with objects easier
        - ```javascript
// Object destructuring
const person = {
  name: 'John',
  age: 32,
  city: 'New York',
  country: 'USA'
};

const { name, age } = person;

// Object destructuring with alias

const { name: firstName, age: years } = person;

// Array destructuring
const fruits = ['apple', 'banana', 'orange'];
const [first, second, third] = fruits;
```
    - ## Spread 
        - Combines objects
        - ... is the new syntax
        - ```javascript
The spread syntax ... is a relatively new operator that was introduced in ES2018. It provides a concise way to combine objects and arrays.

const obj = { 
    foo: 1, 
    bar: 2, 
    baz: 3 
};
const newObj = {
    foo: 4
    ...obj,
};
console.log(newObj); // { foo: 1, bar: 2, baz: 3 }

It’s also useful for combining arrays.

const arr1 = [1, 2, 3];
const arr2 = [4, 5, 6];
const arr3 = [...arr1, ...arr2];
```
    - ## Optional Chaining
        - Call object properties safely
        - obj?.hello; returns undefined without an error 
        - Optional chaining ? is a relatively new operator that was 
introduced in ES2020. It allows you to call object properties safely, 
without throwing an error. When calling properties without this 
operator, you many crash your applcation with the error Cannot read property 'foo' of undefined.
        - ```javascript
const person = { };

const dude = person.name;
console.log(foo); // Uncaught TypeError: Cannot read property 'bar' of undefined

const dude = person?.name; // undefined```
    - ## Nullish Coalescing
        - How nullish coalescing is related to truth and falsy
        - Nullish coalescing is a relativly new operator that was introduced in ES2020. It is similar to the logical OR operator ||, but it only returns the right-hand side if the left-hand side is null or undefined.
        - ```javascript
const foo = null ?? 'bar';
console.log(foo); // 'bar'

const foo = 0 ?? 'bar';
console.log(foo); // 0
```
    - ## Higher Order Functions
        - A higher order function is a function that takes a function as an 
argument, or returns a function. They are commonly used in functional 
programming, and are a powerful tool for abstracting away complexity.
        - ```javascript

// A function that takes a function as an argument
function add(x, y) {
  return x + y;
}
function subtract(x, y) {
  return x - y;
}
function math(x, y, operator) {
  return operator(x, y);
}

math(5, 2, add); // 7```
    - ## Closures
        - A closure is a function that has access to the parent scope, even after 
the parent function has closed. JS will automatically store the state of
 a closure in the heap memory, even after the parent function has 
returned. This behavior makes them useful for encapsulating private 
variables.
        - Heap memory can keep data in indefinitely and get rid of it later
        - more memory and computational power
        - data encapsulation
        - A function that closes over soem state or function to be used later
        - ```javascript
function encapsulatedState(x) {
  let state = 10;
  return function() {
    state += x;
    return state;
  }
}```
    - ## Array Tricks
        - const arr = [1,2,3,4,5,5,6]
        - make array with 100 zeros
            - const arr2 = Array(100).fill(0)
        - Count from 0 to 100
            - const arr2 = Array(100).fill(0).map((_, i) => i +1);
            - map executes a function for each value in array and then replaces it 
            - const arr3 = [...Array(100).keys()];
        - const unique = [...new Set(arr)];
        - ```javascript
for(const val of arr) {
  console.log(val);
}

for(const [i, val] of arr.entries()) {
  console.log(i, val);
}

arr.forEach();
arr.map();
arr.filter();
arr.find();
arr.findIndex();
arr.reduce();```
    - ## History of JavaScript
