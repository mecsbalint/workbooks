# Programming Basics questions

## Data Basics✔

- What are the differences between objects, arrays, and primitives in JavaScript? How are they used in programming?✔

    : Objects and arrays are reference data types (along with functions) and list types, which means they can hold multiple other data which can be primitives or list types too (more on reference type see below). Primitive data types can hold only one unit and one type of data at once. For example a primitive variable can hold one number or one string but not multiple, while an array can hold a list of various data types (numbers, strings, booleans etc).
    So the primitive type variables are used for storing singular data while the objects and arrays are used for group somehow connected data elements together.

- How would you access the value of a specific key in an object?✔

    : The most common way to acces the value is typing the object's name, a dot notation and the specific key's name e.g. objectName.keyName. If you want to add the key name by a variable like a function's parameter or in a for...in loop you have to use square bracket notation instead. If the key contains at least one space you have to use quotemarks along with square brackets e.g. objectName["key with spaces"].

- Explain the concept of key-value pairs in objects and how they differ from indexed elements in arrays.✔

    : The value-key pair of an object is called a property. The object is a list type variable in JavaScript hence it can hold multiple values which are reacheble through their key. Technically it looks similar to the array's index-value pair, however there are significant differences. The key itself can be any string, while the index of an array element is always a sequential number assigned to the value automatically. A key of an object can be named which name can be descriptive about what kind of data belongs to it. For example a "name" key indicates the value of this property is the name of the entity which the object represents.
    Technically the main differenc is that the object's values aren't iterable, hence for...of loop cannot use with an object (but a for...in loop will iterate through the object's keys).

- Describe a scenario where you would choose to use an object instead of an array, or vice versa, and explain your reasoning.✔

    : Using list types means we try to abstract a part of reality and transform it into a form which is understandable and can be handled by the programming language, and the grouping of values by them is for this very purpose. Usually an abstraction of a being require using both arrays and objects.
    Objects are for data which are different in their nature (not in a programming sense but in reality) but belongs to the same being, hence in a sense the object represent this being. For example an object has a name, an age and an occupation key with values - this means the object is an abstraction of a person who has different properties. Here we should use object for this because with the named keys it's more clear and easy to reach the various data about the person.
    Arrays on the other hand, are for data which are similar in their nature but not necessarily belongs to the same being, or at least the array doesn't want to represent that being (unlike the object). For example we want to abstract and use data about not one person but a group of people, then we can list their one similar property in an array (e.g. their names) and make an array from them. With an array we can easily iterate over the list of data if necessarily. It also can be handy if the position of the data can hold important information, for example if we want to store the results of a sport championship, and the position in the array reflect the position in the championship.
    There are more practical parts of these principles like the differences of methods of arrays and objects or that array can be more easily filled with new data by the program itself and more easily be iterated over. However I think they are consequences of said principles and the fact the Javascript language was built along them.

- How can you retrieve the first and last items of an array?✔

    : Retrieving of the first element of an array is pretty straightforward, it can be refered by the number 0 in square brackets after the array's name e.g. arrayName[0].
    The last item is a bit trickier since the index of it depends on the number of the items the array holds. The go to solution for it is using the square brackets with the length method (you should substrack 1 from it since the indexing of the array items starts with 0). For example arrayName[arrayName.length - 1]
    If you doesn't want to modify the original array's last item but only read its value then you can use the at method with a -1 argument like arrayName.at(-1).
    Technically pop method can  return the last element of an array and shift method does the same with the first one, however these methods also cut them from the original array. Although, with these methods you can also replace them so in a sense you can use the items of the og array (not a technical sense though).

- Identify the five most commonly used primitive types in JavaScript, and provide examples demonstrating when and how to use them?✔
    : `String`: a string of characters, we use it to store any kind of information from someone's name to modifiers of functions. For example to store someone's occupation in a variable I would use string.
    `Number`: it's a bit self explanatory, it is for hold any information which can be expressed as numbers. In JavaScript there is only one type of number value (except BigInt). I would use it to store how many books someone has or in what index of an array someone's occupation's name is.
    `Boolean`: it can be `true` or `false`, it is for storing the answer of a question which can be answered one of these statements. I would use it if I wanted to store a state of the current run of the code, for example if a number variable's value became below zero then the isVarNegative variable should be `false`.
    `null`: it is to represent a variable's lack of value on purpose. If an information doesn't exist or can't be interpreted I will add the `null` value to it, which means it has "no value" but it is a known condition.
    `undefined`: it represents a variable's lack of value, but not on purpose. Every variable's value is `undefined` by default but when a variable is used by the code it's value must not be `undefined`. So it is to show someone is missing or miscalculated in the code therefore I wouldn't assign this type to any variable. However, sometimes it's handy to check (with the help of the `typeof` operator) if a variable's value is still undefined.


## Algorithm Basics✔

- Provide examples of assignment operators in JavaScript.✔

    : Assignment operators are to assign a value to a variable.
    `=` simple assignment operator, it assign the value on the right to the variable on the left
    `+=` addition ass. op. it adds the value on the right to the value of the variable on the left
    `-=` substraction ass. op. does the same as addition ass. op. but with substraction
    `*=` multiplication ass. op. multiply the variable's value on the left with the value on the right
    `/=` division ass. op. same but with division
    `%=` remainder ass. op. assign the remainder of the division of the value on the right from the variable's value on the left to the variable 
    `**=` exponentiation ass. op. does the same as multiplication ass. op. but exponentiation instead of multiplication

- Name some of the arithmetic operators in JavaScript.✔

    : `+` addition
    `-` substraction
    `*` multiplication
    `/` division
    `%` modulus/remainder (give the remain of a division)
    `++` increment (add 1 to the value on the left)
    `--` decrement (substract 1 from the value on the left)
    `**` exponentiation

- What are the different comparison operators in JavaScript?✔

    : `===` strictly equal to - it returns true if the two value are equal in value and in type
    `!==` not strictly equal to - it returns true if the two value is different in value or in type
    `>` - it returns true if the value on the left is greater than the value on the right
    `>=` - it returns true if the value on the left is greater or equal to the value on the right
    `<` - it returns true if the value on the left is lesser than the value on the right
    `<=` - it returns true if the value on the left is lesser or equal to the value on the right
    (`==` and `!=` - equal to and not equal to comparison operators, they work similar to their strict counterparts but doesn't take into account the type of the values. The use of these is not recommended.)


- Name a few logical operators used in JavaScript.✔

    : `&&` and operator - returns true if both of the values are true
    `||` or operator - returns true if any of the values is true
    `!` not operator - returns the inverse of the boolean value (true -> fales and false -> true)

- Explain the differences between a `for` loop, `for of` loop, and `for in` loop in JavaScript.✔

    : `for` is one of the most basic and most versatile type of loops if not the most handy to use. It has three expressions:
    1. is executed one time before the first iteration (it is used to declare an index variable and assign value to it).
    2. defines the condition for excecuting a code block
    3. is executed every time after the code block executed
    `for` loop is used for any kind of loops if the number of iteration can be seen at the start of the loop. However, there are other, more specialized loops or methods and for their use case it is recommended to use them instead of the `for` loop.
    : `for...of` is a loop which loops through the values of an iterable object. It's most commonly used on arrays and strings, and it can't be used on objects. In its expression we declare a variable to which the value of the current property of the iterable will be assigned before every iteration and name the iterable object itself. The syntax is for (const/let/var variable of iterable).
    : `for...in` is similar to the `for...of` loop but it loops through an enumerable properties of an object. In practice this means in every iteration the variable declared in its expression will get the current key of the object. It is used to loop through an object and reach its properties. The syntax of it is the same as the `for...of` loop but with an 'in' instead of 'of'

- If you can't use any built-in functions or methods, how would you calculate the average of values in an array?✔

    : I would declare a variable with the let command and assign the value 0 to it. Then I would make a `for...of` loop where the iterable would be the array, and in every iteration I would add the value of the current element to the variable. After the loop I would divide the variable's value with the number of elements of the array (getting it by the `.length` method) and assign the result to the variable.


## Function Basics✔

- What is a function in JavaScript? Explain its purpose and how it is used in programming.✔

    : The function is a block of code made to perform a task. It is only executed when it is called, not when it is defined, but it can be called many times. The function can have parameters which are variables declared when the function is called and values assigned them which is added the call as arguments. These variables' scope is the function's body. Basically the function is to reuse a block of code with potencially different values or variables.
    In programming the functions are the fundamental building blocks of any code. They are used to create blocks which can be combined and structured into a bigger body, the code which reach the goal of the program. The functions are cardinal for the clean code, because they separate tasks from each other and because with the parameters we can name variables by their local functionalities. It is also cardinal to avoid the code repetition which would make the code less readable and useable otherwise. Normally every part of a code is in a function's body, and the code is executed not by the order of the lines but how the functions are called.

- Describe the different syntax elements that make up a JavaScript function.✔

    : The parts of a function can be separated two part, the definition and the call.
    1. The definition of a function is consist the command `function` optionally the function's name (it can be assigned to a variable or executed in place when it isn't necessarily to name thee function), the parameters (also optional) between parentheses, and the function's body between curly braces, which usually contains a return command. So it looks like this: function functionName(parameter1, parameter2, ... parameterN){
        code which is executed when and where the function is called
        return value which is returned to the place of the calling
    }
    2. The call of the function, which is consist the function's name (or the variable's name which the function have been assigned to) and the parentheses, with the arguments between them.

- How do you pass arguments to a function? Explain the concept of parameter passing and provide an example.✔
    
    : During the call of a function you can add arguments inside the parentheses (the arguments must be separated by commas). When the function is executed it's parameters will get the values which were added the call as arguments by the order they were added to the call. So the first argument will assigned to the first parameter etc. If there are less arguments than parameters the remaining parameters' value will remain `undefined`. During a definition of a function a you can assign a default value which the parameter will get during a call if there is no argument provided.
    : Example: function substrack (num1, num2 = 2){
        return num1 - num2;
    }
    add(5, 1); -> return 5 - 1 -> 4 Here the two parameters got the two arguments as value by order, and the function return the result
    add(5); -> return 5 - 2 -> 3 Here the first parameter got the first and only argument as value, and the second one got it's default value since there was no second argument provided during this call.
    add(); -> return `undefined` - 2 -> `NaN` Here the first parameter didn't get value from an argument nor it has a default value, so it remained `undefined` and the code was executed with these variables resulting a `NaN`

- What is the difference between function expressions and function declarations? Provide examples of each.✔

    : In function declaration we use the `function` keyword followed by a name for the funtion and the parentheses (possibly with parameters between them). With this mode we named the function and can call it by its name + parentheses. For example: 
    function add(num1, num2){
        return num1 + num2;
    }
    add(1, 2);
    In function expression we make an anonymous function by simply skip the name. As a consequence we must assign this function to a variable to make it callable (Node won't even let we not assign it as it would stop with a syntax error). This function will be called by the variable name + parentheses. For example:
    const add = function(num1, num2){
        return num1 + num2;
    }
    add(1, 2);
    It is imporant to note that the arrow mode to make a function only can be used as an expression.

- Explain what a callback function is in JavaScript.✔

    : A callback function is a function which is added as argument to an other function. It can be named, unnamed or declared by arrows. The callback function can be defined in the call of the other function (as a lot of built-in method work e.g .map() or .sort() methods). It is important that you shouldn't add the function's name with parentheses because it would call the function during the call of the other function and the argument won't be the function itself but its return value.

- What is the scope of variables in JavaScript functions? Explain the difference between local and global variables.✔

    : A variable declared in a function can be read only inside the `{}` block, since it has local scope, therefore a variable as such is a local variable. We call global variables which are declared outside of any `{}` block, so they are reachable from anywhere in the code.
    It is important to note that a variable declared in a block are reachable everywhere in the block, even in other functions which were called inside the former function. So the variables are reachable from inside, but unreachable from outside.
    Also, this is true only to the variables declared with the `let` and `const` keywords. The `var` keyword works different.


## Built-in Features✔

- What are some commonly used built-in functions or methods in JavaScript for working with strings? Provide examples and explain their usage.✔

    : `str.split()` - creates an array from a string's parts which are separated by the string given as argument. For example if a string is a normal english sentence and the split's argument is " " (a space) then the new array's elements will be the words of the sentence.
    `str.slice()` - create a new slice from the part of the string which was determined by indexes given as arguments. You can add only one index as arguments and it will return the substring starting with it then. If you add two indexes as arguments then the substring will stop at the second index. The indexes can be negative numbers, then they are counted from the last character of string backward (so -1 point to the very last character of the string).
    `str.toUpperCase()`/`.toLowerCase()` - change all letters  in the string to lower case or upper case. Non letters characters and letters which are already in the method's case aren't affected.
    `str.length` - returns the length of the string as a number, it is very useful in various instnces.
    `str.indexOf()` - search a character's position in a string and returns it as an index number. The character is given as the first argument, and a second (optional) argument can set the starting position of the search. If there are multiple occurence of the character the method will return the first one's index.

- Name at least five built-in functions or methods in JavaScript for manipulating arrays. Describe how each function/method works and provide an example for each.✔

    : `arr.sort(callback function)` - reorder the original array based on the callback function's return value. The function has to have two parameters, one for an element of the array and one for the very next element of it. If the callback's return value smaller or equal of 0 then the order of the two element remains the same; if it's bigger than 0 the order is inverted. If there is no callback function given as argument the elements will be ordered by their unicode number (basically it will be an alphabetical order).
    `arr.push()` and `arr.unshift()` - these methods add one or more extra elements to an array, the former to the end of it and the latter to the start of it. The arguments of them are the elements which will be added to the array. They return the new length of the array
    `arr.pop()` and `arr.shift()` - these methods take out an element from the array and return that element. The .pop takes out the last and the .shift the first element of the array. They have no parameters.
    `arr.map(callback function)` - this method iterates over an array's elements and return with a new array which elements are the callback function's return value. The function's parameters can be the current element, the index of said element and the og. array.
    `arr.filter(callback function)` - it also iterates over the array's elements and return a new one, but the new array's elements here are the og. array's unmodified elements where the callback function's return value is true.

- How can you use built-in functions or methods in JavaScript to perform mathematical operations? Give examples of commonly used functions or methods for mathematical calculations.✔

    : You can use the Math object properties as buil-in functions to perform operations which are a bit more complicated the mathematical operators can provide. Here are some examples:
    `Math.min()/Math.max()` - return the biggest or smallest number of the set of numbers given as arguments
    `Math.abs()` - returns the absolute value of a number given as argument
    `Math.random()` - returns a pseudo-random number between 0 and 1 (inclusive to 0)
    `Math.floor()/Math.ceil()` - return the rounded down or rounded up integer value of a number given as argument
    `Math.round()` - return the rounded integer value of a number given as argument

- What are some built-in functions or methods in JavaScript for manipulating numbers? Describe their functionality and give examples of how they can be used.✔

    : `Number()` - create a number value transformed from the value given as argument
    `parseInt()` - create an integer number from the value given as argument
    `parseFloat()` - create floating point number from the value given as argument
    `num.toString()` create a string from a number. The optional argument is the base which is used to represent the number's value.
    `isNaN()` - return a boolean based on the value given as argument is a NaN or not.
    `isFinite()` - return a boolean based on the value given as argument is a finite number.

- Discuss the differences between `for` loops and the `forEach` method in JavaScript.✔

    : The forEach() is a method which do a very similar job as the for loops (especially the for...of loop). However, there are differences.
    1. forEach() is a method which works only with arrays while the for...of loop can be used with any iterable variable (maps, strings etc)
    2. for...of loop is faster than .forEach() (I read it on the internet so it must be true)
    3. With for...of keywords like break, continue or return can be used while a .forEach() method's run can't be stopped like that (forEach doesn't have a return value).
    4. As a method the .forEach() can be chained other methods together in one line which can be useful in some instances (e.g. the .forEach() can be a function call's argument).
    5. The .forEach()'s callback function can have three parameters similar to .map() and .filter(): the current element, the current element's index and the og. array. With for...of we can use the current element and the array quite easily but it lacks the index; the for loop has an index (when we use to iterate through an array) but not as easily to write down as for...of or .forEach(). In conclusion, the .forEach() method is the optimal choice when we want to use the index of the current element during the iterations.


## File Basics✔

- What distinguishes JavaScript data structures from JSON data structures?✔

    : JavaScript is a programming language with its own data structure which is made to used by only the JavaScript itself. The JSON (JavaScript Object Notation) is a data format made to store and transport data, and it is language-agnostic, not necessarily can be used only by JavaScript. Typically it is used to transfer data from server. It is delivered from JavaScript but independent from it.
    JSON can store 6 type of data:
    1. Object
    2. Array
    3. String
    4. Number
    5. Null
    6. Boolean
    Basically a JSON data can hold structures with key-value pairs and lists (and any combination of them).
    The JSON data structure can only hold text, it cannot store any kind of code. Also the JSON data is presented as one string, which is a huge difference from the JS object. These attributes make possible the JSON to be independent from any programming language.

- How would you create a JavaScript data structure from the data in a JSON file?✔

    : There are two necessarily steps to create the JavaScript data from a JSON file:
    1. Read the file. We can do it in a synchronous way. For this we need to import the `fs module` with the line `import * as fs from "node:fs";`. After it we can use the `fs.readFileSync()` method which has to argument: the relative or absolute reach of the file and the encoding type, both as string. We can save it to a variable or use it as an argument for step 2. It is omportant to note that the data read from the file will be one string.
    2. Parsing JSON file (converting it to a JS object). We can do this most easily by the `JSON.parse()` which convert the JSON data into an object. The parameter of this method is the raw JSON data in the form of a string.
    We can merge these two steps by calling the `fs.readFileSync()` method as an argument for the `JSON.parse()` method.


## View Basics✔

- Explain the difference between JavaScript object data structure and DOM data structure.✔

    : DOM (Document Object Model) is a hierarchical representation of a HTML (or XML) document. It's hierarchical like the HTML tree itself, but it consists not html elements but DOM data structures which can be dinamically manipulated and accessed by a programming language e.g. JavaScript (DOM itself is language-agnostic so it could be another language). So basically DOM is an interface which with the JS can use html, a lingua franca understanded by both side. This data structure which represent one element of the html document (e.g. a div element) seems similar to a JavaScript object but it's different from it. It differs in what we can use to manipulate it or how to access it (see below). For example, to remove a DOM object we need to use the .remove() method, to add value to a property's existing value we use the .add() method. However, there are similarities, like the assignment operators work to declare a DOM object's property's value.
    In summary the objects we work in JavaScript when manipulate an html document are JavaScript representations of the DOM element/interface which is connected somehow to the html element. But the methods and properties of these objects is the interface hence the DOM itself.

- What are the necessary steps to change the content of an HTML element using JavaScript?✔

    : The first step is get the HTML element so we can manipulate it. It can be achieved by the `document.getElementById()` or the `document.querySelector()` method. The former needs the html element's id as a string while the latter needs a css selector. There are other methods which get one or more html element as Dom data (like `document.getElementsByClass()` or `document.querySelectorAll()`). It is recommended to add these methods return value to variables.
    After this step we can manipulate the html element. If we are speaking about strictly the user-visibly content of the element (e.g. a text in a paragraph element) we can change it by changing the innerHtml or the innerText property of the html element. We can add a whole new html element as a child with the .appendChild() method or insert a string with html syntax with the `.insertAdjacentHtml()` method, but this isn't recommended.
    If we are speaking about modifying the html element in general we can use its properties for it. For example, to modify the id, add a new class or modify anything about the element we can do it syntactically the same way as modifying a JS object's property.


## Event Basics✔

- Define an event listener in JavaScript.✔

    : Events are a method to make your code reactable to changes, esepcially user inputs. To use them there is the event listener which is ordered to a DOM element (hence the html element it represents). You can add an event listener to an element in JavaScript with the `.addEventListener()` method or by declaring the element's property (e.g. the onclick property) (this isn't recommended). An event listener has a DOM object it belongs to and two non-optional parameters. The first is for deciding what type of event should it listen for (e.g. click or input), the second one a callback function which will be called upon the event (so this is the response of it). The callback function will get an argument which is the event object, which is an object hold the information the particularities of the event itself (e.g. where exatly it happened).
    In summary an event listener is a function which wait for an event to happen in its scope (the parent DOM object) and activate upon it by call its callback function.

- Outline the steps involved in changing the content of an HTML element when it is clicked.

    : First you need to set up an event listener with the `.addEventListener()` method which will add an event listener to the html element. You can add to the element directly which you want to react the click, but it's more handy to add it to the whole document or at least a bigger part of it (like the <body>). This method has two mandatory parameter, the first is set the type of the event which trigger the listener, and the second is the event handler which was called upon the event happens. In this event handler you can choose the element which was clicked (see below) and modify it as you wish (see above how to modify an html element).

- Inside a `click` event listener, how can you access the element that was clicked?✔

    : The event listener's event handler (the callback function) get an argument which is the event object. One of this event object's properties is target, which is the html element on which the event's action (e.g. a click) has happened. So with the event.target property the element which was clicked is accessable.
    The wvwnt.currentTarget property is the element which has the event listener (so the element on you used the `.addEventListener()` method), so it can also work if you set up the eventlistener directly to the element you want to react upon a lcick on. Bu if you have more than one element like this it can be worky.


## Design Basics✔

- What are the differences between `display: block`, `display: inline`, and `display: inline-block` in CSS? When would you use each display declaration, and how do they affect the layout and behavior of elements?✔

    : `Display` is one of the CSS declarations, and the html tags has a default value of it which is either `block` (div, p, headings, form, ul, ol etc) or `inline` (span, img, a, strong, em etc). The differences between them are the following:
        1. `block` takes up the whole with its parent's and there is a line break after it, while `inline` doesn't.
        2. `block` has padding, border and margin declarations while `inline` only has border and padding.
        3. `block` can have `inline` and `block` children while `inline` can have only `inline`
        4. `block` is displayed as block-level box while `inline` as inline-level box
    The `inline-block` is a blend of the two: 
        1. it can have width and height and the top/bottom margins and paddings are respected
        2. it doesn't add a line break after itself
    Using `block` is recommended when One needs a rectangular space to display the content, or more spaces below each other for contents. Or when One needs to set a width and/or height or margin declaration.
    `Inline` is recommended when One wants to use the style for a short span of text.
    `Inline-block` is recommended when One wants to display block-like elements next to each other. E.g. images next to each other, or list items horizontally (for navigation link for example).

- Explain the distinctions between `position: relative` and `position: absolute` CSS declarations.✔

    : The `position` declaration determines how other positioning declaration values will be applied in the style (like top, bottom, left, right). The `relative` value set that the positioning values will be applied relative to its default position (which is the position it occuppies without any other setting). The `absolute` value means the positioning values will be applied relative to the element's nearest positioned ancestor's position.

- What is the box model? Name the CSS properties associated with it.✔

    : The box model is a concept which contains the values which determines how an html element as a rectangular box is displayed. It has the following properties:
    1. `width` and `height` which set up the dimensions of the box
    2. `border` which determines the visible attributes of the box' border
    3. `padding` which determines the space between the border and the box' content
    4. `margin` which determines the space between the box and the surrounding elements (only `block` display type has it)

- Identify the CSS properties that affect font and text appearance.✔

    : In the CSS the declarations known as typographic features determine the text's appearance. They are the following: `font-family`, `font-size`, `line-height`, `font-weight`, `font-style`, `text-decoration`, `text-align`. Also, the `color` declaration determines what any content's, including texts' color is.

- List the steps for adding or removing a class name from an HTML element.✔

    : First we need to reach the html element via the DOM structure (see above), then we can modify it's classList property. We can do it with one of the assignment operator but there are dedicated methods, like `remove()`, `add()` and `toggle()`. The `toggle()` is esepcially useful since with it an html element's appearance can be toggled by events like clicks. By modifiing the DOM object's classList property the corrsponding html element's class name will also being modified.


## JavaScript - Language Specialties✔

- Elaborate on the differences between value and reference data types in JavaScript, specifically in relation to objects and primitives.✔

    : While value data types (or primitives) represent (or hold) a value, reference data types represent a memory reference to a value or data structure like an object or array. The main practical difference between them is how they behave during an assignment. When a variable with value data type is assigned to another variable this means that its value is assigned to the new variable not the variable itself. It means that a new memory part will be created with the very same value and the new variable will be a 'link' to it not the original memory part. In short, the two variables will behave independently of each other after the assignment, and modifying one doesn't modify the other.
    The reference types, on the other hand, will pass the reference of the memory part instead of its value during an assignment. This means that if we assign a reference data type variable to another variable both will refer the very same memory part, so modifying one will modify 'the other' since they are the very same value but on another 'name'.

- Discuss the concept of mutability and immutability in objects, arrays, and primitives, and explain why it is important to understand when working with data structures in JavaScript.✔

    : In JavaScript primitives are immutable data types while arrays, objects and functions are mutables. A mutable variable's value can be changed after it was created, an immutable variable's cannot. So a mutable variable can be changed regardless of with what keyword (`let` or `const`) we created it.
    When we modify an immutable variable (e.g. we add another string of characters to a string variable) technically we don't modify the original value but create a new one and assign it to the variable. That's why any modification cannot happen on a primitive type variable which was declared by `const`.

- Is `null` considered an object or a primitive in JavaScript?✔

    : `null` is one of the seven primitive data types of JavaScript.

- "What does `undefined` represent in JavaScript?"✔

    : `Undefined` is the default value for every variable which had been declared but hasn't assigned a value to it. So it is represent a lack of value which isn't lacking on purpose (unlike in the case of null). Undefined means it shuld have a value but it doesn't have. For example because we call an object's undeclared property or a declared property which doesn't have an assigned value by accident. In most cases coses which works with other data types doesn't behave normally (or run into an error) when one of the elements are `undefined`. Even the equal comparison operator can't be used to find out if a variable's value `undefined` (for this you should use the `typeof` operator).

- When would you use `var`, `let`, and `const` in JavaScript?✔

    : `var` can have global or function scope: if it's declared outside a function it can be used anywhere. It allows reassignment and redeclaration. It is hoisted to the top of its scope but without its assignment (so with its o.g. `undefined` value), so using the variable before its declaration is possible (although I can't see much practical sense of it).
    `let` can have global, local or block scope: if it's declared in a body ({}) it cannot be used outside of it. It allows reassignment but disallows redeclaration. It hoisted the top of its scope like the var but not only without its assigned value but without initialization so using a variable of this kind before it's declaration will result an error.
    `const` can have global, local or block scope. It cannot be redeclared or reassigned. In regards of hoisting it behaves like `let`.
    `var` is considered a legacy keyword since `let` and `const` was introduced in 2015 and such a thing it isn't recommended to use at all in new codes but it is handy to know how it works because legacy reasons. `const` is recommended everytime when a variable won't be reassigned and `let` must be used when it will be reassigned.
 
- Explain the concept of hoisting in JavaScript.✔

    : Hoisting is when the interpreter before run the code moves the declarations of functions, variables and imports to the top of their scope, so they can be used (sort of) before they were declared in the code. But the different data types behave differently in this regard. `functions` are hoisted with their value ('value hoisting') so they can be used as though they were declared and defined at the very start of their scope. `var` variables are hoisted without their assignment so they can be used but their value will be `undefined` before their assignment. `let` and `const` variables are hoisted without their assignment and their initialization, so they cannot be used until the line they are declared - this means there is no practical impact (at least none of I know) of the hoisting of these two variables.


## Git✔

- Discuss the advantages of using a version control system.✔

    : There are several advantages of a version control system (VCS) like Git:
    1. When multiple programmer are working on the same code (which is more common than not) there will be conflicting advancements of which resolves can be tricky and complicated, and a VCS can help it with automatization if possible or with a platform for resolving if it's not.
    2. It is also useful for data survivability reasons: a VCS can manage the different backups of the code
    3. A VCS can also keep and handle older versions of the code which makes it possible to roll back to an older version of it
    4. A VCS also helps to create and manage different versions (branches) of the same code and helps to merge them again when it's necessary.

- Clarify the differences between Git and GitHub.✔

    : Git is a distributed version control system which is for manage a non-linear workflow of a team of programmers. Github is a Git repository hosting service. So Git is a software, Github is a service for using this software, and Github provides the central version of a repository/code.

- What is the purpose of remote repositories in Git?✔

    : A remote repository is a version of the file/project which is stored not locally but somewhere reachable all the project members (like on a web server or a server on the local network). There is no working happen on a remote repository but only synchronisation between the remote and a local repository. The main purpose of a remote repository is the local/remote workflow. This means the local repositories doesn't interacting each other directly but only through the remote reppository, so merges and merge conflict will happen between a local and the remote repositories. This also means the current common version of the project is always reachable by all team members.

- When does a merge conflict occur in Git?✔

    : Merge with Git means merging two branches into one. Likely they have competing commits (so they differ in content of code) but usually the Git can solve it automatically (especially when the changes are in different units of code or even in different files). When Git cannot merge it by itself that's what we call merge conflict and it has to be solved by manually (by accepting the changes one-byone).


## Terminal✔

- How would you execute a JavaScript file in the terminal?✔

    : By type the command `node` and the JavaScript file's name with its extension e.g. node script.js
    (You can circulate throught the exsisting filenames inside the current directory by pressing Tab)

- What is the keyboard shortcut to stop a running process in the terminal?✔

    : Ctrl + c

- How can you retrieve the previous command executed in the terminal?✔

    : By pressing Up Arrow key you can circulate through the formerly excecuted commands by descending order

- How do you navigate to the parent directory of the current directory in the terminal?✔

    : By using the `cd` command with option `..`
    (Alternatively you can use the `cd` command and type the absolute path of the parent directory)


## Debugging✔

- What techniques can you use while debugging a program?✔

    : There are several techniques we can use for debugging:
    1. The rubber duck: when a bug occurs sometimes it's surprisingly effective to explain your code (and your problem) to someone even if it's a mere toy. By explaining it you also think through it and you find out what was the structural problem with your code which cuased the bug.
    2. Backtracking: for debugging maybe the most foundamental tool is to think through what your code should do and what does it do instead step-by-step, and the counterpart of this is doing the same but backward from the problem which occured.
    3. console.log(): This isn't really recommended but we all use it anyway. When a bug occurs sometimes all we need (or what we think we need) is to make one variable visible to find out what is the problem. This is basically a simple and very limited version of using a dedicated debugging tool.
    4. Use a dedicated debugger tool: with a dedicated tool you can go through the running of your code step-by-step while you can see all the variables and other information of your code. You can use the step over, step in, step out commands and place break points at certain lines of your code (see below) (when run the JavaScript code from a debugger it will pause when reach a break point ). You can use the debugger in the VS code or the browser's built-in debugger.

- What does step over, step into and step out mean while using the debugger?✔

    : `Step over`: the debugger executes the next command in code and jump to the next one.
    `Step into`: the debugger starts to execute the next command step-by-step, so a function, method or loop won't be executed at once but by only one step at a time.
    `Step out`: while inside a local scope the step out command will execute the remaining of the code in said scope and jump to the next step.

- How can you start to debug a program from a certain line using the debugger?✔

    : By placing a break point at the line in VS Code, so the debugging run will stop at the beggining of that line. Alternatively you can write into the code the keyword `debugger` which will have the same effect as the break point.
