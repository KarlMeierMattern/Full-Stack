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

> [!IMPORTANT]  
> React components are regular JavaScript functions, but their names must start with a capital letter or they won’t work!  

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

## Components  
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

---

## Props  
- You can design components that accept custom arguments (properties) that change the component's behavior or what is visibly shown when it's rendered to the screen.  
- You can pass down these props from parent components to child components.  
- Note: In React, data flows down the component tree. This is referred to as one-way data flow.  
- Props are immutable (meaning “unchangeable”).  
- When a component needs to change its props (e.g. in response to a user interaction or new data), it will have to “ask” its parent component to pass it different props—a new object.  
- Don’t try to “change props”. When you need to respond to the user input (like changing the selected color), you will need to “set state”.  

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

### Syntax for destructuring props  

![Screenshot 2024-06-21 at 08 41 24](https://github.com/KarlMeierMattern/Full-Stack/assets/99612323/8074a062-784e-4c21-a78d-3db98807915a)  

### Default values for props  

![Screenshot 2024-06-21 at 08 44 36](https://github.com/KarlMeierMattern/Full-Stack/assets/99612323/2975ed3a-ef36-45d1-9558-3b0839e5205a)  

> [!TIP]  
> You can forward all props with `<Avatar {...props} />` JSX spread syntax.  

---  

## State  
- State is information that can change over time, usually triggered by user interaction.  
- You want your apps to respond to state changes and present an updated UI when necessary.  
- State is local to a component instance on the screen. In other words, if you render the same component twice, each copy will have completely isolated state.  
- You can pass state data to a child component as props.  
- If you want child components to share state the right way to do it is to remove state from child components and add it to their closest shared parent.  
- When deciding whether to include state consider if you need a component to re-render based on new input or to show new input. If you do, then state will trigger a re-render. If you don't, then local variables will work.  

> [!TIP]  
> - The convention is to name this pair something like `const [something, setSomething]`.  
> - The first item in the array is the **state variable**, which is the value stored.  
> - The second item is the **state setter function** to update the state variable and trigger React to render the component again.  

The `onClick` event is one of many possible events you can use to respond to user interaction. You can use `onChange` for input fields or `onSubmit` for forms.  

        function HomePage() {
        
            function HandleClick() {
                console.log("increment like count")
            }
            return <button onClick={HandleClick}>Like</button>
        }

> [!NOTE]  
> - In React, `useState`, as well as any other function starting with `use`, is called a Hook.  
> - Hooks are special functions that are only available while React is rendering. They let you “hook into” different React features like state.  
> - Hooks can only be called at the top level of your components or your own Hooks.  
> - You can’t call Hooks inside conditions, loops, or other nested functions.  
> - Hooks are functions, but it’s helpful to think of them as unconditional declarations about your component’s needs.  
> - You “use” React features at the top of your component similar to how you “import” modules at the top of your file.  

### Example  
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

> [!TIP]  
> The convention for naming events & their handlers is to name this pair `onSomething` and `handleSomething`.  
> You could name it anything you like, but conventions make things easier to understand across projects.  

---

## Render & commit  
- Triggering a render (delivering the guest’s order to the kitchen).  
- Rendering the component (preparing the order in the kitchen).  
- Committing to the DOM (placing the order on the table).  

![Screenshot 2024-06-30 at 14 54 57](https://github.com/KarlMeierMattern/Full-Stack/assets/99612323/891029cf-1db3-449d-bded-856750152909)

### Step 1: Trigger a render  
There are two reasons for a component to render:  
1. It’s the component’s initial render; and
2. The component’s (or one of its ancestors’) state has been updated (using the set function).  

#### Initial render  
Rendering must always be a pure calculation:  
- Same inputs, same outputs; and  
- Components mind their own business (should not change any objects or variables that existed before rendering).  

When developing in `StrictMode` React calls each component’s function twice, which can help surface mistakes caused by impure functions.  

    import App from "./app.js"
    import React, { StrictMode } from "react";
    import { createRoot } from "react-dom/client";
    
    const root = createRoot(document.getElementById("root"));
    root.render(
    <StrictMode>
        <App />
    </StrictMode>
    );

### Step 2: React renders your components  
After you trigger a render, React calls your components to figure out what to display on screen. “Rendering” is React calling your components.  

- On initial render, React will call the `root` component.  
- For subsequent renders, React will call the function component whose state update triggered the render.  

All components nested within a re-rendered component are also re-rendered.  

### Step 3: React commits changes to the DOM  
After rendering (calling) your components, React will modify the DOM.  
- For the initial render, React will use the `appendChild()` DOM API to put all the DOM nodes it has created on screen.  
- For re-renders, React will apply the minimal necessary operations to make the DOM match the latest rendering output. React does not touch the DOM if the rendering result is the same as last time.  

### Browser paint  
After rendering is done and React updated the DOM, the browser will repaint the screen, known as “browser rendering”.  

---

## State as a snapshot  
“Rendering” means that React is calling your component, which is a function. The JSX you return from that function is like a snapshot of the UI in time.
The state stored in React may have changed by the time the alert runs, but it was scheduled using a snapshot of the state at the time the user interacted with it!
A state variable’s value never changes within a render, even if its event handler’s code is asynchronous.
React keeps the state values “fixed” within one render’s event handlers. You don’t need to worry whether the state has changed while the code is running.


### Example  

    import { useState } from 'react';
    
    export default function Form() {
      const [to, setTo] = useState('Alice');
      const [message, setMessage] = useState('Hello');
    
      return (
        <form onSubmit={e => {
          e.preventDefault();
          setTimeout(() => {
            alert(`You said ${message} to ${to}`)
          }, 5000);
        }}>
          <label>
            To:{' '}
            <select
              value={to}
              onChange={e => setTo(e.target.value)}>
              <option value="Alice">Alice</option>
              <option value="Bob">Bob</option>
            </select>
          </label>
          <textarea
            placeholder="Message"
            value={message}
            onChange={e => setMessage(e.target.value)}
          />
          <button type="submit">Send</button>
        </form>
      );
    }

---

## Updater function  
React processes state updates after event handlers have finished running. This is called **batching**.  
If you would like to update the same state variable multiple times before the next render you can use `n => n + 1`, which is called an **updater function** when you pass it to a state setter function.  
1. React queues this function to be processed after all the other code in the event handler has run.  
2. During the next render, React goes through the queue and gives you the final updated state.  

        setNumber(number + 5) // state/number is 0, so setNumber(0 + 5). React adds “replace with 5” to its queue (returns 5).
        setNumber(n => n + 1) // n => n + 1 is an updater function. React adds that function to its queue (returns 5+1 = 6).
        setNumber(42) // React adds “replace with 42” to its queue (returns 42).

Here’s how you can think of what you’re passing to the setNumber state setter:  
- An updater function (e.g. `n => n + 1`) gets added to the queue.  
- Any other value (e.g. number 5) adds “replace with 5” to the queue, ignoring what’s already queued.  

After the event handler completes, React will trigger a re-render. During the re-render, React will process the queue. Updater functions run during rendering, so updater functions must be pure and only return the result. Don’t try to set state from inside of them or run other side effects.  

---

## Updating objects in state  
While objects in React state are technically mutable, you should treat them as if they were immutable (read-only) like numbers, booleans, and strings.  

    const [position, setPosition] = useState({
        x: 0,
        y: 0
    });
    
    <div
        onPointerMove={e => {
            setPosition({
                x: e.clientX,
                y: e.clientY
            })
        }}
    </div>

### Local mutation  
Mutation is only a problem when you change existing objects that are already in state. Mutating an object you’ve just created is okay because no other code references it yet. This is called a “local mutation”.  

These two pieces of code are equivalent:  

    // Option 1
    setPosition({
        x: e.clientX,
        y: e.clientY
    })
    
    // Option 2: mutating a fresh object you have just created
    const nextPosition = {};
    nextPosition.x = e.clientX;
    nextPosition.y = e.clientY;
    setPosition(nextPosition);

---

## Copying objects with spread syntax  
Assuming we want to change only the `firstName` in the state object.  

    // Setting state
    const [person, setPerson] = useState({
        firstName: 'Barbara',
        lastName: 'Hepworth',
        email: 'bhepworth@sculpture.com'
      });
    
    // Option 1 is verbose
    const handleFirstNameChange = (e) => {
        setPerson({
          firstName: 'Barbara',
          lastName: 'Hepworth',
          email: 'bhepworth@sculpture.com',
          firstName: e.target.value
        })
      }
    
    // Option 2 is cleaner using the spread operator to copy the existing properties and then updates firstName
    const handleFirstNameChange = (e) => {
        setPerson({
          ...person,
          firstName: e.target.value
        })
      }

> [!NOTE]  
> Note that the `...` spread syntax is “shallow” meaning it only copies things one level deep. This makes it fast, but it also means that if you want to update a nested property, you’ll have to use it more than once.  

---

## Using a single event handler for multiple fields  
Add a `name` property to the element/s where your event handlers are

    export default function Form() {
        const [person, setPerson] = useState({
            firstName: 'Barbara',
            lastName: 'Hepworth',
        });
    
        // Targets the name property of the various input fields
        function handleChange(e) {
            setPerson({
                ...person,
                [e.target.name]: e.target.value
            });
        }
        
        return (
            <>
                <label>
                    First name:
                    <input
                        name="firstName"
                        value={person.firstName}
                        onChange={handleChange}
                    />
                </label>
                <label>
                    Last name:
                    <input
                        name="lastName"
                        value={person.lastName}
                        onChange={handleChange}
                    />
                </label>
                <p>
                    {person.firstName}{' '}
                    {person.lastName}{' '}
                </p>
            </>
        );
    }

---

## Updating a nested object  

    const [person, setPerson] = useState({
      name: 'Niki de Saint Phalle',
      artwork: {
        title: 'Blue Nana',
        city: 'Hamburg',
        image: 'https://i.imgur.com/Sd1AgUOm.jpg',
      }
    });

    // Update the city property
    setPerson({
        ...person, // Copy other fields
        artwork: { // but replace the artwork
            ...person.artwork, // with the same one
            city: "Cape Town" // but in Cape Town
        }
    });

---

## Immer for nested objects  
If your state is deeply nested, you might want to consider flattening it using a shortcut to nested spreads.  
Immer is a popular library that lets you write using the convenient but mutating syntax and takes care of producing the copies for you.  
With Immer, the code you write looks like you are “breaking the rules” and mutating an object.  
But unlike a regular mutation, it doesn’t overwrite the past state!  

The `draft` provided by Immer is a special type of object, called a Proxy, that “records” what you do with it. This is why you can mutate it freely as much as you like! Under the hood, Immer figures out which parts of the draft have been changed, and produces a completely new object that contains your edits.  

> [!NOTE]  
> Run `npm install use-immer` to add Immer as a dependency.  
> `import { useImmer } from 'use-immer'`  
> You can mix and match `useState` and `useImmer` in a single component as much as you like.  

    // Option 1 using spread syntax 
    function handleFirstNameChange (e) => {
        setPerson({
            ...person,
            firstName: e.target.value
        })
    }
    
    // Option 2 using Immer
    function handleNameChange(e) {
        updatePerson(draft => {
            draft.name = e.target.value;
        });
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
    
![Screenshot 2024-06-23 at 17 01 30](https://github.com/KarlMeierMattern/Full-Stack/assets/99612323/f80282c8-be41-4ea0-b0e5-68283930fbd5)  

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

![Screenshot 2024-06-23 at 18 22 45](https://github.com/KarlMeierMattern/Full-Stack/assets/99612323/6436b033-79cb-4407-a7f1-ba6c1988fb18)  

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

![Screenshot 2024-06-23 at 17 56 50](https://github.com/KarlMeierMattern/Full-Stack/assets/99612323/50af8366-6c74-4d19-8d43-588b29ba110f)  

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

---

## Children components  
- Children prop in child components: Allows the child component to render dynamic content provided by the parent component.  
- Children prop in parent components: Allows the parent component to act as a container that can render nested child components or elements.  

### Example: child component renders dynamic content  
        
        export default function App() {
          return (
            <Toolbar
              onPlayMovie={() => alert('Playing!')}
            />
          );
        }
        
        function Toolbar({ onPlayMovie }) {
          return (
            <div>
              <Button onClick={onPlayMovie}>
                Play Movie
              </Button>
            </div>
          );
        }
        
        function Button({ onClick, children }) {
          return (
            <button onClick={onClick}>
              {children}
            </button>
          );
        }

### Exmple: parent acts as container  

        function Card({ children }) {
          return (
            <div className="card">
              {children}
            </div>
          );
        }
        
        export default function Profile() {
          return (
            <Card>
              <Avatar/>
            </Card>
          );
        }
---  

## Event handlers  
- Event handler functions are usually defined inside your components.  
- By convention, it is common to name event handlers as `handle` followed by the event name.  
- You’ll often see `onClick={handleClick}`, `onMouseEnter={handleMouseEnter}`, and so on.  

### Option 1: default  

    export default function Button() {
      function handleClick() {
        alert('You clicked me!');
      }
    
      return (
        <button onClick={handleClick}>
          Click me
        </button>
      );
    }

### Option 2: inline in JSX  

    <button onClick={function handleClick() {
      alert('You clicked me!');
    }}>

### Option 3: arrow/anonymous function  

    <button onClick={() => 
      alert('You clicked me!');
    }>

---

## Event propagation  
- Event handlers will also catch events from any children your component might have.  
- We say that an event “bubbles” or “propagates” up the tree: it starts with where the event happened, and then goes up the tree.  
- `e.stopPropagation()` stops the event handlers attached to the tags above (in parent elements) from firing.  

> [!WARNING]  
> All events propagate in React except `onScroll`, which only works on the JSX tag you attach it to.  
> If you want to prevent an event from reaching parent components, you need to call `e.stopPropagation()`.  

    // e.stopPropagation() prevents the event from bubbling up to the parent
    <button onClick={e => {
        e.stopPropagation();
        onSmash();
    }}>

---

## Preventing default behavior  
- Some browser events have default behavior associated with them.  
- For example, a `<form>` submit event, which happens when a `button` inside of it is clicked, will reload the whole page by default.  
- `e.preventDefault()` prevents the default browser behavior for the few events that have it.  

        export default function Signup() {
          return (
            <form onSubmit={e => {
              e.preventDefault();
              alert('Submitting!');
            }}>
              <input />
              <button>Send</button>
            </form>
          );
        }

---

































