# React  
React is a JavaScript library (consisting of APIs) for building reusable, component-driven user interfaces for web pages or applications.  
React combines HTML with JavaScript functionality into its own markup language called JSX.  

## Building blocks of a web application:  
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

> [!CAUTION]  
> React expects you to never modify state directly. Instead always use `this.setState()` when state changes occur passing in an object with key-value pairs.  
> The keys are your state properties and the values are the updated state data.  

        this.setState({
          username: 'Lewis'
        });

- A **stateless  component** is any function you write which accepts props and returns JSX.  
- A **stateless component**, on the other hand, is a class that extends `React.Component`, but does not use internal state.  

        const StatelessComponent = (props) => {
          // Component logic and rendering
          return <div>Hello, {props.name}</div>;
        };

- Finally, a **stateful component** is a class component that extends `React.Component` and maintains its own internal state (`this.state`).  

---

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

---

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

### Lifecycle methods  
- Lifecycle methods/hooks are special methods that provide opportunities to perform actions at specific points in the lifecycle of a component.  
- They allow you to catch components at certain points in time. This can be before they are rendered, before they update, before they receive props, before they unmount, and so on.  
- Examples include `componentWillMount()`, `componentDidMount()`, `shouldComponentUpdate()`, `componentDidUpdate()`, `componentWillUnmount()`.

> [!TIP]
> `componentDidMount()` is useful to use when executing API calls. When you call an API in this method, and call `setState()` with the data that the API returns, it will trigger an update/re-rendering once you receive the data.  

> [!IMPORTANT]
> `shouldComponentUpdate()`, which takes `nextProps` and `nextState` as parameters, is a lifecycle method you can call when child components receive new state or props, and declare specifically if the components should update or not.   
> The method must return a boolean value that tells React whether or not to update the component. You can compare the current props (`this.props`) to `nextProps` to determine if you need to update or not, and return true or false.  

    shouldComponentUpdate(nextProps, nextState) {
        console.log('Should I update?');
        if (nextProps.value % 2 === 0) {
            return true
        }
    }

---

### Inline styles  
- JSX elements use the style attribute, but because of the way JSX is transpiled, you can't set the value to a string. Instead, you set it equal to a JavaScript object using `{{}}`.  
- Hyphenated words like `font-size` are invalid syntax for JavaScript object properties, so React uses camel case. As a rule, any hyphenated style properties are written using camel case in JSX.
- All property value length units (like `height`, `width`, and `fontSize`) are assumed to be in px unless otherwise specified. If you want to use em, for example, you wrap the value and the units in quotes, like `{fontSize: "4em"}`.  

        // camelcase fontSize
        // You can optionally set the font size to be a number, omitting the units px, or write it as "72px".
        <div style={{color:"red", fontSize: "72px"}}>Big Red</div>

> [!TIP]  
> If you have a large set of styles, you can assign a style object to a constant to keep your code organised.

    const styles = {
      color: "purple",
      fontSize: 40,
      border: "2px solid purple"
    }
    
    class Colorful extends React.Component {
      render() {
        return (
          <div style={styles}>Style Me!</div>
        );
      }
    };

### If/else  
- Use if/else to tie elements that are rendered to a condition.  
- When the condition is true, one view renders. When it's false, it's a different view.
- if/else statements can't be inserted directly into JSX code. When an if/else statement is required, it is outside the return statement.  

      // Standard if/else
      render() {
        if (this.state.display) {
          return (
            <div>
              <button onClick={this.toggleDisplay}>Toggle Display</button>
              <h1>Displayed!</h1>
            </div>
          );
        } else {
          return (
            <div>
              <button onClick={this.toggleDisplay}>Toggle Display</button>
            </div>
          );
        }
      }

### Use && for a more concise conditional  

    render() {
    return (
      <div>
        <button onClick={this.toggleDisplay}>Toggle Display</button>
        {this.state.display && <h1>Displayed!</h1>}
      </div>
    );
    }

### Ternary operator  

    {
        this.state.userAge === ''
        ? buttonOne
        : this.state.userAge < 18
        ? buttonThree
        : buttonTwo
    }

### &&, ||, ternary  

    render() {
        return <h1>{this.props.fiftyFifty && "You Win!" || !this.props.fiftyFifty && "You Lose!"}</h1>;
    }

### Counter  

    handleClick() {
        this.setState(prevState => ({
            counter: prevState.counter + 1
        }));
    }

### Change CSS inline styles  

    render() {
        let inputStyle = {border: '1px solid black'};
        if (this.state.input.length > 15) {
            inputStyle = { border: '3px solid red' };
        }
    }

### Map method over an array  
- When you create an array of elements, each one needs a key attribute set to a unique value. React uses these keys to keep track of which items are added, changed, or removed. This helps make the re-rendering process more efficient when the list is modified in any way.  

        this.state = {
            toDoList: []
        }
        
        render() {
            const items = this.state.toDoList.map((item, index) => (
              <li key={index}>{item}</li>
            ));
        }

### Filter method  

    class MyComponent extends React.Component {
      constructor(props) {
        super(props);
        this.state = {
          users: [
            {
              username: 'Jeff',
              online: true
            },
            {
              username: 'Alan',
              online: false
            },
            
          ]
        };
      }
      render() {
        const usersOnline = this.state.users.filter(user => user.online);
        const renderOnline = usersOnline.map((item,index) => (
          <li key={index}>{item.username}</li>
        ));
        return (
          <div>
            <h1>Current Online Users:</h1>
            <ul>{renderOnline}</ul>
          </div>
        );
      }
    }

### SSR (server side rendering)  
- There are some use cases where it makes sense to render a React component on the server.
- Since React is a JavaScript view library you can run JavaScript on the server with Node.
- React provides a `renderToString()` method you can use for this purpose.  

Two reasons to render on the server:  
1. SEO: client-side rendering would consist of a relatively empty HTML file and a large bundle of JavaScript when initially loaded to the browser. This is not ideal for search engines content indexing. If you render the initial HTML markup on the server and send this to the client, the initial page load contains all the rendered content that can be crawled by search engines.  
2. Inital load performance: with SSR the initial HTML payload is pre-rendered on the server and sent to the client, reducing the initial load time and providing a faster initial page load experience.  

- Search engines crawl the HTML that is sent to the client's browser, not the server-side code itself.
- When a React application is rendered entirely on the client-side (using `ReactDOM.render`), the initial HTML sent to the browser is minimal, usually just a root `<div>` element where React will later attach the rendered content.  
- Search engines crawling this initial HTML will not see any meaningful content, making it difficult for them to understand and index the application's pages effectively.  
- However, with SSR (using `ReactDOMServer.renderToString(<App/>`), the initial HTML payload sent to the browser contains the fully rendered markup of the React components, including their content and structure. This pre-rendered HTML, which represents the initial state of the application, is what search engines can crawl and index.  










