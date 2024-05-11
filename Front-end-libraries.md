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
React is a JavaScript library (consisting of APIs) for building interactive user interfaces.  
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

# Next.js  
React framework that gives you building blocks to create fully interactive, highly dynamic, and performant web applications.  
By framework, we mean Next.js handles the tooling and configuration needed for React, and provides additional structure, features, and optimizations for your application to solve common application requirements such as routing, data fetching, and caching.  

- When a user visits a web page, the server returns an HTML file to the browser.  
- The browser reads the HTML and constructs the Document Object Model (DOM).  
- The DOM is an object representation of the HTML elements.  
- It acts as a bridge between your code and the user interface, and has a tree-like structure with parent and child relationships.

## Imperative vs. declarative programming  
Imperative programming is writing the steps for how the user interface should be updated.  
Declarative programming you declare what they want to show instead of having to write DOM methods.  
React is a popular declarative library that you can use build user interfaces.  

## Syntax  
react is the core React library:  
<code><script src="https://unpkg.com/react@18/umd/react.development.js"></script></code>  

react-dom provides DOM-specific methods that enable you to use React with the DOM:  
<code><script src="https://unpkg.com/react@18/umd/react.development.js"></script></code>  

Browsers don't understand JSX out of the box, so you'll need a JavaScript compiler, such as a Babel, to transform your JSX code into regular JavaScript:  
<code><script src="https://unpkg.com/@babel/standalone/babel.min.js"></script></code>  

    // Imperative
    <html>
      <body>
        <div id="app"></div>
        
        <script src="https://unpkg.com/react-dom@18/umd/react-dom.development.js"></script>
        <script type="text/javascript">
          const app = document.getElementById('app');
          const header = document.createElement('h1');
          const text = 'Develop. Preview. Ship.';
          const headerContent = document.createTextNode(text);
          header.appendChild(headerContent);
          app.appendChild(header);
        </script>
      </body>
    </html>

    // Declarative
    <html>
      <body>
        <div id="app"></div>
        <script src="https://unpkg.com/react@18/umd/react.development.js"></script>
        <script src="https://unpkg.com/react-dom@18/umd/react-dom.development.js"></script>
       
        <!--Inform Babel what code to transform by changing the script type to type=text/jsx.-->
        <script type="text/jsx">
          const domNode = document.getElementById('app');
          const root = ReactDOM.createRoot(domNode);
          root.render(<h1>Develop. Preview. Ship.</h1>);
        </script>
      </body>
    </html>

## JSX  
JSX is a syntax extension for JavaScript that allows you to describe your UI in a familiar HTML-like syntax.  
But browsers don't understand JSX out of the box, so you'll need a JavaScript compiler, such as a Babel, to transform your JSX code into regular JavaScript.  















