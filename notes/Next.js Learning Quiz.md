- # What is Next.js?
    - ## Building Blocks of a Web Application
        - There are a few things you need to consider when building modern applications. Such as:
            - **User Interface** - how users will consume and interact with your application.
            - **Routing** - how users navigate between different parts of your application.
            - **Data Fetching** - where your data lives and how to get it.
            - **Rendering** - when and where you render static or dynamic content.
            - **Integrations** - what third-party services you use (CMS, auth, payments, etc) and how you connect to them.
            - **Infrastructure** - where you deploy, store, and run your application code (Serverless, CDN, Edge, etc).
            - **Performance** - how to optimize your application for end-users.
            - **Scalability** - how your application adapts as your team, data, and traffic grow.
            - **Developer Experience** - your team’s experience building and maintaining your application.
- # From JavaScript to Reaact
    - ## Updating the UI with JavaScript and DOM Methods
        - You can use DOM methods and a programming language, such as JavaScript, to listen to user events and [manipulate the DOM](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Client-side_web_APIs/Manipulating_documents)
 by selecting, adding, updating, and deleting specific elements in the 
user interface. DOM manipulation allows you to not only target specific 
elements, but also change their style and content.
            - https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model/Introduction
            - Let's add an `h1` tag to the doucment:
                - ```javascript
<!-- index.html -->
<html>
  <body>
    <div></div>
  </body>
</html>

// give `div` a unique `id` to target later
<!-- index.html -->
<html>
  <body>
    <div id="app"></div>
  </body>
</html>

// To write javascript you just add a `script` tag
<!-- index.html -->
<html>
  <body>
    <div id="app"></div>
    <script type="text/javascript"></script>
  </body>
</html>
```
                - ## Now inside the `script` tag, use a DOM, `getElementById()`, to select the `div` element by its id
                    - ```javascript
<!-- index.html -->
<html>
  <body>
    <div id="app"></div>

    <script type="text/javascript">
      const app = document.getElementById('app');
    </script>
  </body>
</html>

// continue to use dom by creates a new <h1> element:
<!-- index.html -->
<html>
  <body>
    <div id="app"></div>

    <script type="text/javascript">
      const app = document.getElementById('app');
    </script>
  </body>
</html>


// we can update the head with:
<!-- index.html -->
<script type="text/javascript">
  const app = document.getElementById('app');
  const header = document.createElement('h1');
  const headerContent = document.createTextNode('Develop. Preview. Ship. 🚀');
  header.appendChild(headerContent);
  app.appendChild(header);
</script>
```
                -  Using a single page application aproach With this approach, developers spend a lot of time writing instructions to tell the computer **how** it should do things. But wouldn't it be nice to describe **what** you want to show and let the computer figure out **how** to update the DOM?
        - ## Imperative vs. Declarative Programming
            - Code above is imperative programming - wrote how the interface should be updated. When we need to build near the user interface though, we use declarative.
                - Instead of writing DOM methods, developers are able to declare what to show
            - In other words, **imperative programming** is like giving a chef step-by-step instructions on how to make a pizza. **Declarative programming** is like ordering a pizza without being concerned about the steps it takes to make the pizza. 🍕
    - # Getting Started with React
        - react is the core React Library
        - reac-dom provides DOM - specific methods tha tenable  you to use React with the DOM
            - ```javascript
<!-- index.html -->
<html>
  <body>
    <div id="app"></div>

    <script src="https://unpkg.com/react@17/umd/react.development.js"></script>
    <script src="https://unpkg.com/react-dom@17/umd/react-dom.development.js"></script>

    <script type="text/javascript">
      const app = document.getElementById('app');
    </script>
  </body>
</html>

```
        - Instead of directly manipulating the DOM with plain JavaScript, you can use the ReactDOM.render() method from react-dom to tell React to render our <h1> title inside our #app element.
            - ```javascript
<!-- index.html -->
<html>
  <body>
    <div id="app"></div>

    <script src="https://unpkg.com/react@17/umd/react.development.js"></script>
    <script src="https://unpkg.com/react-dom@17/umd/react-dom.development.js"></script>

    <script type="text/javascript">
      const app = document.getElementById('app');
      ReactDOM.render(<h1>Develop. Preview. Ship. 🚀</h1>, app);
    </script>
  </body>
</html>
```
- # Essential JavaScript for React
    - JavaScript topics covered here 
        - [Functions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions) and [Arrow Functions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions)
        - [Objects](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object)
        - [Arrays and array methods](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array)
        - [Destructuring](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Destructuring_assignment)
        - [Template literals](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Template_literals)
        - [Ternary Operators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Conditional_Operator)
        - [ES Modules and Import / Export Syntax](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Modules)
    - Core Concepts:
        - Components
        - Props
        - State
        - What is the primary purpose of props? To pass data to other components
    - ## Adding interactivity with State
        -  ```javascript
function HomePage() {
  const names = ['Ada Lovelace', 'Grace Hopper', 'Margaret Hamilton'];

  return (
    <div>
      <Header title="Develop. Preview. Ship. 🚀" />
      <ul>
        {names.map((name) => (
          <li key={name}>{name}</li>
        ))}
      </ul>

      <button>Like</button>
    </div>
  );

// Make button do something when clicked
function HomePage() {
  // ...
  return (
    <div>
      {/* ... */}
      <button onClick={}>Like</button>
    </div>
  );
}

// In React, event names are camelCased. The onClick event is one of many possible // events you can use to respond to user interaction. For example, you can use 
// onChange for input fields or onSubmit for forms.

// use handleClick() for handling events
function HomePage() {
  // ...

  function handleClick() {
    console.log("increment like count")
  }

  return (
    <div>
      {/* ... */}
      <button onClick={}>Like</button>
    </div>
     )
   }

// Handle events when driggered by onclick
function HomePage() {
  //    ...
  function handleClick() {
    console.log('increment like count');
  }

  return (
    <div>
      {/* ... */}
      <button onClick={handleClick}>Like</button>
    </div>
  );
}
```
        - ### State and Hooks
            - React has a set of functions called [hooks](https://reactjs.org/docs/hooks-intro.html). Hooks allow you to add additional logic such as **state**
 to your components. You can think of state as any information in your 
UI that changes over time, usually triggered by user interaction
            - Use state to store and increment th enumber of times a user has clicked the like button 
                - ```javascript
function HomePage() {
  React.useState();
}
`useState()` returns an array and you can acces and use array values inside your componnet with array destructuring
                - ```javascript
function HomePage() {
  React.useState();
}

// first item in array is the state value which you can name anything, but should be descriptive

function HomePage() {
  const [likes] = React.useState();

  // ...
}

// second item in array is a function to update the value and hsould be prefixed with the set followed by the name of the state variable

function HomePage() {
  const [likes, setLikes] = React.useState();

  // ...
}

// Lets also add the initial value of like state to zero

function HomePage() {
  const [likes, setLikes] = React.useState();

  // ...
}

// Make sure its working by adding the state variable inside component

function HomePage() {
  // ...
  const [likes, setLikes] = React.useState(0);

  return (
    // ...
    <button onClick={handleClick}>Like({likes})</button>
  );
}

// Call updater function setLIkes in your HomePage component to inside the handleClick() function 

function HomePage() {
  // ...
  const [likes, setLikes] = React.useState(0);

  function handleClick() {
    setLikes(likes + 1);
  }

  return (
    <div>
      {/* ... */}
      <button onClick={handleClick}>Likes ({likes})</button>
    </div>
  );
}

```
                - Unlike props which are passed to components as the first function 
parameter, the state is initiated and stored within a component. You can
 pass the state information to children components as props, but the 
logic for updating the state should be kept within the component where 
state was initially created.
                - This was only an introduction to state, and there’s more you can learn 
about managing state and data flow in your React applications. To learn 
more, we recommend you go through the [Adding Interactivity](https://beta.reactjs.org/learn/adding-interactivity) and [Managing State](https://beta.reactjs.org/learn/managing-state) sections in the React Documentation.
    - # Rendering
        - [🔗](https://nextjs.org/learn/foundations/about-nextjs)
        - [About Next.js](https://nextjs.org/learn/foundations/about-nextjs)
        - [🔗](https://nextjs.org/learn/foundations/from-javascript-to-react)
        - [From JavaScript to React](https://nextjs.org/learn/foundations/from-javascript-to-react)
        - [🔗](https://nextjs.org/learn/foundations/from-react-to-nextjs)
            - [From React to Next.js](https://nextjs.org/learn/foundations/from-react-to-nextjs)
            - [How Next.js Works](https://nextjs.org/learn/foundations/how-nextjs-works)
                - [From Development to Production](https://nextjs.org/learn/foundations/how-nextjs-works/development-and-production)
                - [Compiling](https://nextjs.org/learn/foundations/how-nextjs-works/compiling)
                - [Minifying](https://nextjs.org/learn/foundations/how-nextjs-works/minifying)
                - [Bundling](https://nextjs.org/learn/foundations/how-nextjs-works/bundling)
                - [Code Splitting](https://nextjs.org/learn/foundations/how-nextjs-works/code-splitting)
                - [Build Time vs. Runtime](https://nextjs.org/learn/foundations/how-nextjs-works/buildtime-and-runtime)
                - [Client and Server](https://nextjs.org/learn/foundations/how-nextjs-works/client-and-server)
                - [Rendering](https://nextjs.org/learn/foundations/how-nextjs-works/rendering)
                - [CDNs and the Edge](https://nextjs.org/learn/foundations/how-nextjs-works/cdns-and-edge)
                - [Next Steps](https://nextjs.org/learn/foundations/how-nextjs-works/next-steps)
    - ### Create your first app
        - [Create a Next.js App](https://nextjs.org/learn/basics/create-nextjs-app)
        - [Navigate Between Pages](https://nextjs.org/learn/basics/navigate-between-pages)
        - [Assets, Metadata, and CSS](https://nextjs.org/learn/basics/assets-metadata-css)
        - [Pre-rendering and Data Fetching](https://nextjs.org/learn/basics/data-fetching)
        - [Dynamic Routes](https://nextjs.org/learn/basics/dynamic-routes)
        - [API Routes](https://nextjs.org/learn/basics/api-routes)
        - [Deploying Your Next.js App](https://nextjs.org/learn/basics/deploying-nextjs-app)
    - ### Search Engine Optimization
        - [Introduction to SEO](https://nextjs.org/learn/seo/introduction-to-seo)
        - [Crawling and Indexing](https://nextjs.org/learn/seo/crawling-and-indexing)
        - [Rendering and Ranking](https://nextjs.org/learn/seo/rendering-and-ranking)
        - [Performance & Core Web Vitals](https://nextjs.org/learn/seo/web-performance)
        - [Improving your Core Web Vitals](https://nextjs.org/learn/seo/improve)
        - [Monitoring your Core Web Vitals](https://nextjs.org/learn/seo/monitor)
    - ### Excel
        - [TypeScript](https://nextjs.org/learn/excel/typescript)
    - ## How Next.js Works
    - ## What is Rendering?
        - There
 is an unavoidable unit of work to convert the code you write in React 
into the HTML representation of your UI. This process is called **rendering**.
        - Rendering
 can take place on the server or on the client. It can happen either 
ahead of time at build time, or on every request at runtime.
        - With Next.js, three types of rendering methods are available: **Server-Side Rendering**, **Static Site Generation**, and **Client-Side Rendering**.
    - ### Pre-Rendering
        - Server-Side Rendering and Static Site Generation are also referred to as **Pre-Rendering**
 because the fetching of external data and transformation of React 
components into HTML happens before the result is sent to the client.
    - ### Client-Side Rendering vs. Pre-Rendering
        - In
 a standard React application, the browser receives an empty HTML shell 
from the server along with the JavaScript instructions to construct the 
UI. This is called **client-side rendering** because the initial rendering work happens on the user's device.
        - ![](https://nextjs.org/static/images/learn/foundations/client-side-rendering.png)
        - **Note:**
 You can opt to use client-side rendering for specific components in 
your Next.js application by choosing to fetch data with React’s useEffect() or a data fetching hook such as [useSWR](https://swr.vercel.app/).
        - In contrast, Next.js **pre-renders**
 every page by default. Pre-rendering means the HTML is generated in 
advance, on a server, instead of having it all done by JavaScript on the
 user's device.
        - In practice, this means that for a fully 
client-side rendered app, the user will see a blank page while the 
rendering work is being done. Compared to a pre-rendered app, where the 
user will see the constructed HTML:
        - ![](https://nextjs.org/static/images/learn/foundations/pre-rendering.png)
        - Let’s discuss the two types of pre-rendering:
    - ### Server-Side Rendering
        - With server-side rendering, the HTML of the page is generated on a server for **each** request. The generated HTML, JSON data, and JavaScript instructions to make the page interactive are then sent to the client.
        - On
 the client, the HTML is used to show a fast non-interactive page, while
 React uses the JSON data and JavaScript instructions to make components
 interactive (for example, attaching event handlers to a button). This 
process is called **hydration**.
        - In Next.js, you can opt to server-side render pages by using [getServerSideProps](https://nextjs.org/docs/basic-features/data-fetching/get-server-side-props).
        - **Note:** React 18 and Next 12 introduce an alpha version of **React server components**.
 Server components are completely rendered on the server and do not 
require client-side JavaScript to render. In addition, server components
 allow developers to keep some logic on the server and only send the 
result of that logic to the client. This reduces the bundle size sent to
 the client and improves client-side rendering performance. [Learn more about React server components here](https://reactjs.org/blog/2020/12/21/data-fetching-with-react-server-components.html).
    - ### Static Site Generation
        - With
 Static Site Generation, the HTML is generated on the server, but unlike
 server-side rendering, there is no server at runtime. Instead, content 
is generated once, at build time, when the application is deployed, and 
the HTML is stored in a [CDN](https://nextjs.org/learn/foundations/how-nextjs-works/cdns-and-edge) and re-used for each request.
        - In Next.js, you can opt to statically generate pages by using [getStaticProps](https://nextjs.org/docs/basic-features/data-fetching/get-static-props).
        - **Note:** You can use [Incremental Static Regeneration](https://nextjs.org/docs/basic-features/data-fetching/incremental-static-regeneration) to create or update static pages __after__ you’ve built your site. This means you do not have to rebuild your entire site if your data changes.
        - The
 beauty of Next.js is that you can choose the most appropriate rendering
 method for your use case on a page-by-page basis, whether that's Static
 Site Generation, Server-side Rendering, or Client-Side Rendering. To 
learn more about which rendering method is right for your specific use 
case, see the [data fetching docs](https://nextjs.org/docs/basic-features/data-fetching/overview).
        - In the next section, we’ll discuss where your code can be stored or run after it’s deployed.
    - ## What is the Network?
        - It’s 
helpful to know where your application code is stored and run once it’s 
deployed to the network. You can think of the network as linked 
computers (or servers) capable of sharing resources. In the case of a 
Next.js application, your application code can be distributed to **origin servers**, **Content Delivery Networks (CDNs)**, and **the Edge**. Let’s see what each of these are:
    - ### Origin Servers
        - As
 we discussed earlier, the server refers to the main computer that 
stores and runs the original version of your application code.
        - We use the term **origin** to distinguish this server from the other places application code can be distributed to, such as **CDN servers** and **Edge servers**.
        - When
 an origin server receives a request, it does some computation before 
sending a response. The result of this computation work can be moved to a
 CDN (Content Delivery Network).
    - ### Content Delivery Network
        - CDNs
 store static content (such as HTML and image files) in multiple 
locations around the world and are placed between the client and the 
origin server. When a new request comes in, the closest CDN location to 
the user can respond with the cached result.
        - ![](https://nextjs.org/static/images/learn/foundations/cdn.png)
        - This
 reduces the load on the origin because the computation doesn’t have to 
happen on each request. It also makes it faster for the user because the
 response comes from a location geographically closer to them.
        - In 
Next.js, since pre-rendering can be done ahead of time, CDNs are well 
suited to store the static result of the work - making content delivery 
faster.
    - ### The Edge
        - The Edge is a generalized concept for the fringe (__or edge__)
 of the network, closest to the user. CDNs could be considered part of 
"the Edge" because they store static content at the fringe (edge) of the
 network.
        - Similar to CDNs, Edge servers are distributed to 
multiple locations around the world. But unlike CDNs, which store static
 content, some Edge servers can run small snippets of code.
        - This means both **caching** and **code execution** can be done at the Edge closer to the user.
        - By
 moving some work that was traditionally done client-side or server-side
 to the Edge, you can make your application more performant because it 
reduces the amount of code sent to the client, and part of the user's 
request does not have to go all the way back to the origin server - thus
 reducing latency. [See Edge examples with Next.js here](https://vercel.com/features/edge-functions#:~:text=or%20steps%20required.-,CODE%20EXAMPLES,-Unlock%20the%20potential).
        - In Next.js, you can run code at the Edge with [Middleware](https://nextjs.org/docs/middleware), and soon with [React Server Components](https://nextjs.org/docs/advanced-features/react-18/overview#react-server-components-alpha).
        - # Random Notes and More
            - ## Image Component
                - [https://image-component.nextjs.gallery](https://image-component.nextjs.gallery/)
                - [Next.js Image Component Example - StackBlitz](https://stackblitz.com/github/vercel/next.js/tree/canary/examples/image-component?file=README.md)
                - How to create:
                    - ```jsx
// ../components/Logo.jsx
import Image from 'next/image';
import myLogo from '../public/logo.png'

export default function Logo() {
  return (
    <div>
      <Image
          src={tarheeldevlogo}
          width={250}
          height={250}
          alt="my friggin logo"
      />
    </div>
  )
}```
                    - Post vull version of this in docs
            - # Custom App
                - **Note**: Next.js 13 introduces the app/ directory (beta). This new directory has support for layouts, nested routes, and uses Server Components by default. Inside app/, you can fetch data for your entire application inside layouts, including support for more granular nested layouts (with [colocated data fetching](https://beta.nextjs.org/docs/data-fetching/fundamentals)).
                - [Learn more about incrementally adopting app/](https://beta.nextjs.org/docs/upgrade-guide).
                - Next.js uses the App component to initialize pages. You can override it and control the page initialization and:
                    - Persist layouts between page changes
                    - Keeping state when navigating pages
                    - Inject additional data into pages
                    - [Add global CSS](https://nextjs.org/docs/basic-features/built-in-css-support#adding-a-global-stylesheet)
                - To override the default App, create the file ./pages/_app.js as shown below:
                - export default function MyApp({ Component, pageProps }) {
  return <Component {...pageProps} />}
                - The Component prop is the active page, so whenever you navigate between routes, Component will change to the new page. Therefore, any props you send to Component will be received by the page.
                - pageProps is an object with the initial props that were preloaded for your page by one of our [data fetching methods](https://nextjs.org/docs/basic-features/data-fetching/overview), otherwise it's an empty object.
                - The App.getInitialProps receives a single argument called context.ctx. It's an object with the same set of properties as the [context object](https://nextjs.org/docs/api-reference/data-fetching/get-initial-props#context-object) in getInitialProps.
            - ### [Caveats](https://nextjs.org/docs/advanced-features/custom-app#caveats)
            - ### 
            - ### 
                - If your app is running and you added a custom App, you'll need to restart the development server. Only required if pages/_app.js didn't exist before.
                - Adding a custom [getInitialProps](https://nextjs.org/docs/api-reference/data-fetching/get-initial-props) in your App will disable [Automatic Static Optimization](https://nextjs.org/docs/advanced-features/automatic-static-optimization) in pages without [Static Generation](https://nextjs.org/docs/basic-features/data-fetching/get-static-props).
                - When you add getInitialProps in your custom app, you must import App from "next/app", call App.getInitialProps(appContext) inside getInitialProps and merge the returned object into the return value.
                - App does not support Next.js [Data Fetching methods](https://nextjs.org/docs/basic-features/data-fetching/overview) like [getStaticProps](https://nextjs.org/docs/basic-features/data-fetching/get-static-props) or [getServerSideProps](https://nextjs.org/docs/basic-features/data-fetching/get-server-side-props). If you need global data fetching, consider [incrementally adopting the app/ directory](https://beta.nextjs.org/docs/upgrade-guide).
                - https://tailwindcss.com/docs/utility-first
            - Implement getStaticProps
            - ### Pre-rendering in Next.js
                - Next.js has two forms of pre-rendering: **Static Generation** and **Server-side Rendering**. The difference is in **when** it generates the HTML for a page.
                    - **Static Generation** is the pre-rendering method that generates the HTML at **build time**. The pre-rendered HTML is then __reused__ on each request.
                    - **Server-side Rendering** is the pre-rendering method that generates the HTML on **each request**.
                - Importantly, Next.js let's you **choose**
 which pre-rendering form to use for each page. You can create a 
"hybrid" Next.js app by using Static Generation for most pages and using
 Server-side Rendering for others.
        - # Dynamic Routes
            - ## Page Path Depends on External Data
                - In the previous lesson, we covered the case where the **page content** depends on external data. We used [getStaticProps](https://nextjs.org/docs/basic-features/data-fetching#getstaticprops-static-generation) to fetch required data to render the index page.
                - In this lesson, we’ll talk about the case where each **page path**
 depends on external data. Next.js allows you to statically generate 
pages with paths that depend on external data. This enables **dynamic URLs** in Next.js.
                    - ![](local-asset://Geaux-Notes/Q0-YGkSOlr.png)
                - ### How to Statically Generate Pages with Dynamic Routes
                    - In our case, we want to create [dynamic routes](https://nextjs.org/docs/routing/dynamic-routes) for blog posts:
                        - We want each post to have the path /posts/<id>, where <id> is the name of the markdown file under the top-level posts directory.
                        - Since we have ssg-ssr.md and pre-rendering.md, we’d like the paths to be /posts/ssg-ssr and /posts/pre-rendering.
                    - ### Overview of the Steps
                        - We can do this by taking the following steps. **You don’t have to make these changes yet** — we’ll do it all on the next page.
                        - First, we’ll create a page called **[id].js** under pages/posts. Pages that begin with [ and end with ] are [dynamic routes](https://nextjs.org/docs/routing/dynamic-routes) in Next.js.
                        - In pages/posts/[id].js, we’ll write code that will render a post page — just like other pages we’ve created.
                        - ```javascript
import Layout from '../../components/layout';

export default function Post() {
  return <Layout>...</Layout>;
}

// Now, here’s what’s new: We’ll export an async function called getStaticPaths from this page. In this function, we need to return a list of possible values for id.

import Layout from '../../components/layout';

export default function Post() {
  return <Layout>...</Layout>;
}

export async function getStaticPaths() {
  // Return a list of possible value for id
}

// Finally, we need to implement getStaticProps again - this time, to fetch necessary data for the blog post with a given id. getStaticProps is given params, which contains id (because the file name is [id].js).

import Layout from '../../components/layout';

export default function Post() {
  return <Layout>...</Layout>;
}

export async function getStaticPaths() {
  // Return a list of possible value for id
}

export async function getStaticProps({ params }) {
  // Fetch necessary data for the blog post using params.id
}
```
                        - ![](local-asset://Geaux-Notes/Jy1oA85YMH.png)
                    - ## Implement getStaticPaths
                        - First, let’s set up the files:
                            - Create a file called **[id].js** inside the pages/posts directory.
                            - Also, **remove first-post.js** inside the pages/posts directory — we’ll no longer use this.
                        - Then, open pages/posts/[id].js in your editor and paste the following code. We’ll fill in ... later:
                    - ```javascript
import Layout from '../../components/layout';

export default function Post() {
  return <Layout>...</Layout>;
}

// Then, open lib/posts.js and add the following getAllPostIds function at the bottom. It will return the list of file names (excluding .md) in the posts directory:

export function getAllPostIds() {
  const fileNames = fs.readdirSync(postsDirectory);

  // Returns an array that looks like this:
  // [
  //   {
  //     params: {
  //       id: 'ssg-ssr'
  //     }
  //   },
  //   {
  //     params: {
  //       id: 'pre-rendering'
  //     }
  //   }
  // ]
  return fileNames.map((fileName) => {
    return {
      params: {
        id: fileName.replace(/\.md$/, ''),
      },
    };
  });
}
```
                        - **mportant**: The returned list is __not__ just an array of strings — it **must** be an array of objects that look like the comment above. Each object must have the params key and contain an object with the id key (because we’re using [id] in the file name). Otherwise, [getStaticPaths](https://nextjs.org/docs/basic-features/data-fetching#getstaticpaths-static-generation) will fail.
                        - Finally, we'll import the getAllPostIds function and use it inside [getStaticPaths](https://nextjs.org/docs/basic-features/data-fetching#getstaticpaths-static-generation). Open pages/posts/[id].js and copy the following code above the exported Post component:

                        - ```javascript
import { getAllPostIds } from '../../lib/posts';

export async function getStaticPaths() {
  const paths = getAllPostIds();
  return {
    paths,
    fallback: false,
  };
}
```
                    - paths contains the array of known paths returned by getAllPostIds(), which include the params defined by pages/posts/[id].js. Learn more in the [paths key documentation](https://nextjs.org/docs/basic-features/data-fetching#the-paths-key-required)
                    - Ignore [fallback: false](https://nextjs.org/docs/basic-features/data-fetching#fallback-false) for now — we’ll explain that later.
                - ## Implement getStaticProps
                    - We need to fetch necessary data to render the post with the given id.
                    - To do so, open lib/posts.js again and add the following getPostData function at the bottom. It will return the post data based on id:
                    - ```javascript
export function getPostData(id) {
  const fullPath = path.join(postsDirectory, `${id}.md`);
  const fileContents = fs.readFileSync(fullPath, 'utf8');

  // Use gray-matter to parse the post metadata section
  const matterResult = matter(fileContents);

  // Combine the data with the id
  return {
    id,
    ...matterResult.data,
  };
}

// page/posts/[id].js
import { getAllPostIds, getPostData } from '../../lib/posts';

export async function getStaticProps({ params }) {
  const postData = getPostData(params.id);
  return {
    props: {
      postData,
    },
  };
}

// update post component with postData

export default function Post({ postData }) {
  return (
    <Layout>
      {postData.title}
      <br />
      {postData.id}
      <br />
      {postData.date}
    </Layout>
  );
}

```
                    - post page now uses the getPostData function in getStaticProps to get the post data adn return it as props
                    - ![statically generated pages with dynamic routes](local-asset://Geaux-Notes/D-H7SeVaxq.png)
                - ## Render Markdown
                - ```javascript
npm install remark remark-html

// open lib/posts.js and add + update the getPostData() function to use remark

import { remark } from 'remark';
import html from 'remark-html';

export async function getPostData(id) {
  const fullPath = path.join(postsDirectory, `${id}.md`);
  const fileContents = fs.readFileSync(fullPath, 'utf8');

  // Use gray-matter to parse the post metadata section
  const matterResult = matter(fileContents);

  // Use remark to convert markdown into HTML string
  const processedContent = await remark()
    .use(html)
    .process(matterResult.content);
  const contentHtml = processedContent.toString();

  // Combine the data with the id and contentHtml
  return {
    id,
    contentHtml,
    ...matterResult.data,
  };
}

// update getStaticProps in pages/posts/[id] to use await when calling getPostData

export async function getStaticProps({ params }) {
  // Add the "await" keyword like this:
  const postData = await getPostData(params.id);

  return {
    props: {
      postData,
    },
  };
}

// Update post component in pages/posts/[id] to render contentHtml using dangerouslySetInnerHTML

export default function Post({ postData }) {
  return (
    <Layout>
      {postData.title}
      <br />
      {postData.id}
      <br />
      {postData.date}
      <br />
      <div dangerouslySetInnerHTML={{ __html: postData.contentHtml }} />
    </Layout>
  );
}

```
            - ## Dynamic Routes Details
                - Here is some essential information you should know about [dynamic routes](https://nextjs.org/docs/routing/dynamic-routes).
            - ### Fetch External API or Query Database
                - Like [getStaticProps](https://nextjs.org/docs/basic-features/data-fetching#getstaticprops-static-generation), [getStaticPaths](https://nextjs.org/docs/basic-features/data-fetching#getstaticpaths-static-generation) can fetch data from any data source. In our example, getAllPostIds (which is used by [getStaticPaths](https://nextjs.org/docs/basic-features/data-fetching#getstaticpaths-static-generation)) may fetch from an external API endpoint:
                - ```javascript
export async function getAllPostIds() {
  // Instead of the file system,
  // fetch post data from an external API endpoint
  const res = await fetch('..');
  const posts = await res.json();
  return posts.map((post) => {
    return {
      params: {
        id: post.id,
      },
    };
  });
}
```
                    - ### Development vs. Production
                        - In **development** (npm run dev or yarn dev), [getStaticPaths](https://nextjs.org/docs/basic-features/data-fetching#getstaticpaths-static-generation) runs on __every request__.
                        - In **production**, [getStaticPaths](https://nextjs.org/docs/basic-features/data-fetching#getstaticpaths-static-generation) runs at __build time__.
                    - ### Fallback
                        - Recall that we returned fallback: false from [getStaticPaths](https://nextjs.org/docs/basic-features/data-fetching#getstaticpaths-static-generation). What does this mean?
                        - If [fallback is false](https://nextjs.org/docs/basic-features/data-fetching#fallback-false), then any paths not returned by [getStaticPaths](https://nextjs.org/docs/basic-features/data-fetching#getstaticpaths-static-generation) will result in a **404 page**.
                        - If [fallback is true](https://nextjs.org/docs/basic-features/data-fetching#fallback-true), then the behavior of [getStaticProps](https://nextjs.org/docs/basic-features/data-fetching#getstaticprops-static-generation) changes:
                            - The paths returned from [getStaticPaths](https://nextjs.org/docs/basic-features/data-fetching#getstaticpaths-static-generation) will be rendered to HTML at build time.
                            - The paths that have not been generated at build time will **not** result in a 404 page. Instead, Next.js will serve a “fallback” version of the page on the first request to such a path.
                            - In
 the background, Next.js will statically generate the requested path. 
Subsequent requests to the same path will serve the generated page, just
 like other pages pre-rendered at build time.
                            - If [fallback is blocking](https://nextjs.org/docs/basic-features/data-fetching#fallback-blocking), then new paths will be server-side rendered with getStaticProps, and cached for future requests so it only happens once per path.
                            - This is beyond the scope of our lessons, but you can learn more about fallback: true and fallback: 'blocking' in the [fallback documentation](https://nextjs.org/docs/api-reference/data-fetching/get-static-paths#fallback-false).
                            - ### Catch-all Routes
                                - Dynamic routes can be extended to catch all paths by adding three dots (...) inside the brackets. For example:
                                    - pages/posts/[...id].js matches /posts/a, but also /posts/a/b, /posts/a/b/c and so on.
                                - If you do this, in [getStaticPaths](https://nextjs.org/docs/basic-features/data-fetching#getstaticpaths-static-generation), you must return an array as the value of the id key like so:
                                - ### Router
                                    - If you want to access the Next.js router, you can do so by importing the [useRouter](https://nextjs.org/docs/api-reference/next/router#userouter) hook from [next/router](https://nextjs.org/docs/api-reference/next/router).
                                    - Create a custom 404 page:
                                    - ```javascript
// pages/404.js
export default function Custom404() {
  return <h1>404 - Page Not Found</h1>;
}
```
        - 
