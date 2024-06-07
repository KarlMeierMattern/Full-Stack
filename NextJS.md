# Next.js  
React framework that gives you building blocks to create fully interactive, highly dynamic, and performant web applications.  
By framework, we mean Next.js handles the tooling and configuration needed for React, and provides additional structure, features, and optimizations for your application to solve common application requirements such as routing, data fetching, and caching.  

- When a user visits a web page, the server returns an HTML file to the browser.  
- The browser reads the HTML and constructs the Document Object Model (DOM).  
- The DOM is an object representation of the HTML elements.  
- It acts as a bridge between your code and the user interface, and has a tree-like structure with parent and child relationships.

When you use Next.js in your project, you do not need the following:  
- `react` and `react-dom` scripts, instead, you can install these packages locally using npm.  
- The Babel script because Next.js has a compiler that transforms JSX into valid JavaScript browsers can understand.  
- The `<script type="text/jsx">` tag.  
- The `document.getElementById()` and `ReactDom.createRoot()` methods.  
- The `React.` part of the `React.useState(0)` function.  
- The only code left in the HTML file is JSX, so you can change the file type from `.html` to `.js` or `.jsx`.  

**Steps**:  
1. Create a new file in the same directory as your `index.html` file, called `package.json` with an empty object `{}`.  
2. Run the command `npm install react@latest react-dom@latest next@latest`.  
3. Once complete you should see the following inside `package.json`:  

        {
          "dependencies": {
            "next": "^14.0.3",
            "react": "^18.2.0",
            "react-dom": "^18.2.0"
          }
        }
4. You will also notice a new file called `package-lock.json` file that contains detailed information about the exact versions of each package.

## Routing in Next.js  
- Next.js uses file-system routing. This means that instead of using code to define the routes of your application, you can use folders and files.  
- Adding `export default` to your primary function component helps Next.js distinguish which component to render as the main component of the page.  

## Running the dev server  
1. Add the following to your `package.json` file:  

                "scripts": {
                    "dev": "next dev"
                },
2. In the terminal run `npm run dev`.
3. A new file called `layout.js` is automatically created inside your route folder. This is the main layout of your application. You can use it to add UI elements that are shared across all pages (e.g. navigation, footer, etc).  

## Server & client components  
- An app can be executed in two environments: the server and the client.  
- Next.js uses React **Server Components** by default to improve performance.  
- You can use **Client Components** for smaller parts of your UI.  
- The network boundary separates server and client code.  

By moving rendering and data fetching to the server, you can reduce the amount of code sent to the client, which can improve your application's performance.  
But, to make your UI interactive, you need to update the DOM on the client side.  
Certain operations (e.g. data fetching or managing user state) are better suited for one environment over the other.  

After Server Components are rendered, a special data format called the **React Server Component Payload (RSC)** is sent to the client.  
The RSC payload contains:  
- The rendered result of Server Components.  
- Placeholders (or holes) for where Client Components should be rendered and references to their JavaScript files.  
- React uses this information to consolidate the Server and Client Components and update the DOM on the client.

> [!TIP]
> To make a component a **Client Component** add the React `"use client"` directive at the top of the file. This tells React to render the component on the client.

## Create Next app  
`npx create-next-app@latest`  

---

## Tailwind  
CSS framework that speeds up the development process by allowing you to quickly write utility classes directly in your TSX markup.  
In Tailwind, you style elements by adding class names.  

    <h1 className="text-blue-500">I'm blue!</h1>
When you use `create-next-app` to start a new project, Next.js will ask if you want to use Tailwind. If you select yes, Next.js will automatically install the necessary packages and configure Tailwind in your application.  

---

## Fonts  
- Next.js automatically optimizes fonts in the application when you use the `next/font` module.  
- It downloads font files at build time and hosts them with your other static assets. This means when a user visits your application, there are no additional network requests for fonts which would impact performance.
- In `/app/ui` folder, create a file called `fonts.ts`. Use this file to keep the fonts that will be used throughout your application.

---

## Images  
Next.js can serve static assets, like images, under the top-level `/public` folder. Files inside `/public` can be referenced in your application.  
The `<Image>` component is an extension of the HTML `<img>` tag, and comes with automatic image optimisation, such as: preventing layout shift, resizing images, and lazy loading.  

    import Image from 'next/image';
    <Image
      src="/hero-desktop.png"
      width={1000}
      height={760}
      className="hidden md:block"
      alt="Screenshots of the dashboard project showing desktop version"
    />

---

## Routes & pages  
Next.js uses file-system routing where folders are used to create nested routes. Each folder represents a route segment that maps to a URL segment.

![Screenshot 2024-05-28 at 07 14 38](https://github.com/KarlMeierMattern/Full-Stack/assets/99612323/096ddf98-4a2e-4e48-ade5-b6840bc411e9)  

> [!NOTE]  
> - `page.tsx` is a special Next.js file that exports a React component, and it's required for the route to be accessible.  
> - This is the home page associated with the route `/`.  
> - To create a nested route, you can nest folders inside each other and add `page.tsx` files inside them.  

![Screenshot 2024-05-28 at 07 18 16](https://github.com/KarlMeierMattern/Full-Stack/assets/99612323/116bf0a9-2ce4-4721-a5ec-947ee6fe785a)  

> [!NOTE]  
> - `/app/dashboard/page.tsx` is associated with the `/dashboard` path.  
> - This is how you can create different pages in Next.js: create a new route segment using a folder, and add a `page` file inside it.  
> - By having a special name for `page` files, Next.js allows you to colocate UI components, test files, and other related code with your routes. Only the content inside the `page` file will be publicly accessible.  

![Screenshot 2024-05-28 at 07 32 56](https://github.com/KarlMeierMattern/Full-Stack/assets/99612323/cfc233be-e5e6-46f3-a780-d7fe1493443b)

---

## Layout  
In Next.js, you can use a special `layout.tsx` file to create UI that is shared between multiple pages.  
The `<Layout />` component receives a children prop. This child can either be a page or another layout. The pages inside the folder in which the `layout.tsx` is located will automatically be nested inside a `<Layout />` like so:  

![Screenshot 2024-05-28 at 07 42 49](https://github.com/KarlMeierMattern/Full-Stack/assets/99612323/a945649b-fc88-4aa8-b8ff-f0c4c1acf2b9)

> [!TIP]
> One benefit of using layouts in Next.js is that on navigation, only the `page` components update while the `layout` won't re-render. This is called partial rendering.  

> [!NOTE]  
> - The **root layout** is a requirement and is located at `/app/layout.tsx`.  
> - Any UI you add to the root layout will be shared across all pages in your application.  
> - However, any `layout.tsx` files added to a folder, such as `/app/dashboard/layout.tsx`, are unique to that folder and its pages.

---

## Page navigation  
- In Next.js, you can use the `<Link />` component to link between pages in your application.  
- `<Link>` allows you to do client-side navigation with JavaScript.  
- This avoids full page refreshes when navigating between pages.  
- Whenever `<Link>` components appear in the browser's viewport, Next.js automatically prefetches the code for the linked route in the background. By the time the user clicks the link, the code for the destination page will already be loaded in the background, and this is what makes the page transition near-instant.  

        import Link from 'next/link';
        <Link
            key={link.name}
            href={link.href}
            className="flex h-[48px]"
            >
            <LinkIcon className="w-6" />
            <p className="hidden md:block">{link.name}</p>
        </Link>

---

## Fetching data  
APIs are an intermediary layer between your application code and database. There are a few cases where you might use an API:  
1. If you're using 3rd party services that provide an API.  
2. If you're fetching data from the client, you want to have an API layer that runs on the server to avoid exposing your database secrets to the client i.e. do not query the database directly.  

In Next.js, you can create API endpoints using **Route Handlers**.  

> [!TIP]  
> - If you are using **React Server Components** (fetching data on the server), you can skip the API layer, and query your database directly (using SQL) without risking exposing your database secrets to the client.  
> - Creating a database in the same region as your application code (by using Vercel for example) reduces latency between your server and database.  
> - Fetching data on the server with **React Server Components** allows you to keep expensive data fetches and logic on the server, reduces the client-side JavaScript bundle, and prevents your database secrets from being exposed to the client.  
> - Data from the client is sent to the database server and your component queries the database as opposed to querying the client directly.  

### Using server components  
- Server Components support **promises**, providing a simpler solution for asynchronous tasks like data fetching. You can use `async/await` syntax without reaching out for `useEffect`, `useState` or data fetching libraries.  
- When a function is an `async` component this allows you to use `await` to fetch data.  
- Server Components execute on the server, so you can keep expensive data fetches and logic on the server and only send the result to the client.  
- As mentioned before, since Server Components execute on the server, you can query the database directly without an additional API layer.  

### Request waterfalls  
- Refers to a sequence of network requests that depend on the completion of previous requests.  
- In the case of data fetching, each request can only begin once the previous request has returned data.  
- In some cases waterfalls are necessary (fetching user IDs before fetching their list of friends). In other cases this isn't ideal and impacts performance.  

![Screenshot 2024-05-29 at 18 00 53](https://github.com/KarlMeierMattern/Full-Stack/assets/99612323/00c7079d-5afa-46d4-a320-5390445426fc)
> We need to wait for `fetchRevenue()` to execute before `fetchLatestInvoices()` can start running.  

### Parallel data fetching  
- A common way to avoid waterfalls is to initiate all data requests at the same time - in parallel.  
- You can use the `Promise.all()` or `Promise.allSettled()` functions to initiate all promises at the same time.  
- This can lead to performance gains.  

        const data = await Promise.all([
            invoiceCountPromise,
            customerCountPromise,
            invoiceStatusPromise,
        ]);
    
---

## Static vs dynamic rendering  

### Static rendering  
- With static rendering, data fetching and rendering happens on the server at build time (when you deploy) or during revalidation.  
- The result can then be distributed and cached in a Content Delivery Network (CDN). Whenever a user visits your application, the cached result is served.  

> [!NOTE]  
> **Time-based revalidation**: Automatically revalidates data after a certain amount of time has passed. Useful for data that changes infrequently and freshness is not as critical.  
> **On-demand revalidation**: Manually revalidate data based on an event (e.g. form submission). Useful when you want to ensure the latest data is shown as soon as possible (e.g. when content from your headless CMS is updated).  

![Screenshot 2024-05-29 at 18 12 58](https://github.com/KarlMeierMattern/Full-Stack/assets/99612323/d40364d7-86fa-428f-975c-dc261be3ea81)

**Benefits of static rendering**  
- Faster Websites - Prerendered content can be cached and globally distributed. This ensures that users around the world can access your website's content more quickly and reliably.  
- Reduced Server Load - Because the content is cached, your server does not have to dynamically generate content for each user request.  
- SEO - Prerendered content is easier for search engine crawlers to index, as the content is already available when the page loads. This can lead to improved search engine rankings.  

> [!TIP]  
> - Static rendering is useful for UI with no data or data that is shared across users, such as a static blog post or a product page.  
> - It might not be a good fit for a dashboard that has personalized data that is regularly updated.  

### Dynamic rendering  
- With dynamic rendering, content is rendered on the server for each user at request time (when the user visits the page).  

**Benefits of dynamic rendering**  
- Real-Time Data - Dynamic rendering allows your application to display real-time or frequently updated data. This is ideal for applications where data changes often.  
- User-Specific Content - It's easier to serve personalized content, such as dashboards or user profiles, and update the data based on user interaction.  
- Request Time Information - Dynamic rendering allows you to access information that can only be known at request time, such as cookies or the URL search parameters.  

> [!IMPORTANT]  
> - By default, @vercel/postgres doesn't set its own caching semantics. This allows the framework to set its own static and dynamic behavior.  
> - You can use a Next.js API called `unstable_noStore` inside your Server Components or data fetching functions to opt out of static rendering.  
> - Note: `unstable_noStore` is an experimental API and may change in the future.  

**Drawbacks**  
- The problem with dynamic rendering is what happens if one data request is slower than all the others?  
- With dynamic rendering, your application is only as fast as your slowest data fetch.  

---

## Streaming  
Streaming is a data transfer technique that allows you to break down a route into smaller "chunks" and progressively stream them from the server to the client as they become ready.  

![Screenshot 2024-05-29 at 18 48 31](https://github.com/KarlMeierMattern/Full-Stack/assets/99612323/b681289c-af10-4d43-b64e-a6cbc637c93e)

- Streaming prevents slow data requests from blocking your whole page.  
- This allows the user to see and interact with parts of the page without waiting for all the data to load before any UI can be shown to the user.  

![Screenshot 2024-05-29 at 18 50 48](https://github.com/KarlMeierMattern/Full-Stack/assets/99612323/c7c036e5-0b8b-4732-b2ab-53a688c781ba)

There are two ways you implement streaming in Next.js:  
1. At the page level, with the `loading.tsx` file.
- `loading.tsx` is a special Next.js file built on top of Suspense, which allows you to create fallback UI to show as a replacement while page content loads.  
- The user doesn't have to wait for the page to finish loading before navigating away (this is called interruptable navigation).  
2. For specific components, with `<Suspense>`.  

### Loading skeletons  
- This is a simplified version of the UI that acts a placeholder to indicate to users that the content is loading.  
- Any UI you embed into `loading.tsx` will be embedded as part of the static file, and sent first.

![Screenshot 2024-05-29 at 19 21 31](https://github.com/KarlMeierMattern/Full-Stack/assets/99612323/034b1bcb-e9fa-4156-b84f-c8066684bc63)

### Route groups  
- Route groups allow you to organize files into logical groups without affecting the URL path structure.  
- When you create a new folder using parentheses (), the name won't be included in the URL path. So `/dashboard/(overview)/page.tsx` becomes `/dashboard`.  
- You  can also use route groups to separate your application into sections (e.g. (marketing) routes and (shop) routes) or by teams for larger applications.  

### Streaming components  
- Instead of streaming a whole page you can stream specific components using **React Suspense**.  
- `<Suspense />` allows you to defer rendering parts of your application until some condition is met (e.g. data is loaded).  
- You can wrap your dynamic components in `<Suspense />`. Then, pass it a fallback component to show while the dynamic component loads.  

        <Suspense fallback={<CardsSkeleton />}>
            <CardWrapper />
        </Suspense>

---

## Partial pre-rendering  
- Most routes are not fully static or dynamic. You may have a route that has both static and dynamic content.  
- For example, consider an ecommerce site. You might be able to prerender the majority of the product page, but you may want to fetch the user's cart and recommended products dynamically on-demand.  
- 
![Screenshot 2024-05-30 at 08 07 59](https://github.com/KarlMeierMattern/Full-Stack/assets/99612323/001bda39-bc84-4153-b73c-59a1c41148df)

> [!NOTE]  
> When a user visits a route:  
> - A static route shell is served, ensuring a fast initial load.  
> - The shell leaves holes where dynamic content will load in asynchronous.  
> - The async holes are streamed in parallel, reducing the overall load time of the page.  
> This is different from how your application behaves today, where entire routes are either entirely static or dynamic.  

- At build time (or during revalidation), the static parts of the route are prerendered, and the rest is postponed until the user requests the route.  
- It's worth noting that wrapping a component in Suspense doesn't make the component itself dynamic (`unstable_noStore` achieves this behavior), but rather `Suspense` is used as a boundary between the static and dynamic parts of your route.  
- The great thing about Partial Prerendering is that you don't need to change your code to use it. As long as you're using Suspense to wrap the dynamic parts of your route, Next.js will know which parts of your route are static and which are dynamic.

---

## Adding search & pagination  
Learn how to use the Next.js APIs: `searchParams`, `usePathname`, and `useRouter`.  

### Benefits of implementing search with URL params  
- Bookmarkable and Shareable URLs: Since the search parameters are in the URL, users can bookmark the current state of the application, including their search queries and filters, for future reference or sharing.  
- Server-Side Rendering and Initial Load: URL parameters can be directly consumed on the server to render the initial state, making it easier to handle server rendering.  
- Analytics and Tracking: Having search queries and filters directly in the URL makes it easier to track user behavior without requiring additional client-side logic.  

These are the Next.js client hooks that you'll use to implement the search functionality:  
- `useSearchParams`- Allows you to access the parameters of the current URL. For example, the search params for this URL `/dashboard/invoices?page=1&query=pending` would look like this: `{page: '1', query: 'pending'}`.  
- `usePathname` - Lets you read the current URL's pathname. For example, for the route `/dashboard/invoices`, `usePathname` would return `'/dashboard/invoices'`.  
- `useRouter` - Enables navigation between routes within client components programmatically. There are multiple methods you can use.  

Here's a quick overview of the implementation steps:  
1. Capture the user's input.  
2. Update the URL with the search params.  
3. Keep the URL in sync with the input field.  
4. Update the table to reflect the search query.  

> [!TIP]  
> `"use client"` at the top of a file means this is a Client Component, therefore you can use event listeners and hooks.  
> `<input>` - This is the search input.  
- `URLSearchParams` is a Web API that provides utility methods for manipulating the URL query parameters. Instead of creating a complex string literal, you can use it to get the params string like `?page=1&query=a`.  

> [!IMPORTANT]  
> When to use the `useSearchParams()` hook vs. the `searchParams` prop?  
> - You might have noticed you used two different ways to extract search params. Whether you use one or the other depends on whether you're working on the client or the server.  
> - `<Search>` is a Client Component, so you used the `useSearchParams()` hook to access the params from the client.  
> - `<Table>` is a Server Component that fetches its own data, so you can pass the `searchParams` prop from the page to the component.  
> As a general rule, if you want to read the params from the client, use the useSearchParams() hook as this avoids having to go back to the server.  

> [!TIP]  
> - Debouncing is a programming practice that limits the rate at which a function can fire. In our case, you only want to query the database when the user has stopped typing.  
> How Debouncing Works:  
> - Trigger Event: When an event that should be debounced (like a keystroke in the search box) occurs, a timer starts.  
> - Wait: If a new event occurs before the timer expires, the timer is reset.  
> - Execution: If the timer reaches the end of its countdown, the debounced function is executed.  

---

## Mutating data  

### React Server Actions  
- React Server Actions allow you to run asynchronous code directly on the server.  
- They eliminate the need to create API endpoints to mutate your data.  
- Instead, you write asynchronous functions that execute on the server and can be invoked from your Client or Server Components.  
- Server Actions achieve effective security through techniques like `POST` requests, encrypted closures, strict input checks, error message hashing, and host restrictions, all working together to significantly enhance your app's safety.  

### Using forms with Server Actions  
- In React, you can use the `action` attribute in the `<form>` element to invoke actions.  
- The action will automatically receive the native `FormData` object, containing the captured data.  
- An advantage of invoking a Server Action within a Server Component is **progressive enhancement** - forms work even if JavaScript is disabled on the client.  

        // Server Component
        export default function Page() {
            // Action
            async function create(formData: FormData) {
                'use server';
                
                // Logic to mutate data...
            }
            
            // Invoke the action using the "action" attribute
            return <form action={create}>...</form>;
        }

> [!TIP]  
> - By adding `'use server'` you mark all the exported functions within the file as server functions.  
> - These server functions can then be imported into Client and Server components, making them extremely versatile.  
> - You can also write Server Actions directly inside Server Components by adding `"use server"` inside the action.  

> [!NOTE]  
> - In HTML, you'd pass a URL to the `action` attribute. This URL would be the destination where your form data should be submitted (usually an API endpoint).  
> - However, in React, the `action` attribute is considered a special prop - meaning React builds on top of it to allow actions to be invoked.  
> - Behind the scenes, Server Actions create a `POST` API endpoint. This is why you don't need to create API endpoints manually when using Server Actions.  

### Dynamic Route Segments  
- Next.js allows you to create Dynamic Route Segments when you don't know the exact segment name and want to create routes based on data.  
- This could be blog post titles, product pages, etc.  
- You can create dynamic route segments by wrapping a folder's name in square brackets. For example, `[id]`, `[post]` or `[slug]`.  

---

## Handling errors  
- Handle errors using JavaScript's `try/catch` statements and Next.js APIs.  
- Use the special `error.tsx` file to catch errors in your route segments, and show a fallback UI to the user.  
- Use the `notFound` function and `not-found` file to handle 404 errors (for resources that don’t exist).  
 
### Handling all errors with error.tsx  
- The `error.tsx` file can be used to define a UI boundary for a route segment.  
- It serves as a catch-all for unexpected errors and allows you to display a fallback UI to your users.  
- `error.tsx` needs to be a Client Component i.e. `"use client"`.  
- It accepts two props:  
1. `error`: This object is an instance of JavaScript's native `Error` object.  
2. `reset`: This is a function to reset the error boundary. When executed, the function will try to re-render the route segment.  

![Screenshot 2024-06-03 at 08 34 38](https://github.com/KarlMeierMattern/Full-Stack/assets/99612323/840b67c4-804a-490d-9c01-10a3b514a30a)  

### Handling 404 errors with the notFound function  
- While `error.tsx` is useful for catching all errors, `notFound` can be used when you try to fetch a resource that doesn't exist.  
- `notFound` will take precedence over `error.tsx`, so you can reach out for it when you want to handle more specific errors.  

![Screenshot 2024-06-03 at 08 40 46](https://github.com/KarlMeierMattern/Full-Stack/assets/99612323/5126f65c-df54-42a0-845e-f674dcaec1af)

---

## Improving accessibility  
- Implement server-side validation with Server Actions.  
- Show form errors using the useFormState hook.  
- Use `eslint-plugin-jsx-a11y` with Next.js to implement accessibility best practices.  
- Use React `useFormState` hook to handle form errors, and display them to the user.  
- Accessibility refers to designing and implementing web applications that everyone can use, including those with disabilities. It covers areas such as keyboard navigation, semantic HTML, images, colors, videos, etc.  

### ESLint accessibility plugin  
- By default, Next.js includes the `eslint-plugin-jsx-a11y` plugin to help catch accessibility issues early.  
- For example, this plugin warns if you have images without `alt` text, use the `aria-*` and role attributes incorrectly, and more.
- Add `"lint": "next lint"` in your `package.json` file.  
- Then run `npm run lint` in your terminal.

### Improving accessibility  
1. **Semantic HTML**: Using semantic elements (`<input>`, `<option>`, etc) instead of `<div>` allows assistive technologies to focus on the input elements and provide appropriate contextual information to the user, making the form easier to navigate and understand.  
2. **Labelling**: Including `<label>` and the `htmlFor` attribute ensures that each form field has a descriptive text label. This improves AT support by providing context and also enhances usability by allowing users to click on the label to focus on the corresponding input field.  
3. **Focus Outline**: The fields are properly styled to show an outline when they are in focus. This is critical for accessibility as it visually indicates the active element on the page, helping both keyboard and screen reader users to understand where they are on the form. You can verify this by pressing tab.  

### Client-Side form validation  
- The simplest way is to rely on the form validation provided by the browser by adding the `required` attribute to the `<input>` and `<select>` elements in your forms.  

        <input required id="amount" name="amount" type="number" placeholder="Enter USD amount" className="peer block w-full rounded-md"/>

### Server-Side validation  
By validating forms on the server, you can:  
- Ensure your data is in the expected format before sending it to your database.  
- Reduce the risk of malicious users bypassing client-side validation.  
- Have one source of truth for what is considered valid data.  

> [!TTIP]  
> When using hooks like `useFormState` you will need to turn your file into a Client Component using the `"use client"` directive.  

---

## Adding authentication  
- How to add authentication to your app using NextAuth.js.  
- How to use Middleware to redirect users and protect your routes.  
- How to use React's `useFormStatus` and `useFormState` to handle pending states and form errors.  

### Authentication vs. Authorization  
Authentication checks who you are, and authorization determines what you can do or access in the application.  
- **Authentication** is about making sure the user is who they say they are. You're proving your identity with something you have like a username and password.  
- **Authorization** is the next step. Once a user's identity is confirmed, authorization decides what parts of the application they are allowed to use.  

### NextAuth.js  
- Adds authentication to your application by abstracting away much of the complexity involved in managing sessions, sign-in and sign-out, and other aspects of authentication.  
- Installation: `npm install next-auth@beta`.  
- Next, generate a secret key for your application to encrypt cookies, ensuring the security of user sessions. Run the following command: `openssl rand -base64 32`.  
- Then, in your `.env` file, add your generated key to the `AUTH_SECRET` variable.  
- For auth to work in production, you'll need to update your environment variables in your Vercel project too.  

### Middleware  
- Middleware sits between the request and the application's core logic, allowing you to execute specific code before the request is fully processed and a response is generated.  
- When a request comes in, the middleware intercepts it before it reaches the main application logic.  
- This interception enables you to inspect the request, validate the user's credentials, and potentially perform other tasks related to authentication, such as checking for authorization or setting up session data.  
- Once the middleware has executed its code it can pass control to the main application logic.  

---

## Metadata  
- Metadata is usually within the `<head>` element and is crucial for search engines that need to understand your webpage's content better.  
- Proper metadata helps search engines effectively index webpages thereby enhancing a webpage's SEO, and improving their ranking in search results.  
- Additionally, metadata like Open Graph improves the appearance of shared links on social media, making the content more appealing and informative for users.  

### Types of metadata  
Some common types include:  
- **Title Metadata**: responsible for the title of a webpage that is displayed on the browser tab. Crucial for SEO as it helps search engines understand what the webpage is about.  

        <title>Page Title</title>

- **Description Metadata**: provides a brief overview of the webpage content and is often displayed in search engine results.  

        <meta name="description" content="A brief description of the page content." />

- **Keyword Metadata**: includes the keywords related to the webpage content, helping search engines index the page.  

        <meta name="keywords" content="keyword1, keyword2, keyword3" />

- **Open Graph Metadata**: enhances the way a webpage is represented when shared on social media platforms, providing information such as the title, description, and preview image.  

        <meta property="og:title" content="Title Here" />
        <meta property="og:description" content="Description Here" />
        <meta property="og:image" content="image_url_here" />

- **Favicon Metadata**: links the favicon (a small icon) to the webpage, displayed in the browser's address bar or tab.  

        <link rel="icon" href="path/to/favicon.ico" />


































