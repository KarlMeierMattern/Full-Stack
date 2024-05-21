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
