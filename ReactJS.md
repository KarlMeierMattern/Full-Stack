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

## Event handlers  
Functions passed to event handlers must be passed, not called.  

`<button onClick={handleClick}>` passes the handleClick function.  
`<button onClick={() => alert('...')}>` passes the `() => alert('...')` function.  

![Screenshot 2024-07-04 at 09 00 53](https://github.com/KarlMeierMattern/Full-Stack/assets/99612323/17f91847-8bd5-4f0b-afcf-d64c42945722)  

![Screenshot 2024-07-04 at 09 03 08](https://github.com/KarlMeierMattern/Full-Stack/assets/99612323/6928d1ae-20df-4179-9826-c75a8ecfc4de)  

---

## Components  
Allow you to build self-contained, reusable snippets of code. React components should be capitalized to distinguish them from plain HTML and JavaScript. You use React components the same way you'd use regular HTML tags, with angle brackets <>.  
        
        function Header() {
            return <h1>Develop. Preview. Ship.</h1>
        }

        const app = document.getElementById("app")
        const root = ReactDOM.createRoot(app);
        root.render(<Header/>);
 
To render a component as a child in a React component, you include the component name written as a custom HTML tag in the JSX. When React encounters a custom HTML tag that references another component (a component name wrapped in `< />`), it renders the markup for that component in the location of the tag.  

        // within the parent component
        return (
         <div>
          <ChildComponent/>
         </div>
        )
        
---

## Passing props to a component  
Link: https://react.dev/learn/passing-props-to-a-component#passing-jsx-as-children  

React components use props to communicate with each other. Every parent component can pass some information to its child components by giving them props. You can pass any JavaScript value through them, including objects, arrays, and functions.  

Props are the information that you pass to a JSX tag. For example, predefined props like `className`, `src`, `alt`, `width`, and `height` are some of the props you can pass to an `<img>`:  

    function Avatar() {
      return (
        <img
          className="avatar"
          src="https://i.imgur.com/1bX5QH6.jpg"
          alt="Lin Lanying"
          width={100}
          height={100}
        />
      );
    }

But you can pass any props to your own components, such as `<Avatar>`, to customize them:  

    function Avatar({ person, size }) {
      return (
        <img
          className="avatar"
          src={getImageUrl(person)}
          alt={person.name}
          width={size}
          height={size}
        />
      );
    }

### Syntax for destructuring props  

![Screenshot 2024-06-21 at 08 41 24](https://github.com/KarlMeierMattern/Full-Stack/assets/99612323/8074a062-784e-4c21-a78d-3db98807915a)  

### Default values for props  

![Screenshot 2024-06-21 at 08 44 36](https://github.com/KarlMeierMattern/Full-Stack/assets/99612323/2975ed3a-ef36-45d1-9558-3b0839e5205a)  

### Forwarding props  

![Screenshot 2024-07-25 at 08 41 02](https://github.com/user-attachments/assets/86aace6e-15aa-48a5-962e-6cd274d022d0)

### Passing JSX as children  
Sometimes you’ll want to nest your own components. When you nest content inside a JSX tag, the parent component will receive that content in a prop called `children`. For example, the `Card` component below will receive a `children` prop set to `<Avatar />` and render it in a wrapper div:

    export default function Profile() {
      return (
        <Card>
          <Avatar/>
        </Card>
      );
    }
    
    function Card({ children }) {
      return (
        <div className="card">
          {children}
        </div>
      );
    }

> [!TIP]  
> - Note: In React, data flows down the component tree. This is referred to as one-way data flow.  
> - Props are immutable (meaning “unchangeable”).  
> - When a component needs to change its props (e.g. in response to a user interaction or new data), it will have to “ask” its parent component to pass it different props—a new object.  
> - Don’t try to “change props”. When you need to respond to the user input (like changing the selected color), you will need to “set state”.  

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
    // The first set of curly braces represents a new object that we create
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

## Updating arrays in state  
While arrays are mutable in JavaScript, you should treat arrays in React state as read-only.  
When you want to update an array stored in state, you need to create a new one (or make a copy of an existing one), and then set state to use the new array.  

![Screenshot 2024-07-04 at 08 16 17](https://github.com/KarlMeierMattern/Full-Stack/assets/99612323/fb67e2cf-cff1-4908-997c-35a616dfd70e)  

    const [artists, setArtists] = useState([]);
    
    <button onClick={() => {
        setArtists( // Replace the state
            [ // with a new array 
                ...artists, // that contains all the old items
                { id: nextId++, name: name } // and one new item at the end
            ]
        );
    }}>
    </button>

![Screenshot 2024-07-04 at 08 26 22](https://github.com/KarlMeierMattern/Full-Stack/assets/99612323/cffc5486-3360-4687-a766-5d678d8d88ca)  

---

## Reacting to input with state  
You can trigger state updates in response to either:  
1. Human inputs (click button, type in field); or  
2. Computer inputs (timeout completing, network response arriving, image loading).  

![Screenshot 2024-07-07 at 20 06 24](https://github.com/KarlMeierMattern/Full-Stack/assets/99612323/716df071-115d-4815-a487-1d9eec9c716c)  

> [!TIP]  
> - Start with the state that absolutely must be there.  
> - If you struggle to think of the best way immediately, start by adding enough state that you’re definitely sure that all the possible visual states are covered.  
> - Your first idea likely won’t be the best, but that’s ok—refactoring state is a part of the process.  
> - Expressing all interactions as state changes lets you later introduce new visual states without breaking existing ones. It also lets you change what should be displayed in each state without changing the logic of the interaction itself.  

---

### Sharing state between components  
When you want the state of two components to always change together remove state from both of them and move it to their closest common parent, and then pass it down to them via props. This is known as lifting state up.  

> [!IMPORTANT]  
> - Lifting state up often changes the nature of what you’re storing as state.  
> - The common parent component may need to keep track of which child component is the active one. Instead of a boolean value, it could use a number as the index of the active child component for the state variable.  

![Screenshot 2024-07-11 at 08 39 08](https://github.com/KarlMeierMattern/Full-Stack/assets/99612323/25a1b34c-3504-45fa-a4b1-033f38fae9ef)  

For each unique piece of state, you will choose the component that “owns” it. This principle is also known as having a “single source of truth”. It doesn’t mean that all state lives in one place—but that for each piece of state, there is a specific component that holds that piece of information. Instead of duplicating shared state between components, lift it up to their common shared parent, and pass it down to the children that need it. Your app will change as you work on it. It is common that you will move state down or back up while you’re still figuring out where each piece of the state “lives”.  

> [!TIP]  
> - When you want to coordinate two components, move their state to their common parent.  
> - Then pass the information down through props from their common parent.  
> - Finally, pass the event handlers down so that the children can change the parent’s state.  
> - It’s useful to consider components as “controlled” (driven by props) or “uncontrolled” (driven by state).  

---

## Preserving & resetting state  
React keeps state for as long as the same component is rendered at the same position.  
State is not kept in JSX tags. It’s associated with the tree position in which you put that JSX.  
You can force a subtree to reset its state by giving it a different key.  
Don’t nest component definitions, or you’ll reset state by accident.  

As a rule of thumb, if you want to preserve the state between re-renders, the structure of your tree needs to “match up” from one render to another. If the structure is different, the state gets destroyed because React destroys state when it removes a component from the tree.  

    // State gets destroyed as different child components are used between renders
    // Although you render a Counter, the first child of the div changes from a div to a section
    // Changing the <section> component to a <div> component would preserve state between renders
    
    return (
        <div>
            {isFancy 
            ? (<div><Counter isFancy={true} /></div>) 
            : (<section><Counter isFancy={false} /></section>)
            }
        </div>
    )

If you want to distinguish between different states where two components appear in the same place in the UI, there are two ways to reset state when switching between them:  
1. Render components in different positions; and  
2. Give each component an explicit identity with key.  

        // Using a key ensures state is not preserved between renders
        
        return (
            <div>
                {isFancy 
                ? (<div key="component-1"><Counter isFancy={true} /></div>) 
                : (<div key="component-2"><Counter isFancy={false} /></div>)
                }
            </div>
        )

Specifying a key tells React to use the key itself as part of the position, instead of their order within the parent. This is why, even though you render them in the same place in JSX, React sees them as two different counters, and so they will never share state. Every time a counter appears on the screen, its state is created. Every time it is removed, its state is destroyed. N.B. Keys are not globally unique. They only specify the position within the parent.  

> [!IMPORTANT]  
> Redo task 3 in the link: https://react.dev/learn/preserving-and-resetting-state  

---

## Extracting State Logic into a Reducer  
Components with many state updates spread across many event handlers can get overwhelming. For these cases, you can consolidate all the state update logic outside your component in a single function, called a reducer. Component logic can be easier to read when you separate concerns like this. Now the event handlers only specify what happened by dispatching actions, and the reducer function determines how the state updates in response to them.  

Reducers are a different way to handle state. You can migrate from useState to useReducer in three steps:  
1. Move from setting state to dispatching actions.  
2. Write a reducer function.  
3. Use the reducer from your component.  

### Step 1: Move from setting state to dispatching actions  
Managing state with reducers is slightly different from directly setting state. Instead of telling React “what to do” by setting state, you specify “what the user just did” by dispatching “actions” from your event handlers. (The state update logic will live elsewhere!) So instead of “setting tasks” via an event handler, you’re dispatching an “added/changed/deleted a task” action. This is more descriptive of the user’s intent.

    // Using state
    
    function handleAddTask(text) {
      setTasks([
        ...tasks,
        {
          id: nextId++,
          text: text,
          done: false,
        },
      ]);
    }
    
    // Using Reducer
    // The object you pass to dispatch is called an “action”
    
    function handleAddTask(text) {
      dispatch({
        type: 'added',
        id: nextId++,
        text: text,
      });
    }

> [!NOTE]  
> - A Reducer is a regular JavaScript object. You decide what to put in it, but generally it should contain the minimal information about what happened. The dispatch function is added later on.  
> - An action object can have any shape. By convention, it is common to give it a string type that describes what happened, and pass any additional information in other fields. The type is specific to a component, so in this example either 'added' or 'added_task' would be fine. Choose a name that says what happened.  

### Step 2: Write a reducer function  
A reducer function is where you will put your state logic. It takes two arguments, the current state and the action object, and it returns the next state.  
It’s convention to use switch statements inside reducers for readability. Wrapping each case block in curly braces means variables declared inside of different cases don’t clash with each other.  

    function tasksReducer(tasks, action) {
      switch (action.type) {
        case 'added': {
          return [
            ...tasks,
            {
              id: action.id,
              text: action.text,
              done: false,
            },
          ];
        }
        case 'changed': {
          return tasks.map((t) => {
            if (t.id === action.task.id) {
              return action.task;
            } else {
              return t;
            }
          });
        }
        case 'deleted': {
          return tasks.filter((t) => t.id !== action.id);
        }
        default: {
          throw Error('Unknown action: ' + action.type);
        }
      }
    }

### Step 3: Use the reducer from your component  

Finally, you need to hook up the `tasksReducer` to your component. Import the `useReducer` Hook from React:

    import { useReducer } from 'react';

Then you can replace `useState` with `useReducer` like so: 

    const [tasks, dispatch] = useReducer(tasksReducer, initialTasks);

---

## Passing data deeply with context  
Usually, you will pass information from a parent component to a child component via props. But passing props can become verbose and inconvenient if you have to pass them through many components. Context lets the parent component make some information available to any component in the tree below it—no matter how deep—without passing it explicitly through props.  

### To pass context:  
Step 1: Create and export it with export `const MyContext = createContext(defaultValue)`.  
Step 2: Pass it to the `useContext(MyContext)` Hook to read it in any child component, no matter how deep.  
Step 3: Wrap children into `<MyContext.Provider value={...}>` to provide it from a parent.  

### Step 1: create context  
First, you need to create the context. You’ll need to export it from a file so that your components can use it. The only argument to `createContext` is the default value. In this example, 1 refers to the biggest heading level, but you could pass any kind of value (even an object).  

    import { createContext } from 'react';
    
    export const LevelContext = createContext(1);

### Step 2: use the context  
`useContext` is a Hook. Just like `useState` and `useReducer`, you can only call a Hook immediately inside a React component (not inside loops or conditions).  
    
    import { useContext } from 'react';
    import { LevelContext } from './LevelContext.js';

`useContext` tells React that the Heading component wants to read the `LevelContext`.  

    export default function Heading({ children }) {
      const level = useContext(LevelContext);
      // ...
    }

### Step 3: provide the context  
This tells React: “if any component inside this `<Section>` asks for `LevelContext`, give them this level.” The component will use the value of the nearest `<LevelContext.Provider>` in the UI tree above it.  

    import { LevelContext } from './LevelContext.js';
    
    export default function Section({ level, children }) {
      return (
        <section className="section">
          <LevelContext.Provider value={level}>
            {children}
          </LevelContext.Provider>
        </section>
      );
    }

### When to use context  
Just because you need to pass some props several levels deep doesn’t mean you should put that information into context.  

1. Start by passing props. it’s not unusual to pass a dozen props down through a dozen components. It may feel like a slog, but it makes it very clear which components use which data.  
2. Extract components and pass JSX as children to them.  
If neither of these approaches works well for you, consider context.  

### Use cases for context  
In general, if some information is needed by distant components in different parts of the tree, it’s a good indication that context will help you.

1. Theming: If your app lets the user change its appearance (e.g. dark mode), you can put a context provider at the top of your app, and use that context to adjust the visual look.  
2. Current account: Many components might need to know the currently logged in user. Putting it in context makes it convenient to read it anywhere in the tree.  
3. Routing: Most routing solutions use context internally to hold the current route. This is how every link “knows” whether it’s active or not.  
4. Managing state: As your app grows, you might end up with a lot of state closer to the top of your app. Many distant components below may want to change it. It is common to use a reducer together with context to manage complex state and pass it down to distant components without too much hassle.

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

































