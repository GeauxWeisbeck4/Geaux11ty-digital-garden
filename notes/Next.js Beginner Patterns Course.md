- # Next.js Beginner Patterns Course [[Egghead.io Courses]]
    - Next.js Patterns Course
    - ### 1. Create a new Next.js site
        - ```javascript
npx create-next-app next-project```
    - ### 2. Create and navigate between pages
        - In Next.js, every page is a React component that lives in the `pages/` directory. Every other React component that lives outside of the `pages/` directory is not being considered as a page. Next.js's built-in router generates our routes automatically based on our project structure. For example:
            - The index `/ page` would be the `pages/index.tsx` file,
            - The `/about` page would be `pages/about.tsx` file,
            - The `docs/getting-started` page would be `pages/docs/getting-started.tsx` file, and so on.
        - To navigate between pages, Next.js provides us a `Link` component that's exported from the `next/link` package. To create a link to our About page, we can do the following:
        - ```javascript
/
import Link from 'next/link'

const Home = () => {
  return (
    <Link href="/about">About</Link>
  )}

export default Home;```
        - ## [🔗](https://github.com/nikolovlazar/egghead-beginners-guide-nextjs/tree/main/exercises/exercise-02--create-and-navigate-between-pages#-exercise)🚀 Exercise
            - {{[[TODO]]}}   Create a new "About" page and add a link in the Home page to it.
        - ## [🔗](https://github.com/nikolovlazar/egghead-beginners-guide-nextjs/tree/main/exercises/exercise-02--create-and-navigate-between-pages#-exercise-feedback-form)🍩 Exercise Feedback form
            - {{[[TODO]]}}  Writing down what you learn is key to your retention. Also, I want to make sure each exercise is effective at helping you learn the material. Please quickly fill out [this form](https://docs.google.com/forms/d/e/1FAIpQLSeKPJV5UInaNFlZawN7vZdNyPngyinrkp7eoQO0vzwGzh2EtQ/viewform?usp=pp_url&entry.651170566=Exercise+02+-+Create+and+navigate+between+pages) so you can elaborate on what you learned and give me feedback so I can improve it for future learners.
    - ### Exercise 3: Create Dynamic Routes
        - ## [🔗](https://github.com/nikolovlazar/egghead-beginners-guide-nextjs/tree/main/exercises/exercise-03--create-dynamic-routes#background)Background
            - We learned in the previous exercise that Next.js treats our files in the pages/ directory as pages, and it automatically generates routes for us. But, what if we wanted to create a page with a dynamic route? You can add brackets around the page's name ([pid].tsx) to create a dynamic route.
            - Let's say we have a page in pages/post/[pid].tsx:
            - ```javascript
import { useRouter } from 'next/router'

const Post = () => {
  const router = useRouter()
  const { pid } = router.query

  return <p>Post: {pid}</p>}

export default Post```
            - Any route like /post/1, /post/hello-world, etc. will be matched by the [pid].tsx page. The dynamic parameter pid will be available to us as a query parameter through Next.js's router.
            - If we want to have a multi-segment dynamic route, we can wrap the folders' names with brackets too, for example pages/post/[pid]/[comment].tsx. The router's query will merge the two dynamic segments, so if we visited /post/hello-world/love-it, the query object will be:
            - { pid: "hello-world", comment: "love-it" }
        - ## [🔗](https://github.com/nikolovlazar/egghead-beginners-guide-nextjs/tree/main/exercises/exercise-03--create-dynamic-routes#-exercise)🚀 Exercise
            - Create a genre page that will display the genre's name dynamically. Examples:
                - /rock
                - /country
                - /pop
        - ## [🔗](https://github.com/nikolovlazar/egghead-beginners-guide-nextjs/tree/main/exercises/exercise-03--create-dynamic-routes#%EF%B8%8F-challenge)⭐️ Challenge
            - Make a new dynamic page that will display the artist's name and their music genre. Examples:
                - /rock/axl-rose should display "axl-rose is a rock music artist!"
                - /country/chris-stapleton should display "chris-stapleton is a country music artist!"
                - /pop/bruno-mars should display "bruno-mars is a pop music artist!"
        - ## [🔗](https://github.com/nikolovlazar/egghead-beginners-guide-nextjs/tree/main/exercises/exercise-03--create-dynamic-routes#-checkpoint)🚩 Checkpoint
            - This exercise marks the first checkpoint at which we'll go into breakout rooms to do the following exercises:
                - [Exercise 01: Create a new Next.js TypeScript project](https://github.com/nikolovlazar/egghead-beginners-guide-nextjs/blob/main/exercises/exercise-01--create-a-new-next-js-type-script-project)
                - [Exercise 02: Create and navigate between pages](https://github.com/nikolovlazar/egghead-beginners-guide-nextjs/blob/main/exercises/exercise-02--create-and-navigate-between-pages)
                - [Exercise 03: Create Dynamic Routes](https://github.com/nikolovlazar/egghead-beginners-guide-nextjs/blob/main/exercises/exercise-03--create-dynamic-routes)
            - Start with the first exercise, and work your way through the last one. If you're stuck, do not hesitate to ask. As soon as you're done you can fill out either the [Post-Breakout Feedback Form](https://docs.google.com/forms/d/e/1FAIpQLSda0BFV57OWbSkshNC_jZ809HEBOuW_MzLEz1Bq4PVKtI7R9w/viewform?usp=pp_url&entry.651170566=Group+1:+New+Project,+Pages+%26+Navigation,+Dynamic+Routes), or the feedback forms for each individual exercise. I would appreciate your feedback a lot.
        - ## [🔗](https://github.com/nikolovlazar/egghead-beginners-guide-nextjs/tree/main/exercises/exercise-03--create-dynamic-routes#-exercise-feedback-form)🍩 Exercise Feedback form
            - Writing down what you learn is key to your retention. Also, I want to make sure each exercise is effective at helping you learn the material. Please quickly fill out [this form](https://docs.google.com/forms/d/e/1FAIpQLSeKPJV5UInaNFlZawN7vZdNyPngyinrkp7eoQO0vzwGzh2EtQ/viewform?usp=pp_url&entry.651170566=Exercise+03+-+Create+Dynamic+Routes) so you can elaborate on what you learned and give me feedback so I can improve it for future learners.
    - ### 3. Serve Static Assets
        - ## Background
            - Aside from `pages`, there is another "specialized" folder called `public`. Next.js serves everything in the `public` folder statically, starting from the base URL `/`. If we had an image `public/lazar.png` we can view it on `http://localhost:3000/lazar.png`, or we can reference it in our code:
            - ```javascript
const Avatar = () => {
  return <img src="/lazar.png" alt="Lazar Nikolov" />}

export default Avatar```
            - The `public` folder is also useful for the `robots.txt`, `favicon.ico`, Google Site Verification, and any other static files, including HTML files.
        - ## [🔗](https://github.com/nikolovlazar/egghead-beginners-guide-nextjs/tree/main/exercises/exercise-04--serve-static-assets#-exercise)🚀 Exercise
            - Add the `"lazar.png"` image (which is at the root of this project) to the Home page.
        - ## [🔗](https://github.com/nikolovlazar/egghead-beginners-guide-nextjs/tree/main/exercises/exercise-04--serve-static-assets#-exercise-feedback-form)🍩 Exercise Feedback form
            - Writing down what you learn is key to your retention. Also, I want to make sure each exercise is effective at helping you learn the material. Please quickly fill out [this form](https://docs.google.com/forms/d/e/1FAIpQLSeKPJV5UInaNFlZawN7vZdNyPngyinrkp7eoQO0vzwGzh2EtQ/viewform?usp=pp_url&entry.651170566=Exercise+04+-+Serve+static+assets) so you can elaborate on what you learned and give me feedback so I can improve it for future learners.
    - ### 5. Use `next/image` for Image Optimization
        - ## Background
            - We can always use the good old `<img />` HTML element to display images, but Next.js also provides an `Image `component that has some built-in performance optimizations:
                - Improved Performance: Always serves correctly sized image for each device, using modern image formats.
                - Visual Stability: Prevents Cumulative Layout Shift automatically.
                - Faster Page Loads: Images are only loaded when they enter the` viewport, with optional blur-up placeholders.
                - Asset Flexibility: On-demand image resizing, even for images stored on remote servers.
            - Here's how we can use the Image component:
            - ```javascript
// pages/index.tsx

import Image from 'next/image'

import photo from '../public/photo.png'

const Home = () => {
  return (
    <Image src={photo} alt="Picture of Lazar" />
  )}

export default Home```
            - When we use static imports like in the example above, Next.js's Image component automatically sets the width, height, placeholder and blurDataURL props because it can analyze it on build-time.
            - If we want to load a remote image, it's up to us to provide the width and height props. Because we always want our apps to be secure, Next.js also requires us to provide the domains from which we'll load remote images from:
            - ```javascript
// next.config.js

module.exports = {
  images: {
    domains: ['example.com', 'cdnurl.com', ...]
  }}```
            - To improve our website performance, we can add a priority prop to the image that would be the [Largest Contentful Paint (LCP)](https://web.dev/lcp/#what-elements-are-considered) element for each page. This will tell Next.js to prioritize the loading of that image, and that will make our LCP score much better. The LCP element is usually the largest image visible in the viewport of the page. When you run next dev, you'll see a console warning if the LCP element is an [![]()](https://github.com/nikolovlazar/egghead-beginners-guide-nextjs/tree/main/exercises/exercise-05--use-next-image-for-image-optimization) without the priority property. Once you've identified which element is the LCP, you can add the priority prop like this:
            - ```javascript
// pages/index.tsx

import Image from 'next/image'

import photo from '../public/photo.png'

const Home = () => {
  return (
    <Image
      src={photo}
      alt="Picture of Lazar"
      priority
    />
  )}

export default Home```
        - ## [🔗](https://github.com/nikolovlazar/egghead-beginners-guide-nextjs/tree/main/exercises/exercise-05--use-next-image-for-image-optimization#-exercise)🚀 Exercise
            - Add the "lazar.png" image (which is at the root of this project) to the Home page using the Image component.
        - ## [🔗](https://github.com/nikolovlazar/egghead-beginners-guide-nextjs/tree/main/exercises/exercise-05--use-next-image-for-image-optimization#%EF%B8%8F-challenge)⭐️ Challenge
            - Display a remote image from Twitter using the Image component.
        - ## [🔗](https://github.com/nikolovlazar/egghead-beginners-guide-nextjs/tree/main/exercises/exercise-05--use-next-image-for-image-optimization#-exercise-feedback-form)🍩 Exercise Feedback form
            - Writing down what you learn is key to your retention. Also, I want to make sure each exercise is effective at helping you learn the material. Please quickly fill out [this form](https://docs.google.com/forms/d/e/1FAIpQLSeKPJV5UInaNFlZawN7vZdNyPngyinrkp7eoQO0vzwGzh2EtQ/viewform?usp=pp_url&entry.651170566=Exercise+05+-+Use+next/image+for+Image+Optimization) so you can elaborate on what you learned and give me feedback so I can improve it for future learners.
    - ### 6. Provide page-specific metadata
        - ## Background
            - Something that every website has in common is a metadata, which consists of a title, description, style links, scripts and so on. In Next.js, we can use the Head component to provide metadata for each page specifically:
            - ```javascript
// pages/index.tsx

import Head from 'next/head'

const Home = () => {
  return (
    <>
      <Head>
        <title>Homepage</title>
        <meta name="viewport" content="initial-scale=1.0, width=device-width" />
      </Head>
      <div>
        <h1>Homepage</h1>      </div>
    </>
  )}

export default Home```
            - The content in the Head component can be composed of local hardcoded data, and also obtained from an API or CMS. In order to avoid duplicates, we can use the key prop, which will make sure that the tag is going to be rendered only once:
            - ```javascript
// pages/index.tsx

import Head from 'next/head'

const Home = () => {
  return (
    <>
      <Head>
        <title>Homepage</title>
        <meta name="viewport" content="initial-scale=1.0, width=device-width" />
        <meta name="og:title" content="My awesome course" key="title" />
      </Head>
      <Head>
        <meta name="og:title" content="My Next.js course" key="title" /> // <--- this tag will be rendered
      </Head>
      <div>
        <h1>Homepage</h1>      </div>
    </>
  )}

export default Home```
            - In this case, only the second ("My Next.js course") tag is going to be rendered.
            - The contents of the Head component get cleared upon unmounting the component, so make sure that each page completely defines what it needs without making assumptions about what other pages added.
            - The title, meta, or any other elements need to be direct children of the Head component, or wrapped into maximum one level of <React.Fragment>, otherwise the tags won't be correctly picked up on client-side navigations.
        - ## [🔗](https://github.com/nikolovlazar/egghead-beginners-guide-nextjs/tree/main/exercises/exercise-06--provide-page-specific-metadata#-exercise)🚀 Exercise
            - Add a title and description using the Head component in our homepage.
        - ## [🔗](https://github.com/nikolovlazar/egghead-beginners-guide-nextjs/tree/main/exercises/exercise-06--provide-page-specific-metadata#-checkpoint)🚩 Checkpoint
            - This exercise marks the second checkpoint at which we'll go into breakout rooms to do the following exercises:
                - [Exercise 04: Serve static assets](https://github.com/nikolovlazar/egghead-beginners-guide-nextjs/blob/main/exercises/exercise-04--serve-static-assets)
                - [Exercise 05: Use next/image for image optimization](https://github.com/nikolovlazar/egghead-beginners-guide-nextjs/blob/main/exercises/exercise-05--use-next-image-for-image-optimization)
                - [Exercise 06: Provide page-specific metadata](https://github.com/nikolovlazar/egghead-beginners-guide-nextjs/blob/main/exercises/exercise-06--provide-page-specific-metadata)
            - Start with the first exercise, and work your way through the last one. If you're stuck, do not hesitate to ask. As soon as you're done you can fill out either the [Post-Breakout Feedback Form](https://docs.google.com/forms/d/e/1FAIpQLSda0BFV57OWbSkshNC_jZ809HEBOuW_MzLEz1Bq4PVKtI7R9w/viewform?usp=pp_url&entry.651170566=Group+2:+Static+Assets,+Next+Image,+Page+Metadata), or the feedback forms for each individual exercise. I would appreciate your feedback a lot.
        - ## [🔗](https://github.com/nikolovlazar/egghead-beginners-guide-nextjs/tree/main/exercises/exercise-06--provide-page-specific-metadata#-exercise-feedback-form)🍩 Exercise Feedback form
            - Writing down what you learn is key to your retention. Also, I want to make sure each exercise is effective at helping you learn the material. Please quickly fill out [this form](https://docs.google.com/forms/d/e/1FAIpQLSeKPJV5UInaNFlZawN7vZdNyPngyinrkp7eoQO0vzwGzh2EtQ/viewform?usp=pp_url&entry.651170566=Exercise+06+-+Provide+page-specific+metadata) so you can elaborate on what you learned and give me feedback so I can improve it for future learners.
    - ### 7. Override the App Component
        - ## Background
            - Every page in Next.js is initialized by an App component. By default it's hidden (internal in Next.js), but we can override it to control the page initialization if we want to:
                - Persist layout between page changes
                - Keep state when navigating pages
                - Custom error handling
                - Inject additional data into pages
                - Add global CSS
            - To override the default App, we need to create the pages/_app.tsx file:
            - ```javascript
import type { AppProps } from 'next/app'

const App = ({ Component, pageProps }: AppProps) => {
  return <Component {...pageProps} />}

export default App```
            - Mind the underscore before "app": _app.tsx
            - The Component component is our currently displayed page. The pageProps object contains the initial props that were preloaded by the data fetching methods. If no data fetching methods were used in that particular page, the pageProps object will be empty.
        - ## [🔗](https://github.com/nikolovlazar/egghead-beginners-guide-nextjs/tree/main/exercises/exercise-07--override-the-app-component#-exercise)🚀 Exercise
            - Override the App component and pass a title prop to the Component.
        - ## [🔗](https://github.com/nikolovlazar/egghead-beginners-guide-nextjs/tree/main/exercises/exercise-07--override-the-app-component#-exercise-feedback-form)🍩 Exercise Feedback form
            - Writing down what you learn is key to your retention. Also, I want to make sure each exercise is effective at helping you learn the material. Please quickly fill out [this form](https://docs.google.com/forms/d/e/1FAIpQLSeKPJV5UInaNFlZawN7vZdNyPngyinrkp7eoQO0vzwGzh2EtQ/viewform?usp=pp_url&entry.651170566=Exercise+07+-+Override+the+App+component) so you can elaborate on what you learned and give me feedback so I can improve it for future learners.
    - ### 8. Override the Document
        - ## Background
            - Just like _app.tsx, we can also override the _document.tsx file. We can use a custom Document to augment our application's <html> and <body> tags, like setting the lang property of the <html> tag, adding third-party scripts, linking custom fonts, add analytics scripts etc...
            - To override the default Document, we need to create a file pages/_document.tsx:
            - ```javascript
import { Html, Head, Main, NextScript } from 'next/document'

export default function Document() {
  return (
    <Html>
      <Head />
      <body>
        <Main />
        <NextScript />
      </body>
    </Html>
  )}```
            - 💡 The <Html>, <Head />, <Main /> and <NextScript /> are required for the page to be properly rendered!
            - Note that the Document is only rendered in the server, so event handlers like onClick will not work!
        - ## [🔗](https://github.com/nikolovlazar/egghead-beginners-guide-nextjs/tree/main/exercises/exercise-08--override-the-document#-exercise)🚀 Exercise
            - Override the Document.
        - ## [🔗](https://github.com/nikolovlazar/egghead-beginners-guide-nextjs/tree/main/exercises/exercise-08--override-the-document#-exercise-feedback-form)🍩 Exercise Feedback form
            - Writing down what you learn is key to your retention. Also, I want to make sure each exercise is effective at helping you learn the material. Please quickly fill out [this form](https://docs.google.com/forms/d/e/1FAIpQLSeKPJV5UInaNFlZawN7vZdNyPngyinrkp7eoQO0vzwGzh2EtQ/viewform?usp=pp_url&entry.651170566=Exercise+08+-+Override+the+Document) so you can elaborate on what you learned and give me feedback so I can improve it for future learners.
    - ### 9. Create Custom Style
        - ## Background
            - In Next.js, there are several ways to achieve custom styles:
                - [Adding a Global Stylesheet](https://github.com/nikolovlazar/egghead-beginners-guide-nextjs/tree/main/exercises/exercise-09--create-custom-style#adding-a-global-stylesheet)
                - [Component-level CSS](https://github.com/nikolovlazar/egghead-beginners-guide-nextjs/tree/main/exercises/exercise-09--create-custom-style#component-level-css)
                - [CSS-in-JS](https://github.com/nikolovlazar/egghead-beginners-guide-nextjs/tree/main/exercises/exercise-09--create-custom-style#css-in-js)
        - ### [🔗](https://github.com/nikolovlazar/egghead-beginners-guide-nextjs/tree/main/exercises/exercise-09--create-custom-style#adding-a-global-stylesheet)Adding a Global Stylesheet
            - To add a global stylesheet, we need to import it in the pages/_app.tsx file. If we haven't overriden the App yet, we should do that first.
            - Let's say we have the following file styles.css at the root of the project:
            - ```javascript
body {
  font-family: 'SF Pro Text', 'SF Pro Icons', 'Helvetica Neue', 'Helvetica',
    'Arial', sans-serif;
  padding: 20px 20px 60px;
  max-width: 680px;
  margin: 0 auto;
}```
            - To use it, we need to simply import it in our _app.tsx file:
            - ```javascript
import type { AppProps } from 'next/app'

import '../styles.css'

const App = ({ Component, pageProps }: AppProps) => {
  return <Component {...pageProps} />}

export default App```
            - Since we're importing them in our _app.tsx file, these styles will be applied to every page.
            - Since Next.js 9.5.4, we can also import styles from node_modules, for example: import 'bootstrap/dist/css/bootstrap.css' will import Bootstrap and it will work just fine.
        - ### [🔗](https://github.com/nikolovlazar/egghead-beginners-guide-nextjs/tree/main/exercises/exercise-09--create-custom-style#component-level-css)Component-level CSS
            - Another way of achieving custom styles is using [CSS Modules](https://github.com/css-modules/css-modules), which Next.js has support for.
            - Let's say we want to make a reusable Button component. First, we're going to create the CSS module src/components/button/button.module.css:
            - ```javascript
.error {
  color: white;
  background-color: red;
}```
            - Then, we're going to create the component itself src/components/button/button.tsx:
            - ```javascript
import styles from './button.module.css'

const Button = () => {
  return (
    <button
      type="button"
      className={styles.error}
    >
      Delete
    </button>
  )}

export default Button```
        - ### [🔗](https://github.com/nikolovlazar/egghead-beginners-guide-nextjs/tree/main/exercises/exercise-09--create-custom-style#css-in-js)CSS-in-JS
            - Next.js also comes with a built-in CSS-in-JS support. The simplest way to do CSS-in-JS is inline styles:
            - const Button = () => {
  return (
    <button
      type="button"
      style={{ color: 'white', backgroundColor: 'red' }}
    >
      Delete
    </button>
  )}

export default Button
        - ## [🔗](https://github.com/nikolovlazar/egghead-beginners-guide-nextjs/tree/main/exercises/exercise-09--create-custom-style#-exercise)🚀 Exercise
            - Try all three methods:
                - Create a global stylesheet that defines the container layout
                - Create a flexbox <div> using CSS-in-JS
                - Create a "Log in" Button component that uses CSS Modules and put it in the flexbox
        - ## [🔗](https://github.com/nikolovlazar/egghead-beginners-guide-nextjs/tree/main/exercises/exercise-09--create-custom-style#-exercise-feedback-form)🍩 Exercise Feedback form
            - Writing down what you learn is key to your retention. Also, I want to make sure each exercise is effective at helping you learn the material. Please quickly fill out [this form](https://docs.google.com/forms/d/e/1FAIpQLSeKPJV5UInaNFlZawN7vZdNyPngyinrkp7eoQO0vzwGzh2EtQ/viewform?usp=pp_url&entry.651170566=Exercise+09+-+Create+custom+style) so you can elaborate on what you learned and give me feedback so I can improve it for future learners.
    - ### 10. Create Custom Layouts
        - ## Background
            - React's composable nature allows us to create reusable components. Layouts are exactly that! In [Exercise 07](https://github.com/nikolovlazar/egghead-beginners-guide-nextjs/blob/main/exercises/exercise-07--override-the-app-component) we learned what's the App component and how to override it. So, if we had a custom layout and wanted to use it, the App component is where we should start.
            - In Next.js there are two ways that you can define a custom layout:
                - [Single Shared Layout](https://github.com/nikolovlazar/egghead-beginners-guide-nextjs/tree/main/exercises/exercise-10--create-custom-layouts#single-shared-layout)
                - [Per-Page Layouts](https://github.com/nikolovlazar/egghead-beginners-guide-nextjs/tree/main/exercises/exercise-10--create-custom-layouts#per-page-layouts)
        - ## [🔗](https://github.com/nikolovlazar/egghead-beginners-guide-nextjs/tree/main/exercises/exercise-10--create-custom-layouts#single-shared-layout)Single Shared Layout
            - A Single Shared Layout in Next.js is a custom layout that's used by every page in our app. Let's say our app is simple, and every page has a navbar and a footer. We can define our layout like so:
            - ```javascript
// src/components/layout/index.tsx

import type { ReactNode } from 'react'

import Navbar from './navbar'import Footer from './footer'

type Props = {
  children?: ReactNode}

const Layout = ({ children }: Props) => {
  return (
    <>
      <Navbar />
      <main>{children}</main>
      <Footer/>
    </>
  )}

export default Layout```
            - In order to use this custom layout, we can wrap the Component component in our _app.tsx file:
            - ```javascript
// pages/_app.tsx

import type { AppProps } from 'next/app'

import Layout from 'src/components/layout'

const App = ({ Component, pageProps }: AppProps) => {
  return (
    <Layout>
      <Component {...pageProps} />
    </Layout>
  )}

export default App```
            - Since the Layout component is reused when changing pages, its component state will be preserved.
        - ## [🔗](https://github.com/nikolovlazar/egghead-beginners-guide-nextjs/tree/main/exercises/exercise-10--create-custom-layouts#per-page-layouts)Per-Page Layouts
            - If we want to have multiple layouts (ex. authentication, dashboard, settings etc...), we can define a getLayout property to our pages that will receive the page in props, and wrap it in the layout that we want. Since we're returning a function, we can have complex nested layouts if we wanted to.
            - Here's an example of a page:
            - ```javascript
// pages/index.tsx

import type { ReactElement } from 'react'

import Layout from 'src/components/layout'import NestedLayout from 'src/components/nested-layout'

const Page = () => {
  return (
    // Our page's content...
  )}

Page.getLayout = (page: ReactElement) => {
  return (
    <Layout>
      <NestedLayout>{page}</NestedLayout>
    </Layout>
  )}

export default Page```
            - In order to use this, we need to make some changes in our _app.tsx:
            - ```javascript
// pages/_app.tsx

import type { ReactElement, ReactNode } from 'react'import type { NextPage } from 'next'import type { AppProps } from 'next/app'

type NextPageWithLayout = NextPage & {
  // define the getLayout method for every page
  getLayout?: (page: ReactElement) => ReactNode}

type AppPropsWithLayout = AppProps & {
  // override the default Component definition
  Component: NextPageWithLayout}

const App = ({ Component, pageProps }: AppPropsWithLayout) => {
  // use the getLayout defined in each page
  // if it doesn't exist, provide a fallback
  const getLayout = Component.getLayout ?? ((page) => page)

  return getLayout(<Component {...pageProps} />)}

export default App```
            - Have in mind that the Custom Layouts are not considered as Pages, so the only way to fetch data is on the client-side.
            - That's how we can setup a simple mechanism for custom per-page layouts.
        - ## [🔗](https://github.com/nikolovlazar/egghead-beginners-guide-nextjs/tree/main/exercises/exercise-10--create-custom-layouts#-exercise)🚀 Exercise
            - Create a single shared layout that adds a navigation bar and a footer to each of our pages.
        - ## [🔗](https://github.com/nikolovlazar/egghead-beginners-guide-nextjs/tree/main/exercises/exercise-10--create-custom-layouts#%EF%B8%8F-challenge)⭐️ Challenge
            - Implement the mechanism that allows you to specify which layout is going to be rendered in each page separately.
        - ## [🔗](https://github.com/nikolovlazar/egghead-beginners-guide-nextjs/tree/main/exercises/exercise-10--create-custom-layouts#-exercise-feedback-form)🍩 Exercise Feedback form
            - Writing down what you learn is key to your retention. Also, I want to make sure each exercise is effective at helping you learn the material. Please quickly fill out [this form](https://docs.google.com/forms/d/e/1FAIpQLSeKPJV5UInaNFlZawN7vZdNyPngyinrkp7eoQO0vzwGzh2EtQ/viewform?usp=pp_url&entry.651170566=Exercise+10+-+Create+custom+Layouts) so you can elaborate on what you learned and give me feedback so I can improve it for future learners.
    - ### 11. Use UI Frameworks Like Chakra UI
        - ## Background
            - In [Exercise 09](https://github.com/nikolovlazar/egghead-beginners-guide-nextjs/blob/main/exercises/exercise-09--create-custom-style) we learned how to create and use CSS files. But, most of the developers use UI frameworks to make their life easier. Using a UI framework like Chakra UI in combination with Next.js will supercharge your feature development and make the styling of your app even easier.
            - Frameworks like [Chakra UI](https://chakra-ui.com/) utilize the React Context API to configure your web app's theme and ensure consistent styles. As we mentioned in the [Exercise 07](https://github.com/nikolovlazar/egghead-beginners-guide-nextjs/blob/main/exercises/exercise-07--override-the-app-component), we can override the App component to persist layout between page changes and inject additional data into pages. That's where we can add the ChakraProvider. Chakra UI also comes with a ColorModeScript specifically built for Next.js that we need to put in our custom Document, which we learned how to override in [Exercise 08](https://github.com/nikolovlazar/egghead-beginners-guide-nextjs/blob/main/exercises/exercise-08--override-the-document).
        - ## [🔗](https://github.com/nikolovlazar/egghead-beginners-guide-nextjs/tree/main/exercises/exercise-11--use-ui-frameworks-like-chakra-ui#-exercise)🚀 Exercise
            - Configure Chakra UI in your project.
        - ## [🔗](https://github.com/nikolovlazar/egghead-beginners-guide-nextjs/tree/main/exercises/exercise-11--use-ui-frameworks-like-chakra-ui#-checkpoint)🚩 Checkpoint
            - This exercise marks the third checkpoint at which we'll go into breakout rooms to do the following exercises:
                - [Exercise 07: Override the App Component](https://github.com/nikolovlazar/egghead-beginners-guide-nextjs/blob/main/exercises/exercise-07--override-the-app-component)
                - [Exercise 08: Override the Document](https://github.com/nikolovlazar/egghead-beginners-guide-nextjs/blob/main/exercises/exercise-08--override-the-document)
                - [Exercise 09: Create custom style](https://github.com/nikolovlazar/egghead-beginners-guide-nextjs/blob/main/exercises/exercise-09--create-custom-style)
                - [Exercise 10: Create custom layout](https://github.com/nikolovlazar/egghead-beginners-guide-nextjs/blob/main/exercises/exercise-10--create-custom-layouts)
                - [Exercise 11: Use UI frameworks like Chakra UI](https://github.com/nikolovlazar/egghead-beginners-guide-nextjs/blob/main/exercises/exercise-11--use-ui-frameworks-like-chakra-ui)
            - Start with the first exercise, and work your way through the last one. If you're stuck, do not hesitate to ask. As soon as you're done you can fill out either the [Post-Breakout Feedback Form](https://docs.google.com/forms/d/e/1FAIpQLSda0BFV57OWbSkshNC_jZ809HEBOuW_MzLEz1Bq4PVKtI7R9w/viewform?usp=pp_url&entry.651170566=Group+3:+App+Component,+Document+Component,+Custom+Style,+Custom+Layouts,+Chakra+UI), or the feedback forms for each individual exercise. I would appreciate your feedback a lot.
        - ## [🔗](https://github.com/nikolovlazar/egghead-beginners-guide-nextjs/tree/main/exercises/exercise-11--use-ui-frameworks-like-chakra-ui#-exercise-feedback-form)🍩 Exercise Feedback form
            - Writing down what you learn is key to your retention. Also, I want to make sure each exercise is effective at helping you learn the material. Please quickly fill out [this form](https://docs.google.com/forms/d/e/1FAIpQLSeKPJV5UInaNFlZawN7vZdNyPngyinrkp7eoQO0vzwGzh2EtQ/viewform?usp=pp_url&entry.651170566=Exercise+11+-+Use+UI+frameworks+like+Chakra+UI) so you can elaborate on what you learned and give me feedback so I can improve it for future learners.
    - ### 12. Use the Static Generation Method
        - ## Background
            - In Next.js, there are two forms of pre-rendering, **Static Generation** and **Server-side Rendering**. We can apply these methods for each page individually.
            - The Static Generation method fetches the page's data on **build-time**, and renders static HTML files. To apply the Static Generation method, we need to export a getStaticProps method from our page:
            - ```javascript
// pages/index.tsx

import type { GetStaticProps } from 'next'

import type { Lesson } from 'types/lesson'import { fetchLessons } from 'utils/lessons'

type Props = {
  lessons: Lesson[]}

const Home = ({ lessons }: Props) => {
  return (
    <ul>
      {lessons.map((lesson) => (...))}
    </ul>
  )}

export const getStaticProps: GetStaticProps<Props> = async (context) => {
  const lessons = await fetchLessons()

  const props: Props = {
    lessons
  }

  return {
    props
  }}

export default Home```
            - For our Home page, Next.js will execute the fetchLessons method asynchroniously, and pass the lessons array as a prop in our Home component. If there is no data for the given query, we need to return notFound: true instead of the props. If the lessons data changes and we want to update the page, we can either rebuild our website, or use the [Incremental Static Regeneration](https://github.com/nikolovlazar/egghead-beginners-guide-nextjs/tree/main/exercises/exercise-12--use-the-static-generation-method#incremental-static-regeneration) method.
            - In our getStaticProps method we can also obtain the context, which holds data like:
                - params: the route parameters for pages that use dynamic routes
                - preview: a boolean which is true if the page is in the [Preview Mode](https://nextjs.org/docs/advanced-features/preview-mode), otherwise undefined
                - previewData: an object that holds the preview data set by setPreviewData
                - locale: the active locale, if you've enabled [Internationalized Routing](https://nextjs.org/docs/advanced-features/i18n-routing)
                - locales: an array that contains all of the locales
                - defaultLocale: the default configured locale
        - ## [🔗](https://github.com/nikolovlazar/egghead-beginners-guide-nextjs/tree/main/exercises/exercise-12--use-the-static-generation-method#incremental-static-regeneration)Incremental Static Regeneration
            - The ISR method is an extension of the Static Generation method. We can enable ISR if we provide a revalidate property in our getStaticProps result:
            - ```javascript
export const getStaticProps: GetStaticProps<Props> = async (context) => {
  return {
    props: {...},
    revalidate: 60 * 60,
  }}```
            - The revalidate property will tell Next.js to "revalidate" our data maximum one time in the given timeframe (in our case is 1 hour, 60 seconds times 60).
        - ## [🔗](https://github.com/nikolovlazar/egghead-beginners-guide-nextjs/tree/main/exercises/exercise-12--use-the-static-generation-method#building-pages-with-dynamic-routes)Building pages with dynamic routes
            - Since the Static Generation happens on build-time, if we have a page that uses [Dynamic Routes](https://github.com/nikolovlazar/egghead-beginners-guide-nextjs/blob/main/exercises/exercise-03--create-dynamic-routes) we also need to export the getStaticPaths method. The getStaticPaths method returns a list of paths that have to be rendered to HTML at build-time.
            - ```javascript
import type { GetStaticProps, GetStaticPaths } from 'next'

...

export const getStaticPaths: GetStaticPaths = async () => {
  const lessons = await fetchLessons()

  return {
    paths: lessons.map({ slug } => ({ params: { slug } })),
    fallback: false
  }}```
            - The paths key determines which paths will be pre-rendered. If for example we had 3 lessons, Next.js will pre-render the following URLs:
                - /lessons/getting-started
                - /lessons/create-pages
                - /lessons/create-dynamic-routes
            - For each lesson, Next.js will execute the getStaticProps method. That pre-renders every page and generates static HTML files for them.
            - The fallback key is a boolean key that we must include in our getStaticPaths result. If it's set to false, then any paths that are not returned by the getStaticPaths method will result in a 404 page. If it's set to true, Next.js will render a "fallback" page while it statically generates the HTML and JSON (this includes running the getStaticProps method). When it's done, the page will receive the brand new data in its props and it will render its contents. At the end of the process, Next.js will add the new path to the list of pre-rendered pages.
            - If our page supports a fallback, we can use Next.js's router to check if Next.js wants us to render a fallback page:
            - ```javascript
import { useRouter } from 'next/router'

const Home = () => {
  const router = useRouter()

  if (router.isFallback) {
    return <div>Loading...</div>
  }

  ...
}```
            - If we don't want to display a Loading page, we can set the fallback property in getStaticPaths to 'blocking'. This will make the browser wait for Next.js to pre-render the HTML.
        - ## [🔗](https://github.com/nikolovlazar/egghead-beginners-guide-nextjs/tree/main/exercises/exercise-12--use-the-static-generation-method#-exercise)🚀 Exercise
            - Display a page with a list of genres (like in [Exercise 03](https://github.com/nikolovlazar/egghead-beginners-guide-nextjs/blob/main/exercises/exercise-03--create-dynamic-routes)) and provide the genres using getStaticProps.
        - ## [🔗](https://github.com/nikolovlazar/egghead-beginners-guide-nextjs/tree/main/exercises/exercise-12--use-the-static-generation-method#%EF%B8%8F-challenge)⭐️ Challenge
            - Make a dynamic "genre" page that will display a sentence explaining the genre.
        - ## [🔗](https://github.com/nikolovlazar/egghead-beginners-guide-nextjs/tree/main/exercises/exercise-12--use-the-static-generation-method#-exercise-feedback-form)🍩 Exercise Feedback form
            - Writing down what you learn is key to your retention. Also, I want to make sure each exercise is effective at helping you learn the material. Please quickly fill out [this form](https://docs.google.com/forms/d/e/1FAIpQLSeKPJV5UInaNFlZawN7vZdNyPngyinrkp7eoQO0vzwGzh2EtQ/viewform?usp=pp_url&entry.651170566=Exercise+12+-+Use+the+Static+Generation+method) so you can elaborate on what you learned and give me feedback so I can improve it for future learners.
    - ### 13. Use the Server-Side Rendering Method
        - ## Background
            - In the [previous exercise](https://github.com/nikolovlazar/egghead-beginners-guide-nextjs/blob/main/exercises/exercise-12--use-the-static-generation-method) we learned about Next.js's Static Generation method. In this exercise we're going to explore the Server-side Rendering method.
            - Just like the Static Generation, SSR (Server-side Rendering) is another way of data fetching supported in Next.js. The difference between SSR and SSG is that in SSR the data gets fetched for every request, while in SSG the data used to be fetched on build-time. This method is good for pages that have dynamic data, data that changes often.
            - When the user requests a SSR page, the server fetches the data (queries the DB, uses third-party APIs etc...), generates the HTML, and then gets it back to the browser. Compared to the SSG, the requests in SSR are slower, but that's the price to pay to have dynamic data.
            - To apply the SSR method in Next.js, we need to export a getServerSideProps method from our page:
            - ```javascript
// pages/index.tsx

import type { GetServerSideProps } from 'next'

...

export const getServerSideProps: GetServerSideProps<Props> = async (context) => {
  return {
    props: {
      ...
    }
  }}```
            - The context object is similar to SSG's context, but it also includes:
                - req: the HTTP IncomingMessage object, plus additional parsing helpers
                - res: the HTTP response object
                - query: an object representing the query string
            - Unlike SSG, with SSR we don't need to provide a method similar to the getStaticPaths, because every request generates an HTML file, so no HTML files need to be generated at build-time.
        - ## [🔗](https://github.com/nikolovlazar/egghead-beginners-guide-nextjs/tree/main/exercises/exercise-13--use-the-server-side-rendering-method#-exercise)🚀 Exercise
            - Refactor the previous exercise's solution to use SSR instead.
        - ## [🔗](https://github.com/nikolovlazar/egghead-beginners-guide-nextjs/tree/main/exercises/exercise-13--use-the-server-side-rendering-method#%EF%B8%8F-challenge)⭐️ Challenge
            - To really exploit the power of SSR, utilize the query from the context to filter the music genres.
        - ## [🔗](https://github.com/nikolovlazar/egghead-beginners-guide-nextjs/tree/main/exercises/exercise-13--use-the-server-side-rendering-method#-exercise-feedback-form)🍩 Exercise Feedback form
            - Writing down what you learn is key to your retention. Also, I want to make sure each exercise is effective at helping you learn the material. Please quickly fill out [this form](https://docs.google.com/forms/d/e/1FAIpQLSeKPJV5UInaNFlZawN7vZdNyPngyinrkp7eoQO0vzwGzh2EtQ/viewform?usp=pp_url&entry.651170566=Exercise+13+-+Use+the+Server-side+Rendering+method) so you can elaborate on what you learned and give me feedback so I can improve it for future learners.
    - ### 14. Create and Use API Routes
        - ## Background
            - Since Next.js is built on top of Node.js, it also allows us to define our own API routes. The API routes are functions that are part of the server, but instead of rendering HTML, they're returning JSON data.
            - Any file inside pages/api is mapped to /api/* and it will be treated as an API endpoint instead of a page. These functions are server-side, and will not bundled with your client-side code. That means we can safely open DB connections, and use secret environment variables.
            - For new projects, we can build our entire API with API routes, but if we already have an existing API we don't need to forward our API calls through an API route. We could also use API calls if we want to mask our API or an external service (instead of https://mycompany.com/secret-api-url, we can send requests to /api).
            - To create an API handler, we need to create a file in pages/api and export a default async function:
            - ```javascript
// pages/api/user.ts

import type { NextApiHandler } from 'next'

const handler: NextApiHandler = async (req, res) => {
  return res.status(200).json({ name: 'John Doe' })}

export default handler```
            - The function receives 2 arguments:
                - req: An instance of http.IncomingMessage, plus some pre-built middlewares
                - res: An instance of http.ServerResponse, plus some helper functions
            - The req contains the method, body and query properties that we can use to handle the request. Here's how we can handle different HTTP methods in our API:
            - ```javascript
const handler: NextApiHandler = async (req, res) => {
  if (req.method === 'GET') {
    // process the GET request
  }
  if (req.method === 'POST') {
    // process the POST request
  }}```
            - To get the data sent from the client, we can use the body property:
            - ```javascript
const handler: NextApiHandler = async (req, res) => {
  const { body } = req;
  // body: { name: 'Lazar Nikolov', profession: 'Software Engineer' }

  if (req.method === 'POST') {
    // save data (body) in database
  }}```
            - We can also use a dynamic route when building API handlers.
        - ## [🔗](https://github.com/nikolovlazar/egghead-beginners-guide-nextjs/tree/main/exercises/exercise-14--create-and-use-api-routes#-exercise)🚀 Exercise
            - Create a User Directory API that returns data for a given user. Use a dynamic route that contains the userId, and return the user with that ID. The user data is exported from data/users.ts.
        - ## [🔗](https://github.com/nikolovlazar/egghead-beginners-guide-nextjs/tree/main/exercises/exercise-14--create-and-use-api-routes#-checkpoint)🚩 Checkpoint
            - This exercise marks the fourth checkpoint at which we'll go into breakout rooms to do the following exercises:
                - [Exercise 12: Use the Static Generation method](https://github.com/nikolovlazar/egghead-beginners-guide-nextjs/blob/main/exercises/exercise-12--use-the-static-generation-method)
                - [Exercise 13: Use the Server-side Rendering method](https://github.com/nikolovlazar/egghead-beginners-guide-nextjs/blob/main/exercises/exercise-13--use-the-server-side-rendering-method)
                - [Exercise 14: Create and use API Routes](https://github.com/nikolovlazar/egghead-beginners-guide-nextjs/blob/main/exercises/exercise-14--create-and-use-api-routes)
            - Start with the first exercise, and work your way through the last one. If you're stuck, do not hesitate to ask. As soon as you're done you can fill out either the [Post-Breakout Feedback Form](https://docs.google.com/forms/d/e/1FAIpQLSda0BFV57OWbSkshNC_jZ809HEBOuW_MzLEz1Bq4PVKtI7R9w/viewform?usp=pp_url&entry.651170566=Group+4:+Static+Generation,+Server-Side+Rendering,+API+Routes), or the feedback forms for each individual exercise. I would appreciate your feedback a lot.
        - ## [🔗](https://github.com/nikolovlazar/egghead-beginners-guide-nextjs/tree/main/exercises/exercise-14--create-and-use-api-routes#-exercise-feedback-form)🍩 Exercise Feedback form
            - Writing down what you learn is key to your retention. Also, I want to make sure each exercise is effective at helping you learn the material. Please quickly fill out [this form](https://docs.google.com/forms/d/e/1FAIpQLSeKPJV5UInaNFlZawN7vZdNyPngyinrkp7eoQO0vzwGzh2EtQ/viewform?usp=pp_url&entry.651170566=Exercise+14+-+Create+and+use+API+Routes) so you can elaborate on what you learned and give me feedback so I can improve it for future learners.
    - ### 15. Deploy Your Next.js Site to Vercel
        - ## Background
            - Next.js can be deployed anywhere, but the easiest way is to use the [Vercel](https://vercel.com/) platform, which is created by the people who also created Next.js.
            - Vercel is optimized for Next.js. Out of the box, it applies the following optimizations to your app:
                - Every page can either use Static Generation or Server-Side Rendering.
                - Pages that use Static Generation and assets (JS, CSS, images, fonts, etc) will automatically be served from [Vercel's Edge Network](https://vercel.com/docs/edge-network/overview), which is blazingly fast.
                - Pages that use Server-Side Rendering and API routes will automatically become isolated Serverless Functions. This allows page rendering and API requests to scale infinitely.
            - To deploy your app on Vercel, first you need to push it to a Git provider, like GitHub. Then, follow these steps:
                - Sign up to Vercel (it's free, no credit card needed)
                - Then you'll see the "Import Project" page. Pick the Git provider you host your app's source at.
                - After you've authenticated with your Git provider, you will see a list of your repos. Find the app you want to deploy and click on the "Import" button.
                - Vercel will automatically figure out that it's a Next.js project, and it will apply the defaults for you. If you use any Environment Variables, make sure you add them in the "Environments Variables" section.
                - When you're ready, hit the "Deploy" button and you app will be built and deployed in a few minutes.
            - Congratulations! You app is live now! 🎉
        - ## [🔗](https://github.com/nikolovlazar/egghead-beginners-guide-nextjs/tree/main/exercises/exercise-15--deploy-your-next-js-app-on-vercel#-exercise)🚀 Exercise
            - Deploy the following project on Vercel: [nikolovlazar/deploy-nextjs-on-vercel](https://github.com/nikolovlazar/deploy-nextjs-on-vercel).
        - ## [🔗](https://github.com/nikolovlazar/egghead-beginners-guide-nextjs/tree/main/exercises/exercise-15--deploy-your-next-js-app-on-vercel#-checkpoint)🚩 Checkpoint
            - This exercise marks the fifth checkpoint at which we'll go into breakout rooms to do this exercise only. If you're stuck, do not hesitate to ask. As soon as you're done you can fill out either the [Post-Breakout Feedback Form](https://docs.google.com/forms/d/e/1FAIpQLSda0BFV57OWbSkshNC_jZ809HEBOuW_MzLEz1Bq4PVKtI7R9w/viewform?usp=pp_url&entry.651170566=Group+5:+Vercel+Deployment), or the feedback form for this exercise. I would appreciate your feedback a lot.
        - ## [🔗](https://github.com/nikolovlazar/egghead-beginners-guide-nextjs/tree/main/exercises/exercise-15--deploy-your-next-js-app-on-vercel#-exercise-feedback-form)🍩 Exercise Feedback form
            - Writing down what you learn is key to your retention. Also, I want to make sure each exercise is effective at helping you learn the material. Please quickly fill out [this form](https://docs.google.com/forms/d/e/1FAIpQLSeKPJV5UInaNFlZawN7vZdNyPngyinrkp7eoQO0vzwGzh2EtQ/viewform?usp=pp_url&entry.651170566=Exercise+15+-+Deploy+your+Next.js+app+on+Vercel) so you can elaborate on what you learned and give me feedback so I can improve it for future learners.
