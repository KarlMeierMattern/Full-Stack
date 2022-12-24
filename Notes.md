# JavaScript Notes  

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
|\'|single quote|  
|\\"|double quote|  
|'\\'|backslash|  
|\n|newline|  
|\t|tab|  
|\r|carriage return|  
|\b|word boundary|  
|\f|form feed|  

