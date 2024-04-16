> [!NOTE]
> Useful information that users should know, even when skimming content.

> [!IMPORTANT]
> Key information users need to know to achieve their goal.

> [!WARNING]
> Urgent info that needs immediate user attention to avoid problems.

> [!CAUTION]
> Advises about risks or negative outcomes of certain actions.

# Learn JS by building a role-playing game  
JS is a powerful scripting language that you can use to make web pages interactive. It's one of the core technologies of the web, along with HTML and CSS.  
You'll learn how to work with arrays, strings, objects, functions, loops, if/else statements, and more.  

- You can start writing JS directly in html using a script element.  
- This element is used to load JS into your HTML file. Should be placed just before the closing `</body>` tag.  

		<script src="./script.js"></script>
- The developer console will include errors that are produced by your code, but you can also use it to see values of variables in your code, which is helpful for debugging.  
- A variable is used to hold a value. To use a variable, you must first *declare* it. The `let` keyword tells JavaScript you are declaring a variable.  

		let myAge;
- If you assign a variable while you declare it this is called *initialisation*.  

		let myAge = 32;
- JS interacts with the HTML using the *Document Object Model*, or DOM.  
- The DOM is a tree of objects that represents the HTML. You can access the HTML using the `document` object, which represents your entire HTML document.  
- One method for finding specific elements in your HTML is using the `querySelector()` method, which takes a CSS selector as an argument and returns the first element that matches that selector.  
- Example: create a button1 variable and assign it to the element with id of button1.  

		let button1 = document.querySelector("#button1")
- If you are not going to assign a new value to a variable it is best practice to use the `const` keyword to declare it instead of the `let` keyword. This will tell JavaScript to throw an error if you accidentally reassign it.  

		const myAge = 32;
- In CSS setting `display: none;` will hide the element.  
- Functions are special tools that allow you to run sections of code at specific times. You can declare functions using the `function` keyword.  

		function functionName() {
		}
- Single-line comments can be written with `//` and multi-line comments can be written with `/*` and `*/`.  
- Button elements have a special property called `onclick`, which you can use to determine what happens when someone clicks that button. You can access properties in JS a couple of different ways. The first is with dot notation.  
- Example: when the variable button1 (which is the button with id="button1") is clicked, myFunction will be called.  

		button1.onclick = myFunction;
- The `innerText` property controls the text that appears in an HTML element.  
- Example: change the text of the p element from "Demo" content to "Hello World". Useful when this is preceeded with a button click.  

		<p id="info">Demo content</p>
  
		const info = document.querySelector("#info"); 
		info.innerText = "Hello World";

- To wrap text in double quotes you need to escape the quotes using a backslash. Here is an example:  

		const escapedString = "Naomi likes to play \"Zelda\" sometimes.";
- Functions can take parameters, which are values that are given to the function each time it is run. Here is a function that takes a parameter called param:  

		function myFunction(param) {
		    console.log(param);
		}
- Arrays can store any data type, including objects.  
- Objects are similar to arrays, but with a few differences. One difference is that objects use properties, or keys, to access and modify data. Objects are indicated by curly braces.  
- Object properties are written as key: value pairs, where key is the name of the property (or the key), and value is the value that property holds.  
- Just like array values, object properties are separated by a comma.  
- If a property name has more than one word you'll need to surround it in quotes.  

		const locations = [
		  {
		    name: "town square",
		    "button text": []
		  }
		];
- Zero-based indexing versus dot notation:  

		location["button functions"][2];
		location.text;
- Compound assignment:  

		gold += 10;
- Increasing a value by 1, or incrementing, has a special operator in JavaScript: ++.  

		num++
- Use the push() method to add an object to the end of an array.  

		const arr = ["first"];
		const next = "second";
		arr.push(next);
- Arrays have a length property that returns the number of items in the array.  

		myArray.length
- Scope is the term used to describe where a variable can be accessed. If a variable is declared inside a block of code, like in an if statement, it is only accessible to the code inside that block. This is called block scope.  

		let num = 1;
		if (num === 1) {
		  let num = 2; // this num is scoped to the if statement
		  console.log(num); // expected output: 2
		}
		console.log(num); // expected output: 1 (the global variable)
- The `shift()` method on an array removes the first element in the array and returns it.  

		const numbers = [1, 2, 3];
		const firstNumber = numbers.shift(); // returns 1
- If you have hidden an element in your CSS (`display: none`), you can display the element upon an action being performed (such as a button click) using the `style` and `display` properties. The `style` property is used to access the inline style of an element and the `display` property is used to set the visibility of an element.  

		const paragraph = document.querySelector('p');
		paragraph.style.display = 'block';
- The `Math` object in JavaScript contains static properties and methods for mathematical constants and functions. One of those is `Math.random()`, which generates a random number from 0 (inclusive) to 1 (exclusive). Another is `Math.floor()`, which rounds a given number down to the nearest integer. For example, this generates a random number between 1 and 5:  

		Math.floor(Math.random() * 5) + 1;.
- The strict equality `===` operator checks if the values are equal and if they are the same data type.  

		if (num === 5)
- The `innerHTML` property allows you to access or modify the content inside an HTML element using JavaScript.  
- Functions run specific blocks of code when they are called, but they can also return a value. This value can be assigned to a variable and used elsewhere in your code.  
- The **ternary operator** is a conditional operator and can be used as a one-line if-else statement. The syntax is: condition ? expressionIfTrue : expressionIfFalse.  

		if (num > 5) {
		  return 'num is greater than 5';
		} else {
		  return 'num is smaller than or equal to 5';
		}
  
		// or you can write:
		return num > 5 ? 'num is greater than 5' : 'num is smaller than or equal to 5';
- The logical OR operator `||`.  
- The `pop()` method on an array removes the last element in the array and returns it.  
- The logical AND `&&` operator checks if two statements are true.  
- Not equal `!==`.  

		if (Math.random() <= .1 && inventory.length !== 1)
- A while loop accepts a condition, and will run the code in the block until the condition is no longer true.  

		while (i < 5)
- The new line escape character `\n`.  
- A `for` loop runs for a specific number of times.  
- `for` loops are declared with three expressions separated by semicolons. `for (a; b; c)`, where `a` is the initialization expression, `b` is the condition, and `c` is the final expression.  
- The initialization expression is executed only once, before the loop starts, and is often used to define and set up the loop variable. Think of it like declaring a counter to use in your loop.  
- Many for loops use `i` as the counter and start from 0.  
- The second statement in a `for` loop, the condition statement, is evaluated at the beginning of every loop iteration. The loop will continue as long as the condition evaluates to be true.  
- The last statement in a `for` loop, the final expression, is executed at the end of each loop iteration.  

		for (let i = 0; i < 5; i++) {
  		}
- The `.includes()` method determines if an array contains an element and will return either true or false.  

		const numbersArray = [1, 2, 3, 4, 5]
		const number = 3
		
		if (numbersArray.includes(number)) {
		  console.log("The number is in the array.")
		}

---

# Learn form validation by building a calorie counter  
When building a web application you'll need to be able to accept input from a user.  
You'll learn how to validate user input, perform calculations based on that input, and dynamically update your interface to display the results.  
In this practice project, you'll learn basic regular expressions, template literals, the `addEventListener()` method, and more.  

- Setting the button element type attribute to `button` prevents automatic form submission. This allows for more control over the form submission process to implement custom behaviors as needed. Form submission can then be handled via JS (such as through AJAX).  
- Setting the button element type attribute to `submit` will submit the form.
- To access an HTML element with a given id name, you can use the `getElementById()` method.  

		<h1 id="title">Main title</h1>
		const mainTitleElement = document.getElementById('title');
- In programming, it is standard practice to prefix a variable with `is` or `has` to indicate that the variable is a boolean.  

		let isRunning = true;
		let hasCompleted = false;
- You can use the `split()` method to split a string into an array of substrings. You can pass in an optional separator which tells the method where each split should happen.  

		const str = 'Hello World';
		const strArray = str.split('');
		// ["H", "e", "l", "l", "o", " ", "W", "o", "r", "l", "d"]
- The `.includes()` method returns true if the array contains the character, and false if not. The logical NOT operator `!` will return the opposite of the value of the `.includes()` method.
- Here is an example checking if the current character is not in the vowels array. If it is not, that current character is pushed into the consonantArray:

		const inputString = "Hello World";
		const charArray = inputString.split('');
		const consonantArray = [];
		
		for (let i = 0; i < charArray.length; i++) {
		  if (!['a', 'e', 'i', 'o', 'u'].includes(charArray[i])) {
		    consonantArray.push(charArray[i]);
		  }
		}
- Using Regular Expressions (referred to as "regex") to match specific characters is more inefficient (for memory and runtime performance) than creating a new array by looping through the string.  
- Regex in JavaScript is indicated by a pattern wrapped in forward slashes.  

		const regex = /hello/;
- In regex, shorthand character classes allow you to match specific characters without having to write those characters in your pattern. Shorthand character classes are preceded with a backslash (\). The character class `\s` will match any whitespace character.  
- Your current pattern won't work just yet. `/+-\s/` looks for `+`, `-`, and a space in order. This would match `+- hello` but would not match `+hello`.  
- To tell the pattern to match each of these characters individually, you need to turn them into a character class. This is done by wrapping the characters you want to match in brackets. For example, this pattern will match the characters h, e, l, or o:  

		const regex = /[hello]/;
- Regex can also take specific flags to alter the pattern matching behavior. Flags are added after the closing `/`. The `g` flag, which stands for "global", will tell the pattern to continue looking after it has found a match.  

		const helloRegex = /hello/g;
- Strings have a `.replace()` method which takes two arguments. The first is the character sequence to replace – this can either be a string or a regex pattern. The second is the string to replace that sequence with.  

		"hello".replace(/l/g, "1");
  		// replaces all instances of l with 1
- The regex `i` flag stands for "insensitive" and makes your pattern case-insensitive.  

		const regex = /Hello/i;
		// matches hello, Hello, HELLO, and even hElLo because of the i flag.
- The `+` modifier in a regex allows you to match a pattern that occurs one or more times.
- There is a shorthand character class to match any digit: `\d`. Use this as opposed to the `[0-9]` character class.
- Strings have a `.match()` method, which takes a regex argument and returns an array of match results – containing either the first match, or all matches if the global flag is used.  

		const str = 'example string';
		const regex = /example/;
		const result = str.match(regex);
  		// Returns ['example']
- To query the value from a dropdown you can use the `value` property.  

		// get the id from the select element	
		const entryDropdown = document.getElementById('entry-dropdown');

  		// query the value from the option element
		function addEntry() {
		  const targetId = "#" + entryDropdown.value();
		}
- Template literals allow you to interpolate variables directly within a string and are denoted with backticks `` in JS, as opposed to single or double quotes. You don't need these backticks when using interpolation in HTML. Variables can be passed in to a template literal by surrounding the variable with `${}` – the value of the variable will be inserted into the string.  

		const name = "Naomi";
		const templateLiteral = `Hello, my name is ${name}~!`;
		console.log(templateLiteral);
		// The console will show the string "Hello, my name is Naomi~!".
- To get all of the inputs, you can use the `querySelectorAll()` method, which returns a NodeList of all the elements that match the selector. A NodeList is an array-like object, so you can access the elements using bracket notation.  
- The `innerHTML` property controls the HTML elements that appear on your page.  

		// HTML code
		<form id="form">
		  <label for="first-name">First name</label>
		  <input id="first-name" type="text">
		</form>
  
		// JS code
  		// If you want to add another label and input element inside the form use the innerHTML property
		const formElement = document.getElementById("form");
		const formContent = `
		  <label for="last-name">Last name</label>
		  <input id="last-name" type="text">
		`;
		formElement.innerHTML += formContent;
- Similar to the a button's `onclick` property you can also edit an element's behavior by adding an `addEventListener` method to add a click event to a button. This method takes two arguments. The first is the event to listen to. (Ex. `click`). The second is the callback function that runs when the event is triggered. Note: the function is not called using the `()` but rather the function reference is used. This is because we don't want to exectute the function immediately, but rather call it.  

		// HTML code
		<button class="btn">Print name</button>

  		// JS code
		const button = document.querySelector('.btn');

  		function printName() {
		  console.log("Jessica");
		}

  		button.addEventListener('click', printName);
- Using `innerHTML` alone does not preserve your input content when multiple events take place one after another (such as click events). Using `insertAdjacentHTML()` method takes two arguments. The first argument is a string that specifies the position of the inserted element. The second argument is a string containing the HTML to be inserted. The argument `"beforeend"` inserts the new element as the last child.

		targetInputContainer.insertAdjacentHTML("beforeend", HTMLString).innerHTML;
- A `for/of` loop is used to iterate over elements in an iterable object like an array or NodeList. The variable declared in the loop represents the current element being iterated over.  

		for (const element of elementArray) {
		  console.log(element);
		}
- `for` - loops through a block of code a number of times.  
- `for/of` - loops through the values of an iterable object.  
- In JS values can either be truthy or falsy. A value is truthy if it evaluates to true when converted to a Boolean. A value is falsy if it evaluates to false when converted to a Boolean. null is an example of a falsy value. You can do this by passing the variable directly to your if condition (without a comparison operator). Here's an example of checking the truthiness of helloWorld.  

		if (helloWorld) {
		
		}
- Browsers have a built in `alert()` function, which you can use to display a pop-up message to the user. The message to display is passed as the argument to the alert() function.

		if (invalidInputMatch) {
		      alert(`Invalid Input: ${invalidInputMatch[0]}`);
		    }
- If your `if` statement returns a value, you do not need to explicitly define an else statement.  
- The `Number` constructor is a function that converts a value to a number. If the value cannot be converted, it returns NaN which stands for "Not a Number".

		Number('10'); // returns the number 10
		Number('abc'); // returns NaN
- `getElementById` returns an element. If you want to return a NodeList you can use `[]`. A NodeList is array-like, which means you can iterate through it and it shares some common methods with an array.

		const budgetNumberInput = document.getElementById('budget');
		const budgetCalories = getCaloriesFromInputs([budgetNumberInput]); // square brackets creates a NodeList
- When you need to lower case a string, you can use the `toLowerCase()` method.  

		const firstName = 'JESSICA';
		console.log(firstName.toLowerCase()); // Output: jessica
- `Math.abs()` is a built-in JavaScript method that will return the absolute value of a number.  

		const num = -5;
		Math.abs(num); // 5
- `getElementById` returns an element. This element has a `classList` property, which allows you to access the class associated with the id. This property has `.remove()` and `add()` methods, which accept a string representing the class to remove or add from the element.  

		const paragraphElement = document.getElementById('paragraph');

  		// removes the hide class
		paragraphElement.classList.remove('hide');

  		// adds the hide class
  		paragraphElement.classList.add('hide');
- The difference between `innerText` and `innerHTML` is that `innerText` will not render HTML elements, but will display the tags and content as raw text.

---

# Learn basic string and array methods by building a music player  
Learn some essential string and array methods like the `find()`, `forEach()`, `map()`, and `join()`. These methods are crucial for developing dynamic web applications.  
The project covers fundamental concepts such as handling audio playback, managing a playlist, implementing play, pause, next, previous, and shuffle functionalities. You'll learn how to dynamically update your user interface based on the current song.  

- The spread operator `...` allows you to copy all elements from one array into another. It can also be used to concatenate multiple arrays into one.  
		
		const arr1 = [1, 2, 3];
		const arr2 = [4, 5, 6];

  		// In the example below, both arr1 and arr2 have been spread into combinedArr:
		const combinedArr = [...arr1, ...arr2];
		console.log(combinedArr); // Output: [1, 2, 3, 4, 5, 6]
- An **arrow function** is a shorter and more concise way to write functions in JavaScript. It's a function expression, which is a function that's assigned to a variable.  

		// Here is an example of an arrow function with a single parameter and a single expression in the function body
		const exampleArrowFunction = (param) => {
		  return param
		};

  		// If the function body consists of a single expression, you can omit the curly braces and the return keyword. This is called an implicit return:
		const exampleArrowFunction = (param) => param;
- The `map()` method is used to iterate through an array and return a new array. It's helpful when you want to create a new array based on the values of an existing array.  

		const numbers = [1, 2, 3];
		const doubledNumbers = numbers.map((number) => number * 2);
  		// doubledNumbers will be [2, 4, 6]
- Notice that the `map()` method takes a function as an argument. This is called a **callback function**, which is a function that is passed to another function as an argument.  
- The `join()` method is used to concatenate all the elements of an array into a single string. It takes an optional parameter called a separator which is used to separate each element of the array.  

		const exampleArr = ["This", "is", "a", "sentence"];
		const sentence = exampleArr.join(" "); // Separator takes a space character
		console.log(sentence); // Output: "This is a sentence"

- You can also chain multiple methods together such as `array.map().join()`.  
- **Optional chaining** `?.` helps prevent errors when accessing nested properties that might be null or undefined.  

		const user = {
		  name: "Quincy",
		  address: {
		    city: "San Francisco",
		    state: "CA",
		    country: "USA",
		  },
		};
		
		// Accessing nested properties without optional chaining
		const state = user.address.state; // CA
		
		// Accessing a non-existent nested property with optional chaining
		const zipCode = user.address?.zipCode; // Returns undefined instead of throwing an error
- The `sort()` method converts elements of an array into strings and sorts them in place based on their values in the UTF-16 encoding.  

		const names = ["Tom", "Jessica", "Quincy", "Naomi"];
		names.sort() // ["Jessica", "Naomi", "Quincy", "Tom"]
- In the example  below, the first condition (a.name < b.name) checks if the name of the first fruit is less than the name of the second fruit. If so, the first fruit is sorted before the second fruit. Strings are compared lexicographically which means they are compared character by character. For example, "Apples" is less than "Bananas" because "A" comes before "B" in the alphabet. The reason why this example is returning numbers is because the `sort()` method is expecting a number to be returned. If you return a negative number, the first item is sorted before the second item.
- The `sort()` method accepts a compare callback function that defines the sort order.  

		const fruits = [
		  { name: "Apples", price: 0.99 },
		  { name: "Blueberries", price: 1.49 },
		  { name: "Grapes", price: 2.99 },
		];

		// Version 1
		fruits.sort((a, b) => {
		  if (a.name < b.name) {
		    return -1;
		  }
		
		  if (a.name > b.name) {
		    return 1;
		  }
		
		  return 0;
		});

  		// Version 2 - shortcut to sort an array of numbers
  
  		const numbers = [30,40,20,70,30];
  		numbers.sort((a, b) => {
		  return a - b
  		}	
- The `find()` method retrieves the first element within an array that fulfills the conditions specified in the provided callback function. If no element satisfies the condition, the method returns undefined.  

		const numbers = [10, 20, 30, 40, 50];
		
		// Find the first number greater than 25
		const foundNumber = numbers.find((number) => number > 25);
		console.log(foundNumber); // Output: 30
- The `onclick` property can be added directly to the HTML as well.  
		
		<button onclick="playSong(${song.id})" class="playlist-song-info">
- To get the index of an element in an array you can use the `indexOf()` method, which returns the first index at which a given element can be found in the array, or -1 if the element is not present.  

		const animals = ["dog", "cat", "horse"];
		animals.indexOf("cat") // 1
- The `forEach` method is used to loop through an array and perform a function on each element of the array.  

		const numbers = [1, 2, 3, 4, 5];
		
		// Using forEach to iterate through the array
		numbers.forEach((number) => {
		  console.log(number); // 1, 2, 3, 4, 5
		});
- The `removeAttribute()` method removes an attribute from an element.  

		// Remove the href attribute from an <a> element:
		document.getElementById("myAnchor").removeAttribute("href");
- `textContent` sets the text, similar to `innerText`, of a node and allows you to set or retrieve the text content of an HTML element. 

		<div id="example">This is some text content</div>
  
		const element = document.getElementById('example');
		console.log(element.textContent);
  		// Output: This is some text content
- The `setAttribute()` method adds an attribute to an element. The second argument sets the value of the specified attribute for the element.  

		playButton.setAttribute("aria-label", "Play");
- The `sort()` method is a type of callback function, which can also be used to randomize an array. One way to do this is to subtract 0.5 from `Math.random()` which produces random values that are either positive or negative. This makes the comparison result a mix of positive and negative values, leading to a random ordering of elements.  

		const names = ["Tom", "Jessica", "Quincy", "Naomi"];
		names.sort(() => Math.random() - 0.5);
- The `filter()` method keeps only the elements of an array that satisfy the callback function passed to it.  

		const numArr = [1, 10, 8, 3, 4, 5]
		const numsGreaterThanThree = numArr.filter((num) => num > 3);
		
		console.log(numsGreaterThanThree) // Output: [10, 8, 4, 5]
- The `createElement()` is a DOM method you can use to dynamically create an element using JS. To use `createElement()`, you call it, then pass in the tag name as a string.

		const divElement = document.createElement('div')
- The `createTextNode()` method is used to create a text node. To use it, you call it and pass in the text as a string.

		const myText = document.createTextNode("your text")
- JS provides the `id`, `ariaLabel`, and `className` properties for assigning id, aria-label, and class name attributes.   

		document.createElement("button").id = "reset";
		document.createElement("button").ariaLabel = "Reset playlist";
- `appendChild()` lets you add a node or an element as the child of another element. In the example below, the text "Click me" would be attached to the button:  

		const parentElement = document.createElement("button")
		const parentElementText = document.createTextNode("Click me")

		// attach the text "Click me" to the button
		parentElement.appendChild(parentElementText)
- Use `remove()` to remove an element completely.  

		const resetButton = document.createElement("button");
		resetButton.remove();

---

# Learn the date object by building a date formatter  
Learn how to work with the JS Date object, including its methods and properties.  
Cover concepts such as the `getDate()`, `getMonth()`, and `getFullYear()` methods.  

- In JS built-in **constructors** are like regular functions but start with a capital letter and initialized with the `new` operator in order to create objects.  
- For example, you can use the `Date()` constructor with the `new` operator to create a new `Date` object that returns a string with the current date and time.  

		const currentDate = new Date();
		console.log(currentDate);
		
		// Mon Aug 23 2021 15:31:00 GMT-0400 (Eastern Daylight Time)
- The .getDate() method of the `Date` object returns a number between 1 and 31 that represents the day of the month for that date.  

		const date = new Date();
		const dayOfTheMonth = date.getDate();
		console.log(dayOfTheMonth); // 20
- The `.getMonth()` method of the `Date` object returns a number between 0 and 11. You need to add 1 to it to get the expected month number.  
- The `.getFullYear()` method of the `Date` object returns a number which represents the year for the provided date.  
- The `.getHours()` method of the `Date` object returns a number between 0 and 23. This represents the hour for the provided date, where 0 is midnight and 23 is 11 p.m.  
- The `.getMinutes()` method of the `Date` object returns a number between 0 and 59 which represents the minutes for the provided date.  
- In JavaScript, the change event is used to detect when the value of an HTML element has changed:

		element.addEventListener("change", () => {
  		});
- A `switch` statement is used to compare an expression against multiple possible values and execute different code blocks based on the match. If your `switch` statement is going to have multiple cases it is best practice to include a `break` statement that tells the JS interpreter to stop executing statements. Without adding a `break` statement at the end of each case block the program will execute the code for all matching cases. The `default` case is executed when none of the previous case conditions match the value being evaluated. It serves as a catch-all for any other possible cases.  

		// checks if someVariable='case123'
		switch (someVariable) {
		  case 'case123':
		    // Write your logic here
		    break; // Terminates the switch statement
		default:
		    console.log("It's the weekend!");
		}
- The `.reverse()` method is used to reverse an array in place.  

		const array = [1, 2, 3, 4, 5];
		array.reverse();
		console.log(array); // [5, 4, 3, 2, 1]
- The `.join()` method is used to join the reversed array elements into a string and use a "-" for the separator.

---

# Learn modern JS methods by building football team cards  
Learn how to work with DOM manipulation, object destructuring, event handling, and data filtering.  
This project will cover concepts like `switch` statements, default parameters, `Object.freeze()`, and the `map()` method.  

- The method `Object.freeze(obj)` allows you to freeze an object and prevent any changes being made to it.

> [!TIP]
> An alternative to dot notation is the object destructuring syntax that allows you to unpack values from arrays and objects.  

		const developerObj = {
		  name: "Jessica Wilkins",
		  isDeveloper: true
		};

		// dot notation
  		const name = developerObj.name;
  		const isDeveloper = developerObj.isDeveloper;
  
		// Object destructuring
		const { name, isDeveloper } = developerObj;
- Function parameters can be initialized with default values. If a function is called without an argument, then the default value will be used.  

		const greeting = (arr = "Anonymous") => {
		  return "Hello " + arr;
		} 

		console.log(greeting("John")); // Hello John
		console.log(greeting()); // Hello Anonymous
- `map()` function using dot notation and destructuring. The `.map()` method returns a new array of items separated by commas. To remove the commas between items so it does not show up on screen, chain the `.join()` method to the `.map()` method and pass an empty string as the argument.  

		players: [
		    {
		      name: "Sergio Almirón",
		      position: "forward",
		    },
		    {
		      name: "Sergio Batista",
		      position: "midfielder",
		    }
  		];

		// assume this was an element in your HTML
		const roster = document.getElementById("player-list");

  		// map function & dot notation
  		const renderPlayer = (players) => {
  			const eachPlayer = players.map((player) => {
				return `
  					<p>${player.name}</p>
  					<p>${player.position}</p>
  				`;
  			}).join("");
  			roster.innerHTML = eachPlayer;
  		};

		// map function V1 & destructuring
  		const renderPlayers = (players) => {
  			const eachPlayer = players.map(( {name, position } ) => {
  				return `
  					<p>${name}</p>
  					<p>${position}</p>
  				`;
  			}).join("");
  			roster.innerHTML = eachPlayer;
  		};

		// map function V2 & destructuring
		const renderPlayers = (arr=players) => {
  			roster.innerHTML += arr.map(({ name, position }) => (
				`<p>${name}</p>
  				<p>${position}</p>
  				`
  			).join("");
  		};

		// both functions would produce the same result
		renderPlayer(players);
		renderPlayers(players);
- `e.target.value` represents the value property from the playersDropdownList element. `e` represents an object which contains the information for that event.   

		playersDropdownList.addEventListener("change", (e) => {
		  playerCards.innerHTML = "";
		
		  switch (e.target.value) {
		    case "nickname":
			setPlayerCards(players.filter((player) => player.nickname !== null)); //filters the players array where nicknames are not null
		      	break;
		    case "forward":
		      	setPlayerCards(players.filter((player) => player.position === "forward"));
		      	break;
		    default:
		      	setPlayerCards();

# Learn localStorage by building a ToDo app  
Local storage is a web browser feature that lets web applications store key-value pairs persistently within a user's browser.  
This allows web apps to save data during one session, then retrieve it in a later page session.  
Learn how to handle form inputs, manage local storage, perform CRUD (Create, Read, Update, Delete) operations on tasks, implement event listeners, and toggle UI elements.  

- Similar to adding and removing classes using `el.classList.add()` and `el.classList.remove()` another method to use with the `classList` property is the `toggle`, which adds the class if it is not present on the element and removes the class if it is present on the element.  

		element.classList.toggle("class-to-toggle");
- The HTML `<dialog>` element has a `showModal()` method that can be used to display a modal dialog box on a web page.  

		dialogElement.showModal();
- The HTML `<dialog>` element has a `close()` method that can be used to close a modal dialog box on a web page.  

		dialogElement.close();
- `preventDefault()` method stops the browser from refreshing the page after submitting the form.  
- The `findIndex()` array method finds and returns the index of the first element in an array that meets the criteria specified by a provided testing function. If no such element is found, the method returns -1.  

		const numbers = [3, 1, 5, 6];
		const firstNumLargerThanThree = numbers.findIndex((num) => num > 3);
		
		console.log(firstNumLargerThanThree); // prints index 2
- `unshift()` is an array method that is used to add one or more elements to the beginning of an array.  
- `forEach()` vs `map()` can be used to produce the same output:  

		// element from HTML
		const tasksContainer = document.getElementById("tasks-container");

		// some array
		const taskData = [
			{
				title: "Day1",
				date: 11.01.2024,
				description: "Shopping"
		  	}
		];

		// using forEach
		taskData.forEach(({ title, date, description }) => {
			tasksContainer.innerHTML += `
				<p>${title}</p>
		   		<p>${date}</p>
			 	<p>${description}</p>
		  	`
		})

		// using map V1
		tasksContainer.innerHTML += taskData.map(({ title, date, description }) =>
			`
			 	<p>${title}</p>
			   	<p>${date}</p>
				<p>${description}</p>
		  	`
		).join("");

		// using map V2
		const myContainer = taskData.map(({ title, date, description }) =>
			`
				<p>${title}</p>
			   	<p>${date}</p>
				<p>${description}</p>
		  	`
		).join("");
		tasksContainer.innerHTML += myContainer
- To find the id of a parent element you can use `parentElement`. `this` is a keyword that refers to the current context. In this case, `this` points to the element that triggers the event – the buttons.  

		<div class="task" id="${id}">
		  <button onclick="deleteTask(this)" type="button" class="btn">Delete</button>
		</div>
		
		const deleteTask = (buttonEl) => {
		 const dataArrIndex = taskData.findIndex((item) => item.id === buttonEl.parentElement.id);
		}
- `splice()` is an array method that modifies arrays by removing, replacing, or adding elements at a specified index, while also returning the removed elements. It can take up to three arguments: the first one is the mandatory index at which to start, the second is the number of items to remove, and the third is an optional replacement element.  

		const fruits = ["mango", "date", "cherry", "banana", "apple"];
		
		// Remove date and cherry from the array starting at index 1
		const removedFruits = fruits.splice(1, 2);
		
		console.log(fruits); // [ 'mango', 'banana', 'apple' ]
		console.log(removedFruits); // [ 'date', 'cherry' ]
- `localStorage` offers methods for saving, retrieving, and deleting items. The items you save can be of any JavaScript data type. The `setItem()` method is used to save an item, and the `getItem()` method retrieves the item. To delete a specific item, you can utilize the `removeItem()` method, or if you want to delete all items in the storage, you can use `clear()`. Everything you save in `localStorage` needs to be in string format. To do this wrap the data you're saving in the `JSON.stringify()` method. When you retrieve the item using `getItem()` it will be a string. To view it in its original form before saving, you need to use `JSON.parse()`.  

		const myTaskArr = [
		  { task: "Walk the Dog", date: "22-04-2022" },
		  { task: "Read some books", date: "02-11-2023" },
		];
		
		localStorage.setItem("data", JSON.stringify(myTaskArr));
		
		const getTaskArrObj = JSON.parse(localStorage.getItem('data'));
		console.log(getTaskArrObj);
- You can use `localStorage.removeItem()` to remove a specific item and `localStorage.clear()` to clear all items in the local storage.

# Learn recursion by building a decimal to binary converter  
Recursion is a programming concept where a function calls itself. This can reduce a complex problem into simpler sub-problems, until they become straightforward to solve.  
Learn the fundamental concepts of recursion, explore the call stack, and build out a visual representation of the recursion process through an animation.  

- The `keydown` event fires every time a user presses a key on their keyboard, and is a good way to add more interactivity to input elements.
- Remember that `e` is a common parameter name for the **event object**. Whenever an event listener is triggered by an event, an event object is created automatically. You don't always need to use this object, but it can be useful to access information about the event that was triggered.  
- `key` is one of the properties of event objects. It represents the string value of the key that was pressed.  

		numberInput.addEventListener("keydown", (e) => {
		  if (e.key === "Enter") {
		    checkUserInput();
		  }
		});

- A good way to check and normalize numbers is to use `parseInt()`, which converts a string into an integer or whole number. It takes a string to be converted into an integer, and returns either an integer or NaN.  

		parseInt(2.2); // 2
		parseInt("2e+3"); // 2
		parseInt("e") // NaN
- The `isNaN()` function takes in a string or number as an argument, and returns true if it evaluates to NaN.  

		isNaN("test"); // true
		isNaN(2); // false
		isNaN("3.5"); // false
- Binary numbers are a base-2 number system. These binary digits are called bits, and are the smallest unit of data computers can process. For computers, 0 represents false or "off", and 1 represents true or "on". Binary numbers can be long sequences that start with 0, so they are often represented as strings.  
- Because bits are often grouped into bytes, it's common to see binary numbers represented in groups of eight, sometimes with leading zeros. For example, the number 52 can be represented as 110100, or 00110100 with leading zeros.
- A byte can represent any number between 0 and 255. Here are the placement values for each bit in a byte:
`128 | 64 | 32 | 16 | 8 | 4 | 2 | 1`
- A while loop is used to run a block of code as long as the condition evaluates to true, and the condition is checked before the code block is executed.  

		let i = 0;
		
		while (i < 5) {
		  console.log(i);
		  i++;
		}
- The remainder operator `%` returns the remainder of the division of two numbers.  

		const remainder = 5 % 2; // 1
- A stack is a data structure where items are stored in a LIFO (last-in-first-out) manner. The call stack is a collection of function calls stored in a stack structure. When you call a function, it is added to the top or of the stack, and when it returns, it is removed from the top / end of the stack.  
- A **recursive function** is a function that calls itself over and over. The base case is when the function stops calling itself.  
- Recursive functions also have a **recursive case**, which is where the function calls itself.  

		// Version 1
		const countdown = (number) => {
		  console.log(number);
		
		  if (number === 0) {
		    return;
		  } else {
		    countdown(number - 1);
		  }
		};

		countdown(3)
  		//output 3,2,1,0
- The output sequence 1, 2, 3 at the end of Version 2 below occurs because the function is recursively calling itself and printing the numbers in ascending order as it returns from each recursive call. When a recursive function unwinds it starts returning from the deepest call back to the original call. In this case, after the base case is reached, the function starts returning from countDownAndUp(0) back to the original call countDownAndUp(3).  

		// Version 2
		const countDownAndUp = (number) => {
		  console.log(number);
		
		  if (number === 0) {
		    console.log("Reached base case");
		    return;
		  } else {
		    countDownAndUp(number - 1);
		    console.log(number);
		  }
		};
		
		countDownAndUp(3);
  		// output 3,2,1,0,Reached base case,1,2,3
- The `setTimeout` function takes two arguments: a callback function and a number representing the time in milliseconds to wait before executing the callback function. `setTimeout()`  is asynchronous, meaning that it doesn't stop the execution of the rest of your code.  

		setTimeout(() => {
		  console.log("Hello, world!");
		}, 3000);

---

# Learn basic algorithmic thinking by building a number sorter  
In computer science, there are fundamental numerical sorting algorithms that all developers should learn including bubble sort, selection sort, and insertion sort.  

- Buttons associated with a form element submit by default. To prevent that behavior you can use `.preventDefault()` on your event listener object.  
- Use `document.getElementsByClassName("class-name")` to access an element by its class. Remember that `.getElementsByClassName()` returns a NodeList, which is an array-like object. The **spread operator** `...` spreads the elements out and the `[]` places them into a new array. `forEach` is used to iterate over the array.  

		const inputValues = [...document.getElementsByClassName("class")];
		
		inputValues.forEach((element) => {
		    // Do something with 'element'
		});
- A **fallback value** is a default value assigned to a variable or parameter in case no other value is provided. This helps prevent errors or unexpected behavior in code that relies on the presence of a certain value.  

		const updateUI = (array = []) => {
		
		};
- The **bubble sort** algorithm starts at the beginning of the array and 'bubbles up' unsorted values towards the end, iterating through the array until it is completely sorted.  
- Bubble sort can stop one element before the end of the array in the inner loop because the largest elements are bubbled up towards the end after each pass.  

		const bubbleSort = (array) => {
		  for (let i = 0; i < array.length; i++) { // iterates over the array
		    for (let j = 0; j < array.length - 1; j++) { // performs one pass through of the array to compare adjacent elements		
		      if (array[j] > array[j + 1]) {
		        const temp = array[j];
		        array[j] = array[j + 1];
		        array[j + 1] = temp;
		      }
		    }
		  }
		  return array;
		}
- The **selection sort** algorithm works by finding the smallest value in the array, then swapping it with the first value in the array. Then, it finds the next smallest value in the array, and swaps it with the second value in the array. It continues iterating through the array until it is completely sorted.
- Selection sort needs to consider all elements in the unsorted portion of the array during each pass to find the smallest unsorted element, hence it iterates until the last element.  
  
		const selectionSort = (array) => {
		  for (let i = 0; i < array.length; i++) {
		    let minIndex = i;
		    for (let j = i + 1; j < array.length; j++) {
		      if (array[j] < array[minIndex]) {
		        minIndex = j;
		      }
		    }
		    const temp = array[i];
		    array[i] = array[minIndex];
		    array[minIndex] = temp;
		  }		
		  return array;
		}
- The **insertion sort** algorithm works by building up a sorted array at the beginning of the list. It begins the sorted array with the first element. Then it inspects the next element and swaps it backward into the sorted array until it is in a sorted position, and so on. An insertion sort algorithm starts the sort at the beginning of the list, meaning the first element is already sorted.  

		const insertionSort = (array) => {
		  for (let i = 1; i < array.length; i++) {
		    const currValue = array[i];
		    let j = i - 1;
		
		    while (j >= 0 && array[j] > currValue) {
		      console.log(array, array[i], array[j], array[currValue])
		      array[j + 1] = array[j];
		      j--;
		    }
		    array[j + 1] = currValue;
		    console.log(array[j+1])
		  }
		  return array;
		}
- The built-in method `.sort()` can be used to replace bubble sort, selection sort, and insertion sort.

---

# Learn advanced array methods by building a statistics calculator  
Array manipulation methods, such as map(), reduce(), and filter().  
Handling user input, DOM manipulation, and method chaining.  
Perform statistical calculations like mean, median, mode, variance, and standard deviation.  

- The value of an input element is always a string, even if the input type is `number`.  
- The `.map()` method, which can only be used on an array, takes a callback function as its first argument. You can use it to convert a string to a number using the `Number()` constructor.  

		const value = document.querySelector("#numbers").value;
		const array = value.split(/,\s*/g);
		const numbers = array.map((el) => Number(el));
- The `Number()` constructor will return NaN if the value passed to it cannot be converted to a number.
- The `isNaN()` method returns true if the argument is NaN.
- **Method chaining** involves combining multiple methods together at once.  

		const numbers = array.map(el => Number(el)).filter(el => !isNaN(el));
- The arry method `.reduce()` takes an array and applies a callback function to condense the array into a single value. The callback takes at least two parameters - an accumulator and the current element in the array. The return value for the callback becomes the value of the accumulator on the next iteration. The `.reduce()` method takes a second argument that is used as the initial value of the accumulator.  

		const getMean = (array) => {
		  const sum = array.reduce((acc, el) => acc + el, 0);
		}
- By default the `.sort()` method converts the elements of an array into strings, then sorts them alphabetically. This works well for strings, but not so well for numbers. For example, 10 comes before 2 when sorted as strings, but 2 comes before 10 when sorted as numbers. To fix this, you can pass in a callback function to the `.sort()` method. The function should return a value less than 0 if the first element should come before the second element, a value greater than 0 if the first element should come after the second element, and 0 if the two elements should remain in their current positions.  

		fruits.sort((a, b) => {
		  return a - b
		}
- A `Set` is a data structure that only allows unique values. If you pass an array into the `Set` constructor, it will remove any duplicate values.

		const counts = { '2': 1, '4': 2, '5': 1 };
		if (new Set(Object.values(counts)).size === 1) {
		    return null;
		}
  		// Object.values(counts) returns [1, 2, 1]
  		// new Set(Object.values(counts)) produces [1,2]
  		// new Set(Object.values(counts)).size produces [2]
  		// condition evaluates to false since there are different values
- The `Math` object has a `.min()` and `.max()` method. Any array passed to these methods must must be accompanied by a **spread operator** as these methods expect individual arguments, not an array. By using the spread operator, you're essentially "spreading" the elements of the array into individual arguments. This allows `Math.max()` and `Math.min()` to correctly identify the maximum and minimum values within the array.  

		const numbersArr = [2, 3, 1];
		
		console.log(Math.min(...numbersArr));
		// Expected output: 1
- To calculate a root exponent such as the square root, you can use the `Math.pow()` function.  

		const standardDeviation = Math.pow(variance,1/2); // square root
- The `Math` object has a `.sqrt()` method specifically for finding the square root of a number.  

		const standardDeviation = Math.sqrt(variance); // square root
- The `.sort()` method modifies the array it is called on in place. To fix this, you can chain an empty `.slice()` call before your `.sort()` method, which will make a shallow copy of the array, which you are free to mutate.  

		const sorted = array.slice().sort((a, b) => a - b);
		// array.slice() creates a shallow copy of the array. Then .sort() method is called on this copy.
		// original array remains unchanged

# Learn functional programming by building a spreadsheet  
In Functional Programming code is organised into smaller functions, which are then combined to build complex programs.  
Learn about parsing and evaluating mathematical expressions, implementing spreadsheet functions, handling cell references, and creating interactive web interfaces.  
You'll learn how to dynamically update the page based on user input.  
This project will cover concepts like the `map()` method, `find()` method, `parseInt()`, the `includes()` method.  

- The global `window` object represents the browser window (or tab). It has an `onload` property which allows you to define behavior when the window has loaded the entire page, including stylesheets and scripts.
- When a function itself needs to reuse logic you can declare a nested function to handle that logic.  

		const outer = () => {
		  const inner = () => {
		
		  };
		};
- The `Array()` constructor has a `.fill()` method which can be used to fill an array with a value.
- Instead of using the `setAttribute` method another way to update an attribute in JavaScript is to use the syntax `el.attribute = value;`. The property names for hyphenated HTML attribute values, such as `aria-label`, follow camel case, becoming `ariaLabel`.  

		element.setAttribute("aria-label", "Play");
  		// or
		element.ariaLabel = "Play";
- An example of efficient programming using implicit return.  

		// Version 1
		const isEven = num => num % 2 === 0;
		
		// Version 2
		const isEven = (num) => {
		  if (num % 2 === 0) {
		    return true;
		  }
		  else {
		    return false;
		  }
		};
- `Math.ceil()` is used to round up.  
















