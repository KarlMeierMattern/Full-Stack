# Learn JS by building a role-playing game  
You can start writing JS directly in html using a script element.  
This element is used to load JS into your HTML file. Should be placed just before the closing `</body>` tag.  

		  <script src="./script.js"></script>
The developer console will include errors that are produced by your code, but you can also use it to see values of variables in your code, which is helpful for debugging.
A variable is used to hold a value. To use a variable, you must first *declare* it. The `let` keyword tells JavaScript you are declaring a variable.  

        let myAge;
- If you assign a variable while you declare it this is called *initialisation*.

        let myAge = 32;
- JS interacts with the HTML using the *Document Object Model*, or DOM.
- The DOM is a tree of objects that represents the HTML. You can access the HTML using the document object, which represents your entire HTML document.
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
- 






## BASIC JAVASCRIPT  

### Comments

Use // for inline comments    
Use /* for multiline comments */  

---

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

