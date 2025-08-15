# Web Module Questions

## Modern JS✔

- What is ECMAScript? What is the difference between Javascript & ECMAScript?
    
    : While JavaScript is a programming language, ECMAScript is a standardization to this language. ECMAScript has a lot of functionality which makes writing clean code in JS easier (Const/let, for...of/in loops, arrow fnctions, spread operator, destructuring etc.). Nowadays ECMAScript is the go to way to write code in JS.

- Explain the concept of "block scoping" introduced in ES6. How does it differ from function scoping?
    
    : Block scoping (which is used by variables declared with let or const) means a variable can be used only inside the code block where it's created, and this is true for every block. The function scoping works similar but only true to the functions' scopes not all blocks.

- What are template literals in ES6 and how do they improve string manipulation in JavaScript?

    : Template literals are literals marked by the \`. It can be used to easily combine multiple strings without the `+` or the concate method. It also can have expressions which are JS codes returning a string (for example a variable whose value can be used as a string) - the syntax for these expressions is `${}`. The template literals also can be spreaded through multiple lines in the code, a line break doesn't stop them.

- Explain the concept of "destructuring assignment" in ES6. How does it simplify variable assignment and object/array manipulation.

    : Destructuring assignment is basically a shortcut to assign multiple values from an array or object to different variables. With it creating multiple variable from an object/array at fast is much more easier. The syntax for it is the following:
        1. for arrays: `[] = array` - here the new variables named inside the `[]` will get the values corresponding to their position in the array
        2. for objects: `{} = object` - here the new variables named inside the `{}` will get the values corresponding to the names of the properties of the og object. So the names of the new variables has to be the same as the keys of the properties.

- What is the "spread operator" in ES6 and how can it be used to manipulate arrays and objects more effectively?

    : The spread operator (`...`) spreads or expands an iterable variable (such as a string or array) or an object into its elements. This operator can be used in three instances:
     1. function arguments: it is useful when a function is waiting a series of values instead of one array
     2. Array literals: when creating an array we can spread an existing itrable into it (it is especially useful to create a shallow copy of an existing array).
     3. Object literals: this is the only use case when an object can be spreaded (iterables can be used in all three instances). In this case the object's properties will be expands into the new object, making it easy to create a shallow copy of the existing object. When an iterable is spreaded into a new array the expanded elements' values will be the properties' values and the index numbers will be the keys (when multiple iterables are spreaded into a new object then the latters will overwrite the former ones).

- How does ES6 introduce the concept of "default function parameters"? Provide an example of using default parameters in a function.

    : With this feature we can add a default value to a function's parameter which means the said parameter will get this value if the function call doesn't give it one. It is useful for create default settings and instances for a function and make it useable if one or more arguments are missing. For example: `function add(num1, num2 = 1){return num1 + num2}` - here if we call the function with only one argument the `num2` parameter will get its default value which is 1. 

- Explain the concept of "modules" introduced in ES6. How do they improve code organization and reusability in JavaScript?
    
    : Since ES6 the JS code can be modular which means the modules of the code exist in different places (files) and they can be used together because they can be exported and imported between files. functions, objects, classes and primitives are also can be exported/imported. There are named exports and default exports, the difference is that the named exports has to be imported under the very name of them while the default exports can be imported under any name. However, the named exports can be imported with aliases so in practice can be used under any name after that. With these modules code parts can be reused in multiple files for multiple codes and a project doesn't has to hold everything in one JS file.

- Compare the CommonJS and ES6 "modules". What are the differences?

    : There are five main differences between the two modules (if I am correct the CommonJS ones aren't considered modules but this is not clear):
    1. While ES6 `import` is asynchronous the CommonJS `require` is synchronous, so the former doesn't block execution until it is loaded
    2. ES6 is static and it has to be decided what will be exported/imported during compile time. The CommonJS is dynamic so it can require different modules according to the runtime's state
    3. ES6 `import`/`export` has to be top-level (global scope) while the CommonJS doesn't have this restriction
    4. ES6 isn't natively supported (although it is widely used), CommonJS is
    5. In ES6 the imports are live read-only forms of the exported values which means they can change during the runtime if the exported value is changed (this is a one way thing however). CommonJS isn't live, the exported values don't change if they are modified in place

- What are higher-order functions in JavaScript?

    : We call a function higher order function if it get a function as argument or it returns a function. Commonly used methods which are higher order functions: map(), reduce(), sort(), filter(), forEach(), some() and every(). By creating functions which accept other functions as arguments we can create highly customizable functions which are great for code reusability and modularity.

- Explain the purpose and functionality of the map function in JavaScript. How does it differ from the filter and reduce functions?

    : map() method iterates over it's array and call its callbackFn over every element, and create a new array with the return values of these callings. While filter() and reduce() not necessarily create an array with the same length as the original the map() method do exactly this. It is great to modify every element in an array or create an array of the original array's elements's property. Meanwhile filter() method is for create a filtered version of the array, and reduce() is for accumulate values.

- How can the filter function be used to selectively extract elements from an array based on a given condition? Provide an example where the filter function is used to create a new array with only the elements that meet the specified criteria.

    : The filter() method call its callbackFn on every elements of the array and check these callings return value. If it's truthy it keeps for the newly created array (which is the return value of the method itself).
    For example: `[1, 2, 3].filter((element) => element >= 2)` - in this case the filter's return value is `[2, 3]` because only during the second and third iteration was the callbackFn's return value truthy.

- What is the role of the reduce function in JavaScript? How can it be used to aggregate or combine the elements of an array into a single value? Provide an example where the reduce function is used to calculate a cumulative sum or find the maximum value in an array.

    : reduce() method is for accumulate or combine elements in an array which are prevalent throughout the array itself (e.g. a property of the elements). Its callbackFn has a special parameter which holds the result of the former iterations' results. For example: `[23, 4, 12].reduce((acc, element) => acc + element)` - this will return the number 39 because in every iteration the current element's value is added to the cumulative value of the former iterations.


## Fetch✔

- How does a query string parameter in a URL contribute to web application functionality? Explain how query string parameters are typically used to pass data between web pages or APIs.

    : Query string parameter is a convenience way to pass information to the server about the webpage's current state and the details of the request. It can be used to send multiple parameters to the server with in any combination. It is tipycally used for requests to get a specific part of the data (e.g. there is a request for the results of a user searching with filters) or to pass API keys to the server.

- What is the purpose and functionality of the fetch function in JavaScript?

    : The Fetch APi is an interface to making HTTP requests and processing the responses. Fetch() function creates a request and receive the response of it. In the fetch() function's parameters all parts of the request can be set up (url, method, headers, body), and the return value of it is a Promise. This function is the foundation of client-server communication in JS (?).

- Explain the syntax of the fetch function and how it handles asynchronous operations. Compare and contrast the syntax of making HTTP requests using fetch with async/await versus the syntax using .then() and .catch(). What are the key differences and benefits of using the async/await syntax in terms of code structure and readability?

    : fetch() returns a Promise of which result is the response to the request, so to use this response we need to add some asynchronicity to this. There are two method/syntax to do this:
    1. async/await syntax: we can set a function to become asynchronous with the `async` keyword and inside a function like this the `await` keyword will halt the run of the code until the line where the `await` is isn't finished. For error handling we can use Try/catch.
    2. .then/.catch syntax: we can string together multiple then() and catch() methods. The callback function of the then() method will executed only after the synchronous code is finished it was stringed. The catch method is for error handling.
    The async/await syntax is considered more readable, maintainable and overall better for clean code because it looks more similar to the synchronous code syntaxes, and with the try/catch both synchronous and asychronous errors can be handled.

- What is asynchronicity in JavaScript? Name some typical use cases when asynchronicity is needed.

    : Most programming language is synchronous by , which means the code is executed line by line, element by element without any paralell action. But many of them, including JavaScript can handle asynchronous code as well with the correct syntax. This enables the program to remain responsive while a task is running. In JavaScript maybe the most important use of asynchronicity is making http requests which could have a long runtime depending on for example the network state. Another use case of it when we want some code to be executed not at once but a bit later. Or the state setter function in React which is async (or async-like?) for performance reasons.

- How can you handle the response received from a fetch request?

    : To reach a response's body it is necessary to make the code to wait for the fetch to finish its task, because it returns a Promise. There are two method for this, the async/await and the .then/.catch (see above). With one of these methods we can use the body of the response which holds important information depending the nature of the request and the server.

- How does the fetch function handle errors and handle HTTP status codes? Provide an example of using fetch to handle different types of responses, including successful and error responses.

    : For any errors which prevent the fetch to fulfill there is the try/catch syntax (for async/await) or the .catch() (for .then()). But there can be errors which don't prevent the fetch, only the request isn't succesful (e.g. it's a get request for information based on an id but the server's endpoint doesn't find it in the databse). For these kind of errors/unsuccesfulnesses there is the response's ok property which is true if the response code is between 200-299 (so it's succesful), otherwise it's false. With this property we can write code which behave differently based on its value.
    Example: fetch(url).then((response) => {
        !response.ok && throw new Error(response.status);
        return response.json();
    }).catch((error) => console.error(error));

- Explain the parts of an URL.

    : These are the parts of the URL (Uniform Resource Locator), for example the https://www.telex.hu/hirek/megolte_a_mikulast_majd_virgacsot_adott_maganak?search=mikulas
    1. Protocol: It specifies the protocol of the request. In most cases it is either HTTP (Hypertext transfer protocol) or HTTPS (HTTP secure), maybe FTP (file transfer protocol)
    2a. Domain name: it can consist the www. and has a TLD (top level domain), in our example it is .hu (www.telex.hu). This is more or less a cover for the ip address of the telex's server
    2b. IP adress and ports: instead of a domain name there could be an ip address and port number, for local url it is most likely to use these
    3. Path: this specifies the path of the resource the client (usually the browser) want to reach, in this example the telling path will lead us to a devastating article
    4. Query string: this is optional part of the url, with this the client can pass parameters to the server. The syntax is that it start with a ?, the properties are separated by an &, and the key and value is separated by an =
    5. Fragment identifier: also an optional part of the url, with this we can link a specific part of a webpage directly


## Serve✔

- Explain the concept of client-server communication in the context of web development. How does information flow between the client and the server in a typical client-server architecture?

    : In web development the client-server communication mostly means it happens with HTTP or HTTPS requests and responses, which means this protocol is the form how the client and server exchange information. It is used to serve the client (most likely a browser) with the resources and data to build up the web application and to give the client side a way to modify or manage the data stored in or reached by the server (e.g. a mongoDB database). So the client typically send requests and get reqponses for them from the server.

- What is the role of HTTP requests and responses in web development? Explain the structure of an HTTP request and an HTTP response.

    : HTTP requests-responses are the staple structures of the client-server communication. A http request has four parts:
    1. request line: it has 3 subparts: the http-method (e.g. GET), the URI (Uniform Recources Identifier), and the version of the HTTP protocol
    2. headers: contains metadate about the request, for example the type of the body's content, or keys for authorization
    3. body: it contains the data sent with the request. this data contains various type of data

- Explain the key differences between the CommonJS require syntax and the ECMAScript (ES) module syntax import. How do these two approaches handle module dependencies and exports in JavaScript?

    : syntactically they look like this (for the key differences see above):
    1. CommonJS: const moduleName = require("moduleLocation");
    2. ES: import moduleName from "moduleLocation";

- What are the advantages of using the ES module syntax import over the CommonJS require syntax?

    : There are four advantages of using ES modules over the older CommonJS syntax:
    1. Static analysis: the ES modules can be analised at build time giving an opportunity to apps to optimize the code.
    2. The ES modules are natively supported by modern browsers
    3. The ES module syntax is considered more readable

- What is Express.js and how does it simplify web application development in Node.js? Explain the core features and benefits of using Express.js as a web framework.

    : Express.js is a back end framework for create RESTful APIs with Node.js. With it it's much easier to create server API endpoints in JS by serving a relatively simple syntax and giving numerous tool for it. In a MERN application the server side is built on this framework. The main features of Express.js is the following:
    1. Routing: with Express.js it is quite easy to define routing and set up endpoints, specify how the app should respond to different HTTP requests.
    2. Middleware: Express.js has a lot of built-in middleware which can be easily used in a modular way. Aside from the built-in middlewares we can create custom ones.
    3. Static files: Express can serve static files by defining a static directory, make sending to client side html, css or JS code easy.
    4. Error handling: Express.js has built-in error handlers which make it easy to apply error handling to a web app's server side.

- Explain the process of handling static files (e.g., CSS, images) in Express.js. How can you configure Express.js to serve static assets from a specific directory in your application?

    : You can serve the content of a folder with the express.static() middleware with which the express handles the requests for these files with a proper response (with the asked file in the response's body). We use the express' use() method for this, which has two parameter, the path where it has to activated and the middleware which is the express.static(), and this has a parameter which is the path of the directory we want to make available.

- How does Express.js handle HTTP request/response cycles? Explain the process of receiving and responding to requests using Express.js middleware and route handlers.

    : Express.js handles these cycles with middleware functions and route handlers to process the incoming requests and send responses back. When an HTTP request reach the express.js app it first executed the middlewares created in this app (if the requests path contains the middleware's path parameter or if there is no such parameter of the middleware) and after that the route handler with the corresponding path parameter will handle the request and send back a response to the client, completing the cycle.


## Forms✔

- How does routing work in Express.js? Explain how to define routes and handle different HTTP methods (GET, POST, etc.) in an Express.js application.

    : One of the HTTP request's main attributes is the URI string which contains for example the TLD or the IP/port numbers, so basically serves as an address to where the request should 'go'. With Express.js these routes can be defined and so create code which act accordingly to the request's path (and method, and other information it holds). We can create endpoints with the expressap.GET/POST etc. methods which has a path parameter and a callback function which is executed if a request reach the endpoint.

- What are the various methods available in Express.js for sending responses to clients? Explain the differences between res.send() and res.json() in Express.js.

    : There are several methods of the response object for sending response to the client: 
    1. res.send(): this send back a response which response's body will be the value it got as argument. The response's content-type will be aligned with the type of the parameter.
    2. res.json(): this is for sending data as json string. It stringifies the value it got as parameter and send it as response, while the content-type is set to 'application/json'.
    3. res.download(): this is for sending a file to be downloaded by the user
    4. res.sendFile(): this is for sending a file to the client but not necessarily for to downloaded by the user, it waits the path of the file as parameter
    5. res.sendStatus(): this set the response's status code and also its body as the status code's string representation

- Explain what the express.json() middleware does.

    : Express.js's middleware does some processing on the request before it reaches an endpoint. These middleware are for modify and pass the request to another middleware or the endpoint by design.
    The express.json() built-in middleware in particular parse the stringified json object arrived as the request's body into a Javascript object if the content-type of the request is 'application/json'.

- What is the purpose of the next() function in Express.js middleware? How can you use it to pass control to the next middleware function in the chain or to terminate the middleware processing?

    : In express the middleware get three arguments: the request object, the response object and the next function. The next function end the actual middleware's processing and pass the request to the next middleware or to the endpoint.

- Explain the concept of route parameters in Express.js. How can you extract dynamic values from the URL path using route parameters, and how are these values accessed within route handlers?

    : With express.js the path of endoints can contain parts of it which can be any kind of substring. For example a path looks like this: '/api/emlpoyees/:id' means that a request with the '/api/employees/apacuka' uri will reach this endpoint and the apacuka will be processed as a parameter. This parameter can be accessed via the request object passed to the route handler's callback function: the request.params holds the route parameters as properties where the key is the name of the parameter (id in this example) and the value is the substring which is in the place of the parameter in the request's uri (apacuka in this example).

- Can you name some typical HTTP response codes and their meaning?

    : Some example of HTTP response codes:
    1. 200 - ok
    2. 201 - created
    3. 400 - bad request
    4. 404 - not found
    5. 429 - too many requests
    6. 444 - no response
    7. 500 - internal server error

- Can you name some typical HTTP request/response headers and their meaning?

    : They are the most common headers:
    1. Content-Type: specifies the type of the body's content, it is crucial for passing information in the request/response's body
    2. Cache-Control: specifies how the response should be cached
    3. Accept: defines what type of data (e.g. html, json etc.) the client can accept from the server
    4. Authorization: holds the client's credentials to access some restricted resource

- What are the common HTTP methods used in web development, and what are their respective purposes?

    : There are some methods used in web development, the most important ones for CRUD operations are:
    1. GET - this is for getting information/resources from the server, this is the basic method if you type a URI into a browser's address bar. Usually data to specify the ask for resources (e.g. filters) are passed via url queryparameters or sometimes route parameters.
    2. POST - this is for add a document/element to the resources of the server. It is usually pass the content to be added in the request's body and the response usually send back the data in the form it was saved (e.g. with the newly generated id).
    3. PUT - this is for replacing an existing element of the database to a new one. It is work similar to the POST method but the request holds some information to identify the element to be replaced (most likely it is an id passed via route parameter).
    4. PATCH - this is for updating some part of an element, possibly by not replacing the parts' value but add to them, which means the patch can be not-idempotent (repeating the same request could change the resources final state). Otherwise it works similar to PUT method.
    5. DELETE - this is for deleting an element or elements from the server resources. The response usually sends back the deleted data.

- How does the GET method differ from the POST method? Explain when it is appropriate to use each method. Which one uses request body to send data? What the other method uses to send data?
    
    : see above

- Explain the use of the PATCH method in HTTP. How does it differ from the PUT method, and when should it be used to update a resource?

    : see above

- How can the DELETE method be used to remove a resource from a server? Explain how the DELETE method works and any considerations for handling resource deletion.

    : see above

- How do you handle form submissions using JavaScript? Explain the process of capturing form data and preventing the default form submission behavior.

    : Form html element has a built-in behaviour to handle submit event and some attributes to set it up. In most cases it isn't fit for the actual form's intended purpose so it is ncessary to prevent this behaviour completely. In the submit event's handler function the event.preventDefault() method terminate any process of this behaviour making it possible to create some custom form submitting in this function.
    So we usually handle form submission by event handler. There are some way to capture form data, the most handy is the formData() method which create a special object which contains the values of the form's input fields. Alternatively we can get these data from the form's children, and with React we usually use states to store the current values of the form's input fields.

- Explain the required elements necessary to define a form in HTML.

    : The form element itself is obviously necessary, and some of its attributes is necessary to set up the default submission behaviour but it isn't necessary in every case (see above). Aside from it what is truly mandatory is at least one form controls element which collect user input (but usually there are multiple elements in a form). There has to be some kind of trigger to send the form, it is usually a submit button.

- What is the purpose of the required attribute in HTML form elements? How does it enforce mandatory input fields and prevent form submission without the required information?

    : When a form's element's required attribute is set to true (it's false by default) the form cannot be submitted is that element is empty.

- Explain the different types of form input fields available in HTML. How do input types like text, number, email, checkbox, and radio buttons differ, and how are they used in forms?

    : Input element has a type attribute which defines what kind of input that element wait. Even if some of the input types wait for a text (e.g. text, email etc.) there is some built-in input validation in them which is very handy to use. Text, number, email etc. types show an input field and wait the user to type some input in them, while checkbox and radio buttons can be only clicked on and set checked with this (the differenc between them is multiple checkbox can be checked while only one radio button can be active under the same name). So radio buttons are used in forms for exclusive choices while checkboxes for non-exclusive ones.

- Can you explain the purpose of the name attribute in a context of form submission?

    : The name attribute is for identify input elements during the submit, because the form element holds its input elements' value under their name (form.elements['element's name']).

- Can you explain how we can connect a label tag to a form element?

    : There are two simple methods to connect a label with a form element:
    1. Put the form element inside the label element, simple as that.
    2. Use the label element's for attribute and give it the value of the form element's id we want to connect to.

- How can you dynamically manipulate or modify form elements using JavaScript? Explain how to add or remove form fields dynamically based on user interaction or specific conditions.

    : With classic DOM manipulation we can do this with the event listener and its callback function. Inside this function we can use the appendchild method to add more form elements to the form.
    With React we can render the form element deriving from a map() method of an array and use states and state setters to trigger re-rendering under specific circumstances.

- How can you convert form data into a format that can be easily transmitted or processed by the server?

    : With the formData() method we can create a special object which has properties representing the form's fields and values. This object can be sent as a HTTP request's body (the Content-Type will be automatically set to 'multipart/formdata'), so from the server perspective this request would be the same as the request being sent according to the form's default behaviour.


## React✔

- What is React.js and what are its key features?

    : React is an open source library/framework developed and maintained by Meta. It is made for create single-page applications and generally build UIs/UXs. During this Codecool module this was the standard way to create the frontend side of the web app. It has several key features of which they are the most importants:
    1. JSX: JavaScript Syntax Extension is a combination of html and JS, in other words it's a html-like extension to JS language which can embed JS code into itself in an easily readable way, making it more easy to work on both the html structure and the frontend logic of the application.
    2. Virtual DOM: it is an extra layer between DOM and the webapp which use React. Without it any changes would automatically lead to rerender the whole DOM at once which make webapp slower. With React the Virtual DOM is updated first upon changes in the webapp's run, the React finds the differences between Virtual DOM and DOM and updates only the changed parts, making the webapp's run faster.
    3. One-way data binding: in React the data normally is passed from top to bottom via params of components, this is a key attribute of React.
    4. Conditional Statements: JSX allows to write conditional statements and React will render the Virtual DOM accordingly.
    5. Components: React divides the web page into components which are part of the UI design with their own logic and design, and these components make it easier to handle the web page by its parts.
    6. Extension: React is a widely used library and as such it has a lot of extensions which help developers to create apps more easily.
    7. It follows from the above points that React can provide better performance

- Explain the concept of virtual DOM and how it contributes to React's performance.

    : see above

- Explain the component-based architecture in React.js. How do components work, and how can they be composed to build complex user interfaces?

    : Component is a reusable piece of UI (or the web page) which holds this piece's functionality, design and presentation. In React a web page is built with the hierachical structure of components, which make handle the parts of a webpage separatily possible. The return value of a component is always a piece of the Virtual DOM and it can contain calls of another components making them the 'child' of the said component. For example if we have a news site with two separate column and a header, we use one component which calls three other ones representating the separate parts of the web page (columns and the header), and working on one component means only that part of the web page is affected. This means the parts of the web pag can behave quite differently.
    When a component is being used (= being part of the Virtual DOM actual state) we call it mounted, and when ceased to be part of it we call it unmounted.

- What is the significance of JSX in React.js? Explain how JSX combines HTML-like syntax with JavaScript code and how it is transpiled into regular JavaScript during the build process.

    : JSX makes it possible to write html-like syntax in the JS code and to manipulate DOM without the classic DOM manipulation techniques (like `appendchild`). The components return value is written in this syntax which can hold html elements or html-like element (e.g. other components' calls). Syntactically it means that inside the html-like JSX with the `{}` brackets we can put 'vanilla' JS code which return value which is usable to the JSX (like a string or another piece of JSX syntax).
    It is important to note that jsx has to be transpiled before it run to regular JavaScript, one tool for this is Babel, but a React app is doing it automatically. Under the hood it is the React.createElement what creates the element which is used to update the UI.

- What are props in React and how are they used to pass data between components? Explain the concept of props and how they facilitate parent-child component communication.

    : Props (short for properties) are the tool to pass data from parent component to child ones. This is a one-way communication where only the parent pass information to its children. The props itself is a parameter of the child component (actually the only parameter), and it is an object which properties are the information the component's call passed as 'arguments', which in jsx syntactically looks like defining a html element's attribute (for example in a component's call name="John" will became a property of the props where the key is name and the value is John).

- How can you access and utilize props within a functional component in React? Explain how to extract and use props using the destructuring syntax.
    
    : Props can be accessed with the component's only parameter called 'props' (see above) as any other function's parameter. For a shortcut we can use object destructuring in the parameter list quite easily because a component's only parameter is the props object. Syntactically it look like this: `function Component({propsPropertyOne, propsPopertyTwo}) {}`.

- How can you pass callback functions as props in React? Provide an example of how to pass a function from a parent component to a child component, enabling the child to communicate with the parent.

    : As with any other function calls, with the name of the callback function or with a function declaration. For example in the parent component where we declared a function called handleChange:
    `...<ChildComponent onChange={handleChange}/>`
    will be used in the ChildComponent like this:
    `function ChildComponent({onChange}) {...<form onChange={onChange}>}` - with this the form element in the jsx syntax is got the function defined in the parent as a change event handler.

- Explain the concept of spreading props in React. How can the spread operator be used to pass multiple props from a parent component to a child component in a concise manner?

    : If the parent component has to pass several props it can be exhausting to write them down in the component call with the jsx syntax. Instead of this, we can spread into it with the spread operator in the following syntax: `<ChildComponent {...object}/>` - where 'object' is an object which holds the properties we want to pass the child component. But we don't necessarily need object for this, we can use separate variables: `<ChildComponent {...{var1, var2, var3}} />` where the 'vars' are declared variables from the parent component.

- Explain the concept of default props (with ES6 JS syntax) in React. How can you define default values for props in a component to handle cases where the prop value is not explicitly passed?
    
    : The most simple way to do this is to use the destructuring syntax in the child component's parameter list, where with a `=` we can declare default value to a property of the props parameter, like this: `function ChildComponent({propsPropertyOne = null}){}` - with this the `propsPropertyOne` property will get the value `null` if there is no value passed to this specific property.

- Explain the immutability principle when working with props and states in React. Why is it important to avoid directly modifying prop values within a component, and what are some best practices for maintaining immutability?

    : For React to work properly it is important to not mutate objects which are used as props or states, although a JS object in fact mutable, this is called immutability principle. It is important because the changes of a state trigger re-rendering, but only when the state get a new value - and since objects (and arrays etc.) are mutables and reference type values simply modifying them won't create a new value, and changing a state this way (even with state setter) won't cause re-rendering.
    To avoid this problem we can create a shallow copy of the state's value, modify this copy and set it as the new value of the state with its setter. It is also important to know which method create a new reference type value and which modify the original in place.

- How does React.js handle state management? Explain the concept of state and how it differs from props.

    : A state is an object which purpose is to hold a value which is important to the work of the component or components. When a state gets a new value the React check if this change should lead the re-rendering of the virtual DOM (or part of it). States are also used to send back information from child components to the parent. We create states with the UseState hook, which is basically a constructor which create a state and a state setter. This latter is a function with which we should change the value of the state. Passing this setter as props make it possible the children components to add new value to one of their parent's states.

- What are React hooks? Explain the purpose and benefits of hooks like useState, useEffect in React.js.
    
    : Hooks allow us to use React features like useState or UseEffect. With them we can use these features in function components making class components unnecessary. UseState creates states and their setters (see above), while with useEffect we can define a function which is only executed when given states are changed (it is only run once at the mounting of the component if the dependency array is empty). It has two parameters, the callback function and the dependency array which can holds the states the useEffect 'listen of'. Without this the function which is called simply in the component's body would be executed every time something is changed.

- Explain the concept of virtual DOM reconciliation in React.js. How does React efficiently update and render components by performing minimal DOM manipulations?

    : When a state's value is changed (not modified) the React regenerate the DOM tree creating a second virtual DOM. After that it compares the older virtual DOM to the new one and reconciles their differences and renders the differences. After that React applies these changes to the real DOM with the minimum number of operations necessary. This means the React only changes when and what is necessary to change the real DOM making the web app more performance efficient.

- Explain how to manage complex state objects with useState. Explain techniques like object spreading or merging to update specific properties within an object state.

    : When we want to modify a state's value which is a complex object we can use the spread operator to spread this object's properties into a new object creating a shallow copy of it. We can use it to merge objects into a new one. If we want to merge one or more objects into an existing one we can use the `Object.assign()` method which has two type of parameters: the first one is the target object which will be modified and the parameters after it are the source objects of which properties will spread into the target object.

- Why is it important to provide a new array as an argument to the useState hook when adding an item to an existing array?

    : As we said above the React's reconcilement is only activated when a state gets a new value, and with reference type values like objects and arrays it won't be a new value if we modify (for example push) them. And if an array is a state's value it has to be something to do wiht virtual DOM and the web app's UI (otherwise it shouldn't be a state's value in the first place).

- How does conditional rendering work in React? Explain the different techniques and approaches available to conditionally render components or content based on certain conditions or state values. How can it be used to control the visibility or behavior of components based on user interactions or other dynamic conditions?

    : One of the great result of JSX syntax is that we can combine JS conditional methods with the html-like form of JSX. This means we can set up conditions and React will render the UI of the web page differently according to the state of the code's run. We can use switch, if/else, ternary operator, nullish coalescing operator, and logical operator etc. for this, basically any JS code which runs differently based on the state of certain conditions. The most common method for React is the ternary operator though.
    This can be on another levels too. One component's return value could be one ternary operator with two branch, or a component call's props can be differ based on some condition.

- How can you create a select input element in React? How does it differ from the html's select tag? Can you show an example of a controlled and an uncontrolled select element with default value setting?

    : Creating a select input element in react is quite similar to the plain html method because of the JSX, there are differences, however. One is that for the select's attributes' values we can add JS code, for example a function to one of the event listener attributes, or a state to the 'value' attribute. The other important difference is that we can create option tags with JS, making it possible to dynamically rendering options to it (e.g. making an array's all element to be represented in the select input as an option).
    In React there is also an important pair of concepts, the controlled and uncontrolled elements. The former means that the form or other user input is handled and stored is states (e.g. in a form's all fields have a corresponding state and submitting that form the event handler will retract the information from these states). In the case of the uncontrolled elements the user input is handled by the DOM itself. To use this way in the React we can use the `useRef()` hook with which we can reach the current value of the element (the variable on which we used the `useRef()` should be the value of the select element's `ref` attribute).


## Database✔

- What is MongoDB, and how does it differ from traditional relational databases? Explain the key features and advantages of MongoDB as a NoSQL database solution.

    : MongoDB is a document-oriented NoSQL database with JSON-like documents and optional schemas. There are several key differences between MongoDB and the SQL (Structured Query Language) solutions (like MySQL):
    1. In MongoDB each record is stored in documents while in SQL databases the records are stored as a row in a table
    2. Multiple records are stored in a collection in MongoDB instead of a table as in the SQL databases
    3. In MongoDB's collection the documents can have different structures while in SQL the rows has to follow the format of the table. This also means in MongoDB a field's value can be non primitive data type like list or object. And while with mongoose we can add a more strict schema for a collection the definition of the schema is more flexible than in SQL solutions.
    4. For its less structured (or potentially more structure variation) databases MongoDB has a deep (and confusing) query API for create searching/filtering parameters

- Explain the concept of collections and documents in MongoDB? How does MongoDB store data, and how is it organized within collections and documents.

    : MongoDB data structure is built on documents which are stored in collections (and collections are stored in databses). A document is composed of fields (key-value pairs like an object's property in JS) where the value is a form of BSON data, so it can be more than the six JSON data types.

- What is Mongoose.js, and how does it simplify working with MongoDB in a Node.js environment? Explain the key features and benefits of using Mongoose.js.

    : Mongoose is an ODM (Objective Data Modelling) library for JS to manage data stored in MongoDB. ODM basically means it modelling something (in this case a MongoDB database) with JS objects. Its key features are:
    1. Schemas: while MongoDB's liberty in data structure make it suitable to be widely used, for specific use it is highly useful to have a more strict schema for the collection and mongoose has schema which is enforced in the application layer. Mongoose also has built-in data validation which is essential to enforce the specific schema's ruleset.
    2. Mongoose has methods for manipulating MongoDB databases in JS, it's model object's built-in functions can be used for any kind of CRUD action. Mongoose has also have tool to connect for example a web server to a MongoDB database. While MongoDB can be manipulated in JS without mongoose it is more easy and efficient that way.

- How do you define and create schemas in Mongoose.js? Explain how schemas define the structure and validation rules for documents in MongoDB collections.

    : We can create schemas with the mongoose built-in Schema constructor, the syntaxis looks like this:
    `const newSchema = new Schema({
        fieldOne: {`(ruleset for field)`},
        fieldTwo: {`(ruleset for field)`}
    })`
    We can set value type and default value for a field, make it required or unique etc in the ruleset. If we create a mongoose model (roughly the JS representation of a MongoDB collection) with this particular Schema we defined and later want to add new documents or modify existing ones via mongoose the new data has to be aligned with these rules (e.g. a field which is required cannot be missing in a document).

- Explain the different types of Mongoose.js data modeling techniques. How can you define relationships between MongoDB collections using Mongoose.js, such as one-to-one, one-to-many, and many-to-many relationships?
    
    : When we want to create complex data structures in MongoDB we can use either embedded documents or document references. The former means there are nested complex data structures (e.g. an object) inside a document while in the case of the latter there are ids as references to other documents from other collections.
    In the case of document references we can use mutiple type of relationships:
    1. One-to-one: in this case one document is only referred to exactly one other document from an other collection.
    2. One-to-many: in this case one document is referred to multiple documents from an other collection, but these documents are still referred to only this one document (e.g. books belong to only one author, but an author can belong to multiple books).
    3. many-to-many: in this case one document is referred to multiple documents from an other collection and these documents can also be referred to multiple documents.
    We can define this relationships with mongoose's Schema constructor: in the field's ruleset where which we want to have a reference to another document we can use the { type: Schema.Types.ObjectId, ref: "mongoosemodel's name" } code, and this way the schema will want an id from that collection for this particular field. If we want this field to hold multiple references we can simply put this code into a []. With this we can establish one-to-many or many-to-many relationships with mongoose.

- What are the available options for querying and manipulating data using Mongoose.js? Explain how to perform CRUD operations (create, read, update, delete) using Mongoose.js methods and queries.

    : Mongoose has a series of built-in methods to execute CRUD operations on the database:
    1. Create: we can create a new document by using a mongoose model as a constructor, and use the .save() method on this document. Alternatively we can use the mongoose model's .create() method to create a new document in the collection.
    2. Read: we can use the mongoose model's .find(), .findOne() and .findById() methods. The first two methods wait for search parameters for argument, the third's argument is a value for id by default.
    3. Update: we can use .findOneAndUpdate() method for this, it has two parameters, the first is the search parameter and the second is the updated data. Another method is .updateMany() which has similar parameters but update all documents matched to the search parameter's criteria. Alternatively if we combine the .find() method with the document's .save() method for updating.
    4. Delete: we can use .findOneAndDelete(), .deleteOne() and .deleteMany() methods, they have one parameter which is the search parameter.

- Explain the process of connecting to a MongoDB database using Mongoose.js. How can you configure and establish a connection to a MongoDB server using Mongoose.js in a Node.js application?

    : It's quite simple to establish a connection with a MongoDB server with mongoose. We need to use the .connect() method for it, which has only one parameter, the url of the database we want to connect to. Usually this url keep some kind of information for authentication, for example if we want to connect to a MongoAtlas database (which is a cloud database service) in the url there is the username and password as substrings. After we connected to the database we can use the mongoose's methods on it.


## MERN✔

- Explain the concept of React Router. How does it enable client-side routing in React.js applications and facilitate the creation of multi-page-like experiences?

    : React Router is a third party library to expanse the functionality of the React library by handling routing in React JS applications. With it it's easy to create dynamic routes and navigation in Single Page Applications which give the same experience as though it happens via server side routing. It can handle different paths, but it can work without communication with the server, which is important if the client side's connection is instable. This can be achieved by React Router's methods like createBrowserRouter() or RouterProvider, with them we can set different components to be called according to the path given by the user (or the website's code). This happens "inside" the React, so the actual DOM isn't refreshed more than necessary.

- Explain the concept of server-side routing in Express.js. How does Express handle incoming requests and route them to the appropriate API endpoints or route handlers?

    : Server-side routing is the more traditional way to handle different pages in the same web application. This means every time the user navigates to a new page (typically with a new path) the old page is discarded and a new html is loaded. This happens with server-client communication in the form of http requests/responses, so the server provides the resources (html, JS code, CSS, other files) for the new page. This means that the client only need to download the current page's resources not the entire app's like in client-side routing. However, in this case the client has to download the current resources every time tha page is changing even if there are overlaps with these resources (e.g. the design elements or the navbar).
    With Express.js we can create the server-side routing by creating endpoints with .get/.past etc. methods with different paths and set up responses which handle the resources necessary for the pages belongs to said paths.

- What is the MERN stack? Explain the individual components of the MERN stack and their role in building web applications.
    
    : MERN is an acronym for MongoDB, Express.js, React and Node.js, four technology with which we can create a full-stack web application as they tackle different parts of it. The Node.js is a JS runtime environment to create (and run) JavaScript code, this is kinda the base of the MERN stack. Express.js is a library for JavaScript to create server routes and endpoints. React is also a JavaScript library/framework to create single page applications and build UI/UX for web apps. MongoDB is a NoSQL database software with which we can use these kind of databases (there is also a JavaScript library for handling MongoDB via JavaScript: mongoose).
    With these technologies we can create JavaScript code, create the client and server side of the web app and use database to store, read and manipulate data which belongs to the web app.

- Explain how does a proxy works during React development. How can you tell the webpack dev server to proxy the requests to your backend? What kind of URLs you have to use in the fetch in your JS code, if you want to use the proxy.

    : During development with MERN the client-side requests came from a different origin than the server side which receives them. Beacuse of the Same Origin Policy (a security mechanism which forbid JS files to send HTTP requests to another origin except their own) this means that during development the requests toward the server will be unsuccesful. The most easy yet safe solution for this is to set up proxy in the client side which transmit requests to the server-side kind of bypassing the SOP. With React we can set up proxy in either the package.json or, if we use Vite in the vite.config file. In these settings we can determine what HTTP requests should be transmitted to the server. With this we can use only the path part of the url because for the request it will be as though the place of request is from the same origin as the place of response.

- Explain the advantages and benefits of using the MERN stack for web development. How does each component of the MERN stack contribute to the development process and overall efficiency of building modern web applications?

    : The MERN stack has several advantages:
    1. It enables full-stack development with only one language, the JavaScript. This make learning curve more friendly and the codebase more consistent, make it easier to work simultaniously on every part of the web app.
    2. The Node.js with the Express.js library is great for creating server side for web apps with high user traffic because it can handle well simultaneous connections (Node.js process multiple requests simultaneously).
    3. With the React we can create dynamic and high performance UI which has all the advantages of React (see above).
    4. With MongoDB we has a felxible and scalable data management tool.
    5. The parts of the MERN stack are designed to work together in a seamless way which creates faster development cycles and overall more efficient development.

- How does data flow in the MERN stack architecture? Explain how the frontend, built with React.js, communicates with the backend, developed with Node.js and Express.js, to handle client requests and serve data from the MongoDB database.

    : The frontend in a MERN stack architecture communicates with backend by HTTP requests/responses. The frontend built with React create requests with the .fetch() method and the routes and endpoints of the backend (server) side receive and process them according to the url and method of the requests and send a proper response to the client side. With MERN because the React has an own development server which serves the UI functionalities of the web app the backend's function is usually only to serve the RestAPI (CRUD) requests.