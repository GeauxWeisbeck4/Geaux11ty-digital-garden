- # Resources and Links
    - https://developers.google.com/search/docs/fundamentals/seo-starter-guide
    - https://developer.mozilla.org/en-US/docs/Web/HTTP/Status
    - 
- # Why is SEO important?
    - SEO is the key to increased conversion and 
confidence in your brand. Higher search ranking placement equates to 
more organic visitors. **Search engine organic traffic** – visitors who come to your site through clicking a result in a search engine – is key to many businesses for three reasons:
        - **Qualitative** – Increased chance that visitors turn into customers.
        - **Trustable** – Higher confidence in your brand or mission.
        - **Low-Cost**
 – Aside from the time and effort spent, having good SEO practices that 
result in higher search engine ranking is free. There is no direct cost 
to appear in top organic search results positions.
    - Plan out as a Next.js developer and content writer
        - ### Three Pillars of Optimization
            - The process of optimizing a website can be divided into three main pillars:
                - **Technical** – Optimize your website for crawling and web performance.
                - **Creation** – Create a content strategy to target specific keywords.
                - **Popularity** – Boost your site's presence online so search engines know you are a trusted source. This is done through the use of [backlinks](https://moz.com/learn/seo/backlinks) – third-party sites that link back to your site.
            - The SEO discipline is broad and has [many facets](https://learningseo.io/), but as a Next.js developer, the first step is to understand how you can make your web app SEO-ready with some best practices.
- # Search Systems
    - Search Systems are what you typically refer 
to as Search Engines (Google, Bing, DuckDuckGo, etc.). They are 
massively complex systems that tackle some of the biggest challenges in 
technology history.
    - Search Systems have four main responsibilities:
        - **Crawling** – the process of going through the Web and parsing the content in all websites. This is a massive task as there are [over 350 million domains](https://www.businesswire.com/news/home/20200528005832/en/Internet-Grows-to-366.8-Million-Domain-Name-Registrations-at-the-End-of-the-First-Quarter-of-2020) available.
        - **Indexing** – finding places to store all of the data gathered during the crawling stage so it can be accessed.
        - **Rendering**
 – executing any resources on the page such as JavaScript that might 
enhance the features and enrich content on the site. This process 
doesn't happen for all pages that are crawled and sometimes it happens 
before the content is actually indexed. Rendering might happen after 
indexing if there are no available resources to perform the task at the 
time.
        - **Ranking** – querying
 data to craft relevant results pages based on user input. This is where
 the different ranking criteria are applied in Search engines to give 
users the best answer to fulfill their intent.
    - In the next section, we will learn more specifically how Googlebot works. 
Googlebot is Google's internet crawler, the part of the search system 
that gathers all the information needed to create the massive database 
of content to serve search results.
- # Web Crawlers
    - ![](local-asset://Geaux-Notes/GRp9WXWgAb.png)
    - A general overview of the process can be the following:
        - **Find URLs**:  Google sources URLs from many places, including [Google Search Console](https://search.google.com/search-console), links between websites, or [XML sitemaps](https://developers.google.com/search/docs/advanced/sitemaps/overview).
        - **Add to Crawl Queue**:
 These URLs are added to the Crawl Queue for the Googlebot to process. 
URLs in the Crawl Queue usually last seconds there, but it can be up to a
 few days depending on the case, especially if the pages need to be 
rendered, indexed, or – if the URL is already indexed – refreshed. The 
pages will then enter the [Render Queue](https://nextjs.org/learn/seo/rendering-and-ranking).
        - **HTTP Request**: The crawler makes an HTTP request to get the headers and acts according to the returned status code:
            - 200 - it crawls and parses the HTML.
            - 30X - it follows the redirects.
            - 40X - it will note the error and not load the HTML
            - 50X - it may come back later to check if the status code has changed.
        - **Render Queue**:
 The different services and components of the search system process the 
HTML and parse the content. If the page has some JavaScript client-side 
based content, the URLs might be added to a Render Queue. Render Queue 
is more costly for Google as it needs to use more resources to render 
JavaScript and therefore URLs rendered are a smaller percentage over the
 total pages out there on the internet. Some other search engines might 
not have the same rendering capacity as Google, and this is where 
Next.js can help with your rendering strategy.
        - **Ready to be indexed**: If all criteria are met, the pages may be eligible to be indexed and shown in search results.
    - In the next few sections, we will take a deep dive into each of the main components of a search system's processes: [crawling and indexing](https://nextjs.org/learn/seo/crawling-and-indexing), and [rendering and ranking](https://nextjs.org/learn/seo/rendering-and-ranking).
- # Http Status Codes
    - ### 200
        - The [HTTP 200 OK](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status/200) success status response code indicates that the request has succeeded.
        - In order for a page to be indexed on Google it must return status code 200. This is what you typically want to look for in your pages in order for them to receive organic traffic.
        - This is the default code that will be set when Next.js renders a page successfully.
    - ### 301/308
        - The [HTTP 301 Moved Permanently](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status/301) redirect status response code indicates that the resource requested has been definitively moved to the destination URL.
        - This is a permanent redirect. In general, this is the most widely used redirect type.
        - Redirects can be used for a variety of reasons, but the main one is to indicate 
that a URL has been moved from point A to point B.
        - Redirects are needed to ensure that, if a content is moved from one place to the 
other, you do not lose current and potential clients and that the bots 
can continue to index your site.
        - Main difference between two codes is that a '301' allwos for changing request from 'POST' to 'GET' a '308' does not
        - Here's how to trigger a '308' redirect in Next.js
            - ```javascript
//  pages/about.js
export async function getStaticProps(context) {
  return {
    redirect: {
      destination: '/',
      permanent: true, // triggers 308
    },
  };
}
```
        - You can also use the 'permanent: true' for redirects set in 'next.config.js'
            - ```javascript
//next.config.js

module.exports = {
  async redirects() {
    return [
      {
        source: '/about',
        destination: '/',
        permanent: true, // triggers 308
      },
    ];
  },
};
```
    - ### 302
        - The[HTTP 302 Found](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status/302) redirect status response code indicates that the resource requested has been temporarily moved to the destination URL.
        - In most cases, 302 redirects should be 301
 redirects. This may not be the case if you are redirecting users 
temporarily to a certain page (e.g. a promotion page) or if you are 
redirecting users based on location.
    - ### 404
        - The [HTTP 404 Not Found](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status/404) client error response code indicates that the server can't find the requested resource.
        - As noted above, pages that are moved should be redirected with a HTTP 301 status code to the new location. When this doesn't happen, URLs may return a 404 status code.
        - 404
 Status Codes are not necessarily bad by default, as it's the desired 
outcome if a user happens to visit a URL that doesn't exist, but they 
shouldn't be a frequent error within your pages as it could lead to 
lackluster search rankings.
        - Next.js will automatically return a 404 status code for URLs that do not exist in your application.
        - In some cases, you might also want to return a 404 status code from page. You can do this by returning the following in place of props:
            - ```javascript
export async function getStaticProps(context) {
  return {
    notFound: true, // triggers 404
  };
}
```
            - Custom 404 page
                - ```javascript
// pages/404.js
export default function Custom404() {
  return <h1>404 - Page Not Found</h1>;
}
```
    - ### 410
        - The [HTTP 410 Gone ](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status/410) 
client error response code indicates that access to the target resource 
is no longer available at the origin server and that this condition is 
likely to be permanent.
        - This is not 
used very often, but you might want to look for this status code if you 
are deleting content on your website that won't exist any more.
        - Examples where a HTTP 410 Gone might be wise to use include:
            - **E-Commerce**: Products permanently removed from inventory.
            - **Forum**: Threads that have been deleted by the user.
            - **Blog**: Blog post removed from site.
        - This status code informs bots that they should never return to crawl this content.
    - ### 500
        - The [HTTP 500 Internal Server Error](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status/500) response code indicates that the server encountered an unexpected condition that prevented it from fulfilling the request.
        - Next.js will automatically return a 500 status code for an unexpected application error. You can [create a custom 500 error page](https://nextjs.org/docs/advanced-features/custom-error-page#500-page) that is statically generated at build time by creating pages/500.js.
        - Example:
            - ```javascript
// pages/500.js
export default function Custom500() {
  return <h1>500 - Server-side error occurred</h1>;
}
```
    - ### 503
        - The [HTTP 503 Service Unavailable](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status/503) server error response code indicates that the server is not ready to handle the request.
        - It's recommended to return this status code when your website is down and 
you predict that the website will be down by an extended period of time.
 This prevents losing rankings on a long-term basis.
- # Robots.txt
    - A [robots.txt file](https://developers.google.com/search/docs/advanced/robots/intro) tells search engine crawlers which pages or files the crawler can or can't request from your site. The robots.txt file is a web standard file that most [good bots](https://www.cloudflare.com/learning/bots/how-to-manage-good-bots) consume before requesting anything from a specific domain.
    - You might want to protect certain areas from your website from being 
crawled, and therefore indexed, such as your CMS or admin, user accounts
 in your e-commerce, or some API routes, to name a few.
    - These files must be served at the root of each host, or alternatively you can redirect the root /robots.txt path to a destination URL and most bots will follow.
    - How to add to Next.js
        - ```javascript
//robots.txt

# Block all crawlers for /accounts
User-agent: *
Disallow: /accounts

# Allow all crawlers
User-agent: *
Allow: /
```
- # XML Sitemaps
    - **Sitemaps** are the easiest way
 to communicate with Google. They indicate the URLs that belong to your 
website and when they update so that Google can easily detect new 
content and crawl your website more efficiently.
    - Even though XML Sitemaps are the most known and used ones, they can also be created via [RSS](https://developers.google.com/search/docs/advanced/sitemaps/build-sitemap) or [Atom](https://developers.google.com/search/docs/advanced/sitemaps/build-sitemap), or even via [Text](https://developers.google.com/search/docs/advanced/sitemaps/build-sitemap) files if you prefer maximum simplicity.
    - A
 sitemap is a file where you provide information about the pages, 
videos, and other files on your site, and the relationships between 
them. Search engines like Google read this file to more intelligently 
crawl your site.
    - Google says:
        - You might need a sitemap if:
            - **Your site is really large.** As a result, it's more likely Google web crawlers might overlook crawling some of your new or recently updated pages.
            - **Your site has a large archive of content pages that are isolated or not well linked to each other.** 
If your site pages don't naturally reference each other, you can list 
them in a sitemap to ensure that Google doesn't overlook some of your 
pages.
            - **Your site is new and has few external links to it.** 
Googlebot and other web crawlers navigate the web by following links 
from one page to another. As a result, Google might not discover your 
pages if no other sites link to them.
            - **Your site has a lot of rich media content (video, images) or is shown in Google News.** If provided, Google can take additional information from sitemaps into account for search, where appropriate.
    - While sitemaps are not mandatory for great 
search engine performance, they can facilitate crawling and indexing to 
bots and hence your content will be picked up faster and rank 
accordingly.
    - It's strongly recommended to 
use sitemaps and make them dynamic as new content is populated across 
your website. Static sitemaps are also valid, but they might be less 
useful to Google as it won't serve for constant discovery purposes.
- # How to add sitemaps to a Next.js Project
    - ## Manual 
        - Relatively simple and static site, manually create a sitemap.xml in the public director
            - ```javascript
  <!-- public/sitemap.xml -->
   <xml version="1.0" encoding="UTF-8">
   <urlset xmlns="http://www.sitemaps.org/schemas/sitemap/0.9">
     <url>
       <loc>http://www.example.com/foo</loc>
       <lastmod>2021-06-01</lastmod>
     </url>
   </urlset>
   </xml>```
    - ## getServerSideProps
        - It's more likely your site will be dynamic. In this case, we can leverage getServerSideProps to generate an XML sitemap on-demand.
        - We can create a new page inside the pages directory such as pages/sitemap.xml.js.
 The goal of this page will be to hit our API to get data that will 
allow us to know the URLs of our dynamic pages. We will then write an 
XML file as the response for /sitemap.xml
            - ```javascript
//pages/sitemap.xml.js
const EXTERNAL_DATA_URL = 'https://jsonplaceholder.typicode.com/posts';

function generateSiteMap(posts) {
  return `<?xml version="1.0" encoding="UTF-8"?>
   <urlset xmlns="http://www.sitemaps.org/schemas/sitemap/0.9">
     <!--We manually set the two URLs we know already-->
     <url>
       <loc>https://jsonplaceholder.typicode.com</loc>
     </url>
     <url>
       <loc>https://jsonplaceholder.typicode.com/guide</loc>
     </url>
     ${posts
       .map(({ id }) => {
         return `
       <url>
           <loc>${`${EXTERNAL_DATA_URL}/${id}`}</loc>
       </url>
     `;
       })
       .join('')}
   </urlset>
 `;
}

function SiteMap() {
  // getServerSideProps will do the heavy lifting
}

export async function getServerSideProps({ res }) {
  // We make an API call to gather the URLs for our site
  const request = await fetch(EXTERNAL_DATA_URL);
  const posts = await request.json();

  // We generate the XML sitemap with the posts data
  const sitemap = generateSiteMap(posts);

  res.setHeader('Content-Type', 'text/xml');
  // we send the XML to the browser
  res.write(sitemap);
  res.end();

  return {
    props: {},
  };
}

export default SiteMap;
```
- # Special Meta Tags for Search Engines
    - **Meta robot tags** are 
directives that search engines will always respect. Adding these robots 
tags can make the indexation of your website easier.
    - There is a difference between directives and suggestions. **Meta robots tags** or[robots.txt](https://nextjs.org/learn/seo/crawling-and-indexing/robots-txt) files are **directives** and will always be obeyed. **Canonical tags** are **recommendations** that Google can decide to obey or not.
    - There are many options when it comes to page level meta tags, but the following are examples that commonly associated with SEO:
        - ```javascript
<meta name="robots" content="noindex,nofollow" />
```
    - The robots tag is probably the most common tag you will see. By default it will have the value index,follow so it does not need to specified, all is also a valid alternative version:
        - ```javascript
<meta name="robots" content="all" />
```
        - Other directives
            - ### noindex
                - To not show this page in search results. Omitting noindex will indicate the page can be indexed and shown in search results.
                - When
 building a website, you might not want to index certain pages. Common 
use cases include settings pages, internal search pages, policies, and 
more.
            - ### nofollow
                - To
 not follow links on this page. Omitting this will allow robots to crawl
 and follow links on this page. Links found on other pages may enable 
crawling, so if link A appears in pagesX and Y, and X has a nofollow robots tag, but Y doesn't, Google may decide to crawl the link.
                - https://developers.google.com/search/docs/crawling-indexing/robots-meta-tag#directives
                - 
