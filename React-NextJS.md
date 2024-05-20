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

## Imperative vs. declarative programming  
Imperative programming is writing the steps for how the user interface should be updated.  
Declarative programming you declare what they want to show instead of having to write DOM methods.  
React is a popular declarative library that you can use build user interfaces.  

## JSX  
- React uses a syntax extension of JavaScript called JSX that allows you to write HTML directly within JavaScript.  
- But browsers don't understand JSX out of the box, so you'll need a JavaScript transpiler, such as a Babel, to transform your JSX code into regular JavaScript.  
- In JSX you can't use the word `class` to define HTML classes as this is a reserved word in JavaScript. Instead, JSX uses `className`.  
- The naming convention for all HTML attributes and event references in JSX become camelCase. For example, `onClick`, `onChange` etc.
- JSX elements must be written with a self-closing tag. A `<div>` can be written as `<div></div>` in most instances or `<div />`, when it has no children.

## Components in JSX  
- Everything in React is a component.  
- There are two ways to create a React component. The first way is to use a JavaScript function.  
- Defining a component in this way creates a **stateless component**, which can receive data and render it, but does not manage or track changes to that data.  
- React requires function names to begin with a capital letter.

> [!TIP]  
> Use curly braces to enter "JavaScript land" while you are in "JSX land". You can add any JavaScript expression (something that evaluates to a single value) inside curly braces.  

        // Normal function
        function MyComponent() {
            return <h1>This is a simple JSX example</h1>;
        }

        // Arrow function
        const MyComponent = () => {
          return <h1>This is a simple JSX example</h1>;
        }

- The other way to define a React component is with the **ES6 class syntax**.
- This is done by extending the `React.Component` class so that the class has access to many useful React features, such as local state and lifecycle hooks.
- The class also has a `constructor` defined within it that calls `super()`, which is used to call the constructor of the parent class, in this case `React.Component`.
- The constructor is a special method used during the initialisation of objects that are created with the `class` keyword.
- It is best practice to call a component's constructor with `super`, and pass `props` to both. This makes sure the component is initialized properly.  

        class Kitten extends React.Component {
          constructor(props) {
            super(props);
          }
        
          render() {
            return (
              <h1>Hi</h1>
            );
          }
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
### 1. Components  
- Allow you to build self-contained, reusable snippets of code.  
- First, React components should be capitalized to distinguish them from plain HTML and JavaScript.
- Second, you use React components the same way you'd use regular HTML tags, with angle brackets <>.  
        
        function Header() {
            return <h1>Develop. Preview. Ship.</h1>
        }

        const app = document.getElementById("app")
        const root = ReactDOM.createRoot(app);
        root.render(<Header/>);
- To render a component as a child in a React component, you include the component name written as a custom HTML tag in the JSX.  
- When React encounters a custom HTML tag that references another component (a component name wrapped in `< />`), it renders the markup for that component in the location of the tag.  

        // within the parent component
        return (
         <div>
          <ChildComponent/>
         </div>
        )
- A typical React component is an ES6 class which extends `React.Component`. It has a `render` method that returns HTML (from JSX) or null. This is the basic form of a React component.  

        class MyComponent extends React.Component {
          constructor(props) {
            super(props);
          }
          render() {
            return (
              <div>
                <h1>My First React Component!</h1>
              </div>
            )
          }
        }
        
        ReactDOM.render(<MyComponent/>, document.getElementById("challenge-node"))

### 2. Props  
- You can design components that accept custom arguments (properties) that change the component's behavior or what is visibly shown when it's rendered to the screen.  
- You can pass down these props from parent components to child components.  
- Note: In React, data flows down the component tree. This is referred to as one-way data flow.  

        function Header({ title }) {
          return <h1>{`Cool ${title}`}</h1>;
        }
- React provides useful type-checking features to verify that components receive props of the correct type using `propTypes`.  
- This will throw a useful warning when the data is of any other type. It's considered a best practice to set `propTypes` when you know the type of a prop ahead of time.  

        const Items = (props) => {
          return <h1>Current Quantity of Items in Cart: {props.quantity}</h1>
        };
        
        // Define propTypes for the Items component to require quantity as a prop and verify that it is of type number
        Items.propTypes = { quantity: PropTypes.number.isRequired }
- `defaultProps` sets the default properties.  

        // if you render the Camper component without passing a name prop, it will display "CamperBot"
        Camper.defaultProps = { name: "CamperBot" };
- If the component that you're passing a prop to is an ES6 class component, rather than a stateless functional component you must use the `this` keyword anytime you refer to a class component within itself.  

        class Welcome extends React.Component {
          constructor(props) {
            super(props);
          }
          render() {
            return (
                <div>
                  <p>Hello, <strong>{this.props.name}</strong>!</p>
                </div>
            );
          }
        };

### 3. State  
- Props are read-only information that's passed to components. State is information that can change over time, usually triggered by user interaction.  
- You want your apps to respond to state changes and present an updated UI when necessary.  
- In React, event names are camelCased.  
- You create state in a React component by declaring a state property on the component class in its constructor.  
- This initializes the component with state when it is created.  
- The state property must be set to a JavaScript object. Declaring it looks like this.
- If you want to access a state value within the return of the render method, you have to enclose the value in curly braces.  

        class StatefulComponent extends React.Component {
          constructor(props) {
            super(props);
            this.state = {
              firstName: "Karl",
            }
          }
        
          render() {
            return (
            <div>
            { /* Change code below this line */ }
            <p>{this.state.name}</p>
            { /* Change code above this line */ }
            </div>
            );
          }
        };
> [!NOTE]  
> If you make a component stateful its state is local to that component and no other components are aware of its state.  
> Unless you pass state data to a child component as props.  

- The `onClick` event is one of many possible events you can use to respond to user interaction.  
- You can use `onChange` for input fields or `onSubmit` for forms.  

        function HomePage() {
        
            function HandleClick() {
                console.log("increment like count")
            }
            
            return <button onClick={HandleClick}>Like</button>
        }
- React expects you to never modify state directly. Instead always use `this.setState()` when state changes occur passing in an object with key-value pairs.  
- The keys are your state properties and the values are the updated state data.  

        this.setState({
          username: 'Lewis'
        });
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
- A **stateless functional component** is any function you write which accepts props and returns JSX.  
- A **stateless component**, on the other hand, is a class that extends `React.Component`, but does not use internal state.  
- Finally, a **stateful component** is a class component that does maintain its own internal state. You may see stateful components referred to simply as components or React components.  

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

### Methods  
- You can also define methods for your component class.  
- A class method typically needs to use the `this` keyword so it can access properties on the class (such as state and props) inside the scope of the method.  
- One common way is to explicitly bind this in the constructor so this becomes bound to the class methods when the component is initialised.  
- Example: `this.handleClick = this.handleClick.bind(this)`.  
- Then, when you call a function within your class method, `this` refers to the class and will not be undefined.  

> [!TIP]  
> By using an arrow function, you don't need to bind a method in the constructor.  

        reset = () => {
          this.setState((prevState) => ({ count: 0 }));
        }

> [!TIP]  
> Call `event.preventDefault()` in the submit handler (method), to prevent the default form submit behavior which will refresh the web page.  

> [!IMPORTANT]  
> **Unidirectional data flow** refers to state which flows in one direction down the tree of your application's components, from the stateful parent component to child components.  
> Generally state management (parent) should be handled separately to UI rendering (children).  

### Pass state as props to child components  

        // In the parent component's render method we're passing the name state as a prop to the Navbar component
        <Navbar names={this.state.name} />
        
        // Then, in the Navbar component's render method, we're accessing the names prop instead of trying to access the state directly
        <h1>Hello, my name is: {this.props.names}</h1>


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

> [!TIP]
> To make a component a **Client Component** add the React `"use client"` directive at the top of the file. This tells React to render the component on the client.  





















