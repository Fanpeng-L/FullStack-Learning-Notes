# Next.js

## 1. Rendering
**Client-Side Rendering:**  
In a standard React application, the browser receives an empty HTML shell from the server along with the JavaScript instructions to construct the UI. This is called client-side rendering because the initial rendering work happens on the user's device.  
**Pre-Rendering:**  
Next.js **pre-renders every page** by default. The HTML is generated in advance, on a server, instead of having it all done by JavaScript on the user's device.

💡 When to use Server-side rendering?
- When the data needs to be up-to-date with every request

<br>

## 2. Pages (React components)
In Next.js, a page is a React Component, which is exported from a file in the pages folder.  
- `pages/index.js` is associated with the `/` route;  
- `pages/posts/first-post.js` is associated with the `/posts/first-post` route.

`Link` Component:  
```js
import Link from 'next/link';

<h1 className={styles.title}>
  Read <Link href="/posts/first-post">this page!</Link>
</h1>
```
The Link component enables client-side navigation between two pages in the same Next.js app. Client-side navigation means that the page transition happens using JavaScript, which is faster than the default navigation done by the browser.  

## 3. Metadata 
