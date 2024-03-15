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

		const regex = /[helo]/;
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
		
		fruits.sort((a, b) => {
		  if (a.name < b.name) {
		    return -1;
		  }
		
		  if (a.name > b.name) {
		    return 1;
		  }
		
		  return 0;
		});
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
- JS provides the id and ariaLabel properties for assigning id and aria-label attributes.   

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


































































### Data Types  

JavaScript provides eight different data types which are:  
1. undefined  
2. null  
3. boolean  
4. string  
5. symbol  
6. bigint  
7. number; and  
8. object  

---

### Variables  

    var ourName;  
    ourName = 5;  

> `var ourName` is the variable delcaration  
> `ourName = 5` is the variable assignment  
> In JavaScript we end statements with semicolons  

Variable names can be made up of numbers, letters, and $ or _, but may not contain spaces or start with a number.  

It is common to initialize a variable to an initial value in the same line as it is declared:  

    var myVar = 0;  

---

### let vs var  

One of the problems with declaring variables with the `var` keyword is that you can easily overwrite variable declarations.  
Unlike var, when you use `let`, a variable with the same name can only be declared once.  

    let camper = "James";  
    let camper = "David";  

> The above code will produce an error

### const  

You can also declare variables using the `const` keyword.  
`const` has the same features as `let`, with the added bonus that variables declared using `const` cannot be reassigned.  
You should always name variables you don't want to reassign using the `const` keyword.  
It is best practice to use uppercase variable identifiers for immutable values and lowercase or camelCase for mutable values.  

    const FAV_PET = "Cats";  
    FAV_PET = "Dogs";  

> The above code will produce an error  

---

### Numbers  

    const myVar = 5 + 10;  

> Number is a data type in JavaScript which represents numeric data.  

### Increment/Decrememnt a number  

You can easily increment/decrement a variable (increase/decrease by 1) ++ or -- operators.  

    i++;  
    i--;

> is the equivalent of  

    i = i + 1;  
    i = i - 1;  

---

### Compound assignment with augmented addition/subraction/multiplication/division  

    let myVar = 1;  
    myVar += 5;  
    console.log(myVar);  

> `myVar += 5` is the same as `myVar = myVar + 5`.  
> Similarily you can use `-=`or `*=` or `/=` for subtraction/multiplication/division.  

---

### Literal quotes in strings  

When you need a literal quote inside of a string, you can do the following:

    var myVar = "Karl said \"This is a good idea\" and then left"  

> The output is: *Karl said "This is a good idea" and then left.*  
> Alternatively, you can use single/double quotes for the main string and double/single quotes for the literal quote.  
> With this method you can remove the `\`escape character

    var myVar = 'Karl said "This is a good idea" and then left'  

Where a word contains an apostrophe you can either use an escape character or change the order of the quotations.  

    const badStr = 'Finn responds, "Let's go!"';

> The above code throws out an error as the outermost quotes (single) are used within the quoted sentence (for the apostrophe).  

    const badStr = "Finn responds, 'Let's go!'";  
    const badStr = 'Finn responds, "Let\'s go!"';  

> Either of the two options above will solve the issue.  

---

### Escaping sequences in Strings  

| **Code** | **Output** |  
|---|---|  
|\\'|single quote|  
|\\"|double quote|  
|\n|newline|  
|\t|tab|  
|\r|carriage return|  
|\b|word boundary|  
|\f|form feed|  

> To perform a backslash requires two backslashes `\\`  

---

### Concatenating strings  

Concatenation does not add spaces between concatenated strings, so you'll need to add them yourself.  

    let ourStr = "I come first. ";  
    ourStr += "I come second.";  

> This produces the string `I come first. I come second.` 

---

### Length of a string  

You can find the length of a `String` value by writing `.length` after the string variable or string literal.  

### Bracket notation for indexing  

Similar to Python, JavaScript uses *zero-based* indexing.  

    const firstName = "Charles";  
    const firstLetter = firstName[0];  

> The result would be `C`.  

---

### Understand String Immutability  

In JavaScript, `String` values are *immutable*, which means that they cannot be altered once created.  

    let myStr = "Bob";  
    myStr[0] = "J";  

> The above code produces an error.  

---

### Use Bracket Notation to Find the Last Character in a String  

    const firstName = "Ada";  
    const lastLetter = firstName[firstName.length - 1];  

> The above code produces a result of `a`.  

---

### JavaScript Arrays  

With JavaScript array variables, we can store several pieces of data in one place.  

    const sandwich = ["peanut butter", 4, "bread"];  

---

### Nested arrary  

You can also nest arrays within other arrays.  

    const teams = [["Bulls", 23], ["White Sox", 45]];  

---

### Access Array Data with Indexes  

    const array = [50, 60, 70];  
    console.log(array[0]);  

> The result of the above is `50`.  

---

### Modify Array Data With Indexes  

Unlike strings, the entries of arrays are *mutable* and can be changed freely, even if the array was declared with const.  

    const ourArray = [50, 40, 30];  
    ourArray[0] = 15;  

> The result is `[15,40,30]`.  

---

### Multi-Dimensional Arrays  

    const arr = [  
        [1, 2, 3],  
        [4, 5, 6],  
        [7, 8, 9],  
        [[10, 11, 12], 13, 14]  
    ];  

    arr[3][0][1];  


> The result of the above is `11`.  

---

### Manipulate Arrays with .push()  

An easy way to append data to the end of an array is via the push() function.  

    const arr2 = ["Stimpson", "J", "cat"];  
    arr2.push(["happy", "joy"]);  
    console.log(arr2);

> The result of the above is `["Stimpson", "J", "cat", ["happy", "joy"]]`.  

---

### Manipulate Arrays with .pop()  

.pop() is used to pop a value off of the end of an array.  

    const threeArr = [1, 4, 6];  
    const oneDown = threeArr.pop();  
    console.log(oneDown);  
    console.log(threeArr);  

> The output of `oneDown` is `6`, while `threeArr`is `[1,4]`.  

### Manipulate Arrays with .shift()  

.shift() removes the first element.  

---

### Manipulate Arrays with unshift()  

.unshift() works exactly like .push(), but instead of adding the element at the end of the array, unshift() adds the element at the beginning of the array.  

    const ourArray = ["Stimpson", "J", "cat"];  
    ourArray.shift();  
    ourArray.unshift("Happy");  

> ourArray would have the value `["Happy, "J", "cat]`.  

---

### Write Reusable Code with Functions  

    function functionName() {  
    console.log("Hello World");  
    }  

> You can call the function with `functionName()`.  

---

### Passing Values to Functions  

**Parameters**  
- When a function is defined, it is typically defined along with one or more parameters.  
- Variables that act as placeholders for the values that are to be input to a function when it is called.  

**Arguments**  
- The actual values that are input (or "passed") into a function when it is called.  

    function testFun(param1, param2) {  
    console.log(param1, param2);  
    }  

---

### Using Return  

You can use a return statement to send a value back out of a function.  

    function plusThree(num) {  
    return num + 3;  
    }  

    const answer = plusThree(5);  

> `answer` has the value `8`.  

**Note**: In the case that the function doesn't have a return statement, when you call it, the function processes the inner code but the returned value is undefined.

---

### Global Scope and Functions  

In JavaScript, scope refers to the visibility of variables.   
Variables defined outside of a function block have *Global* scope.  
This means, they can be seen everywhere in your JavaScript code.  

Variables declared without the `let` or `const` keywords are automatically created in the global scope.  
This can create unintended consequences elsewhere in your code or when running a function again.  
Always declare your variables with `let` or `const`.  

---

### Local Scope and Functions  

Variables which are declared within a function, as well as the function parameters, have *local* scope.  
That means they are only visible within that function.  

    function myTest() {  
    const loc = "foo";  
    console.log(loc);  
    }  

    myTest();  
    console.log(loc);  

> The `myTest()` function call will display the string `foo` in the console.  
> The console.log(loc) line will throw an error, as `loc` is not defined outside of the function.  

---

### Global vs Local Scope in Functions  

It is possible to have both local and global variables with the same name.  
When you do this, the local variable takes precedence over the global variable.  

---

### Understanding Boolean Values  

Booleans may only be one of two values: `true` or `false`.  
They are basically little on-off switches, where true is on and false is off.  
These two states are mutually exclusive.  

---

### Conditional Logic with if Statements  

The keyword `if` tells JavaScript to execute the code in the curly braces under certain conditions, defined in the parentheses.  
These conditions are known as `Boolean` conditions and they may only be `true` or `false`.  

When the condition evaluates to `true`, the program executes the statement inside the curly braces.  
When the Boolean condition evaluates to `false`, the statement inside the curly braces will not execute.  

**Pseudocode**:  

    if (condition is true) {  
        statement is executed  
    }  

**Example**:  

    function test (myCondition) {  
        if (myCondition) {  
            return "It was true";  
        }  
        return "It was false";  
    }  

    test(true);  
    test(false);  

> `test(true)` returns the string `It was true`.  
> `test(false)` returns the string `It was false`.  

---

### Comparison with the Equality Operator  

There are many comparison operators in JavaScript. All of these operators return a boolean `true` or `false` value.  

The most basic operator is the equality operator `==`. The equality operator compares two values and returns `true` if they're equivalent or `false` if they are not.  

    function equalityTest(myVal) {  
        if (myVal == 10) {  
            return "Equal";  
        }  
        return "Not Equal";  
    }  

> If `myVal` is equal to `10`, the equality operator returns true, so the code in the curly braces will execute, and the function will return `Equal`.  

**Note**: In order for JavaScript to compare two different data types (for example, `numbers` and `strings`), it must convert one type to another. This is known as *Type Coercion*. Once it does, however, it can compare terms as follows:

    1   ==  1  // true  
    1   ==  2  // false  
    1   == '1' // true  
    "3" ==  3  // true  

---

### Comparison with the Strict Equality Operator  

Strict equality (`===`) is the counterpart to the equality operator (`==`).  
However, unlike the equality operator, which attempts to convert both values being compared to a common type, the strict equality operator does not perform a type conversion.  

    3 ===  3  // true  
    3 === '3' // false  

**Note**: In JavaScript, you can determine the type of a variable or a value with the `typeof` operator, as follows:

    typeof 3  
    typeof '3'    

> `typeof 3` returns the string `number`, and `typeof '3'` returns the string `string`.  

---

### Comparison with the inequality operator  

It means not equal and returns `false` where equality would return `true` and vice versa.  

    1 !=  2    // true  
    1 != "1"   // false  
    1 != '1'   // false  
    1 != true  // false  
    0 != false // false  

---

### Comparison with the Strict inequality Operator  

The strict inequality operator (`!==`) is the logical opposite of the strict equality operator.  
The strict inequality operator will not convert data types.  

---

### Comparison with the Greater/Less Than and Greater/Less Than or Equal to Operators  

The greater/less than (`>`/`<`) and greater/less than or equal to operators (`>=`, `<=`) compare the values of two numbers.  
Like the equality operator, these operators will convert data types of values while comparing.  

---

### Comparison with the Logical And Operator  

