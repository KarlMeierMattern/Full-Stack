> [!NOTE]  
> Highlights information that users should take into account, even when skimming.

> [!TIP]
> Optional information to help a user be more successful.

> [!IMPORTANT]  
> Crucial information necessary for users to succeed.

> [!WARNING]  
> Critical content demanding immediate user attention due to potential risks.

> [!CAUTION]
> Negative potential consequences of an action.

# React  
React is a JavaScript library (consisting of APIs) for building reusable, component-driven user interfaces for web pages or applications.  
React combines HTML with JavaScript functionality into its own markup language called JSX.  

Building blocks of a web application:  
- User Interface - how users will consume and interact with your application.  
- Routing - how users navigate between different parts of your application.  
- Data Fetching - where your data lives and how to get it.  
- Rendering - when and where you render static or dynamic content.  
- Integrations - what third-party services you use (for CMS, auth, payments, etc.) and how you connect to them.  
- Infrastructure - where you deploy, store, and run your application code (serverless, CDN, edge, etc.).  
- Performance - how to optimize your application for end-users.  
- Scalability - how your application adapts as your team, data, and traffic grow.  
- Developer Experience - your team's experience building and maintaining your application.

> [!IMPORTANT]  
> For each part of your application, you will need to decide whether you will build a solution yourself or use other tools, such as packages, libraries, and frameworks.  

## Imperative vs. declarative programming  
Imperative programming is writing the steps for how the user interface should be updated.  
Declarative programming you declare what they want to show instead of having to write DOM methods.  
React is a popular declarative library that you can use build user interfaces.  

## JSX  
- React uses a syntax extension of JavaScript called JSX that allows you to write HTML directly within JavaScript.  
- But browsers don't understand JSX out of the box, so you'll need a JavaScript transpiler, such as a Babel, to transform your JSX code into regular JavaScript.  
- Use curly braces to enter "JavaScript land" while you are in "JSX land". You can add any JavaScript expression (something that evaluates to a single value) inside curly braces.  

        function MyComponent() {
          return <h1>This is a simple JSX example</h1>
        }

react is the core React library:  
<code><script src="https://unpkg.com/react@18/umd/react.development.js"></script></code>  

react-dom provides DOM-specific methods that enable you to use React with the DOM:  
<code><script src="https://unpkg.com/react@18/umd/react.development.js"></script></code>  

Browsers don't understand JSX out of the box, so you'll need a JavaScript compiler, such as a Babel, to transform your JSX code into regular JavaScript:  
<code><script src="https://unpkg.com/@babel/standalone/babel.min.js"></script></code>  
In addition, you will need to inform Babel what code to transform by changing the script type to <code>type=text/jsx</code>.  

## Declarative programming  
Declarative programming you declare what they want to show instead of having to write DOM methods.  
React is a popular declarative library that you can use build user interfaces.  

        // Declarative
        <div id="app"></div>
        
        <script type="text/jsx">
          const domNode = document.getElementById("app")
          const root = ReactDOM.createRoot(domNode);
          root.render(<h1>Develop. Preview. Ship.</h1>);
        </script>

> [!NOTE]
> The above can be shortened to `ReactDOM.render(<h1>Develop. Preview. Ship.</h1>, document.getElementById("app"))`.
> The syntax is: `ReactDOM.render(componentToRender, targetNode)`.
> The first argument is the React element or component that you want to render, and the second argument is the DOM node that you want to render the component to.  

## Imperative programming  
Imperative programming is writing the steps for how the user interface should be updated.  

        // Imperative
        <div id="app"></div>
        
        <script type="text/javascript">
          const app = document.getElementById('app');
          const header = document.createElement('h1');
          const text = 'Develop. Preview. Ship.';
          const headerContent = document.createTextNode(text);
          header.appendChild(headerContent);
          app.appendChild(header);
        </script>

## React core concepts  
1. Components: allow you to build self-contained, reusable snippets of code.  
- First, React components should be capitalized to distinguish them from plain HTML and JavaScript.
- Second, you use React components the same way you'd use regular HTML tags, with angle brackets <>.  
        
        function Header() {
            return <h1>Develop. Preview. Ship.</h1>
        }

        const app = document.getElementById("app")
        const root = ReactDOM.createRoot(app);
        root.render(<Header/>);

2. Props: you can design components that accept custom arguments (properties) that change the component's behavior or what is visibly shown when it's rendered to the screen.
- You can pass down these props from parent components to child components.  
- Note: In React, data flows down the component tree. This is referred to as one-way data flow.  

        function Header({ title }) {
          return <h1>{`Cool ${title}`}</h1>;
        }

5. State:  
- Props are read-only information that's passed to components. State is information that can change over time, usually triggered by user interaction.  
- In React, event names are camelCased.  
- The `onClick` event is one of many possible events you can use to respond to user interaction.  
- You can use `onChange` for input fields or `onSubmit` for forms.  

        function HomePage() {
        
            function HandleClick() {
                console.log("increment like count")
            }
            
            return <button onClick={HandleClick}>Like</button>
        }
- React has a set of functions called hooks. Hooks allow you to add additional logic such as state to your components. You can think of state as any information in your UI that changes over time, usually triggered by user interaction.  
- You can use state to store and increment the number of times a user has clicked a "Like" button for example.  
- The React hook used to manage state is called `useState()`.

Example  
- The first item in the array is the state value, which you can name anything. It's recommended to name it something descriptive.  
- The second item in the array is a function to update the value. You can name the update function anything, but it's common to prefix it with set followed by the name of the state variable you're updating.  
- You can also take the opportunity to add the initial value of your likes state to 0.  
- Clicking the button will now call the `handleClick` function, which calls the `setLikes` state updater function with a single argument of the current number of `likes + 1`.  

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

> [!CAUTION]  
> JSX must return a single element. This one parent element would wrap all of the other levels of nested elements.  
> For instance, several JSX elements written as siblings with no parent wrapper element will not transpile.  

        // Valid JSX:
        <div>
          <p>Paragraph One</p>
          <p>Paragraph Two</p>
          <p>Paragraph Three</p>
        </div>
        
        // Invalid JSX:
        <p>Paragraph One</p>
        <p>Paragraph Two</p>
        <p>Paragraph Three</p>

> [!TIP]  
> To put comments inside JSX, you use the syntax `{/* */}` to wrap around the comment text.


---

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

To make a component a **Client Component** add the React `"use client"` directive at the top of the file. This tells React to render the component on the client.  





















