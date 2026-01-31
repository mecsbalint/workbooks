
# Python

## Python Introduction✔

* What is Python?

    : Python is a high-level, interpreted, dynamically type-checked and garbage-collected language created in the 1980s by Guido van Rossum (the first release was in 1991). Python is a multi-paradigm language that supports OOP or procedural programming. It is one of the most popular languages and it's used mainly for data science, data analysis, machine learning and other fields.

* What is `CPython`?

    : `CPython` is the original, most popular and maintained implementation of the Python language which works both as a compiler and as an interpreter since it compiles Python to bytecode before interpreting it. It is written in C and Python, and it has some distinct feature like the GIL or the FFI (see below). Usually (and in this workbook) when we talk about Python's implementation details such as how it is executed we talk about the `CPython` implementation.

* What are some of the other implementations of Python?

    : Python has quite a few "production-quality" implementations. `Jython` is written in Java and compiles Python to Java bytecode hence it can be run on Java Virtual Machine afterwards, and it can use any Java classes. `PyPy` is written in `RPython` and translates Python code to `C`. `IronPython` is written entirely in `C#` and allows to use `.NET` libraries and frameworks in the `Python` code.

* What is PEP8?

    : PEP8 is the 8th element or part of the Python Enchancement Proposals, and is a guide for Python coding conventions a programmer should follow when writing in Python, however they are not hard rules. It has recommendations for variable naming, code layout, comment styling etc. It was created by Guido van Rossum among others.

* What are the key features of Python?

    : There are several features of Python:
    1. It is free and open source, and it has a large community support
    2. Python is a high-level language and its design emphasizes readability and easy using.
    3. Python is an integrated language which means it is easy to integrate with other languages especially C or C++. Because of this there is a lot very useful and fast library for Python written in C or other low-level language (e.g. Pandas or Matplotlib).
    4. Python is a dinamically typed language, which means the type for a variable is decided at runtime and a variable can get any type of value during runtime.

* How is Python interpreted?

    : Python is an interpreted language which means its code is compiled line-by-line during runtime rather than compiled all together before runtime (like compiled languages do). It's important to mention here that these terms can't describe fully the implementations of the languages. We consider Python an interpreted language because it executes code logic directly and doesn't have a dedicated compilation step, everything is happening during the runtime.
    The steps from the python code to running the program on the machine is done by the Python Interpreter. First it compiles the Python code into bytecode and also checks for syntax error. After this the bytecode is processed and converted to machine-executable code by the Python Virtual Machine and this code is run on the machine itself.

* How does Python handle memory management? What is the purpose of the `gc` module in Python?

    : Python's memory management is done by its garbage collector from the built-in `gc` module during runtime. Garbage collector monitors the values created for the execution of the python code and deletes any value which isn't pointed to by a variable (so it isn't in use anymore). It does it by reference counting. Garbage collection's advantage is it gets rid off unused values automatically and the programmer doesn't need to do it. It's disadvantage is that it requires to be run during the execution of the program using resources and making the program's run a bit slower.

* What is the Global Interpreter Lock (GIL) in Python?

    : GIL is a lock that allows only one thread to hold the control of the Python Interpreter even in multithread environment at a time. Allowing multiple threads to control the interpreter would be problematic because of the reference counting of Python's memory management. Multiple thread could lead race conditions where a counter is decreased or increased by more than one thread simultaneously which could lead to memory leaking or incorrect memory releasing (which means some value would be lost while they are still in use). It doesn't mean that only one thread can be used by the interpreter during the whole runtime, but every thread has to wait until no one else is run (to execute bytecode a thread needs the interpreter lock). This means that Python is effectively single-threaded performance-wise.
    It was chosen as a solution because the early days of Python the operation systems didn't have the concept of multi-threading, and a lot of library written in C was created with these environments in mind. They needed a thread-safe memory management and the GIL provided it and it was simple to implement. Later this wasn't change because Python is faster for single-thread programs this way and most of its libraries were built this way.

* How can you create and use a Module in Python?

    : To create a Python module you need only a file with th `.py` extension and some legit Python code as content. To use it you can use the `import` statement. With it you can import the whole module or only elemnts of it (like variables or functions).

* What is the `if __name__ == "__main__"` statement used for?

    : When we importing a module in Python the program will execute the imported module. Because of this, if there is anything that isn't a declaration in the imported module we should put in an if statement's true branch where the condition is `__name__ == "__main__"`. This condition will be only true when we directly run the said module.

* What is the purpose of `__init__.py` in a Python package?

    : `__init__.py` file is a declaration file that indicates that the directory is a regular python package and can be imported. It is usually an empty file but it will be executed upon the first import of the package, so if necessary we can put some code in it (e.g. it can import some other modules the package needs). It's important to mention that since Python 3.3 the `__init__.py` is optional as the interpreter can recognize python packages without it as namespace packages. For regular packages `__init__.py` is still necessary.

* How do you handle exceptions in Python?

    : By default an exception cause the program to stop (we call it an unhandled exception). We can handle exceptions with the try-except control structure. If an exception occurs in the try's block then it won't stop the program to run but rather it will run the except's block where we can handle the problem itself. We can chain multiple except blocks after a try block and set them to "listen" different kind of exceptions.

* What is conditional expression in Python?

    : Conditional expression is a shorthand syntax element to write an if-else in a single line. The syntax is value if condition else alt_value. It is usefule everywhere we need an expression but it's especially used for dynamic variable assignment. 

* What is the difference between `del` and `remove()`?

    : `del` is a statement to remove a value or an item of the value and can be used on immutable variables. `remove()` method is a built-in method that remove the first matching element with the argument from the list we called upon.

* What can happen if you try to delete/drop/add an item from a List, while you are iterating over it in Python?

    : When a loop iterating over a List or other iterable then it go through the iterable step by step by the elements position, so when it iterate over the value on the Nth position then the next iteration will be over the value on the N+1th position and so on, and does it until there is no remaining position in the iterable. If we modify the iterable we can cause unexpected results like the loop doesn't iterate over an element if we delete another the loop has already iterated over. Or if we add a new element in every iteration we can stuck in an infinite loop because the ever-growing iterable will never be ended.
    For these reasons it's considered unsafe to modify the iterable directly during an iteration, especially if it means changing the length of the iterable. The easiest workaround for this is to create a copy of the list and modify that during the iterations. 

* What is slice operator in Python and how to use?

    : Slice operator creates a subsequent from a sequent. It's syntax is `[num1:num2:num3]` where the num1 sets the starting point inclusively and the num2 the ending point exclusively, and the num3 sets the length of the steps (by default it's 1).

* What arithmetic operators (+,*,-,/) can be used on lists in Python? What do they do?

    : The `+` operator can be used on a List if the other element of the operation is also a list; in this case the operation returns a concatenation of the two lists. The `*` operator can be used on a List only if the other element of it is a number; then the operation's return value is the List's concatenation of itself so many times as the number induces. The `-` and the `/` operators can't be used with Lists.

* What is the purpose of the `in` and `not in` membership operators in Python?

    : The `in` operator returns a `bool` value according to if a the value structure on the right contains the value on the left. The value on the right is treated as in loops for example, so if it's a dictionary this operator will check the keys of that dictionary. The `not in` operator works the same way but returns False if the data structure contains the value rather than True.

* What is the with statement in Python and why is it used?

    : `with` statement is used for resource management (for example file reading) and it's basically a syntax sugar that equivalent with a try-finally block where the .close() method is called in the finally block on the flow we started in the `with` statement's line.


## Types in Python✔

* Do the variables have type in Python?

    : No, the variables don't have a type in Python, rather they all have a reference that points to a value which has a type. The variables are stored in the stack along with their reference or pointer and the values are stored in the private heap of the program. Hence any type of value can be assigned to a variable without restriction in Python.

* What is the difference between `is` and `==` in Python?

    : In Python `is` is an identity operator and checks if the two variables of its sides are pointed to the exact same object. The `==` equality operator on the other hand checks the values of the objects and returns a `bool` accordingly. In a more technical way the equality operator will call the `__eq__()` dunder function on the element on the left with the element on the right as an argument.

* What is `None` in Python?
    
    : `None` is a special value in Python, the only possible value of the type `NoneType`. It's used to represent the lack of value and it's not equal to `False` but is a falsy value.

* What is the difference between mutable and immutable types in Python?

    : Immutable types in Python means the value objects belonging to these types cannot be modified. Most of them are the non-collection data types like numbers or booleans, string or bytes but some of the collection data types are also immutable like the tuple. The other collection data types are mutable which means their data objects can be modified.

* What are Python’s built-in data types?

    : There are several built-in data types for Python and we can categorized them into different groups:
    1. Numeric types: `int`, `float`, `complex`
    2. Sequence types: `list`, `tuple`, `range`
    3. Text type: `str`
    4. Set types: `set`, `frozenset`
    5. Mapping type: `dict`
    6. Boolean type: `bool`
    7. Binary types: `bytes`, `bytearray`, `memoryview`

* What type of elements can a list contain in Python?

    : A list can contain any value from every data types in Python, moreover it can contain different types at the same time.

* Describe the `tuple`, `list`, `set`, `frozenset` and `dictionary` types!

    : They are all Python's built-in collection data types with different attributes. `tuple` is an unmodifiable array of elements, while `list` is the same but modifiable. `frozenset` and `set` works similar to them but they can't hold repetition of values. `dictionary` is a collection of key-value pairs where the keys have to be unique. They are the built-in solutions for store complex data structures in Python.

* How can you check if all the characters in a string are alphanumeric?

    : We can use the `string`'s built-in `isnumeric()` function which returns a True if all the characters in the string are alphanumeric, otherwise it returns False. Sadly it doesn't handle `.` which means a `string` that can be parsed to a float number will return a False if we check it with the `isnumeric()`.

* What is List comprehension?

    : List comprehension is syntactic shorthand to create a new `list` by iterating over an iterable. Its syntax is `[{expression} for item in iterable if {condition}]`.

* How does Dictionary comprehension work?

    : Dictionary comprehension, similar to List comprehension is a shorthand to create a new dictionary by iterating over an iterable. Its syntax is `{key: value for member in iterable [if condition]}`.

* What is the difference between list/set/dictionary comprehension and a generator expression in Python?

    : The generator expression is syntactically very similar to the list comprehension, the only difference is that it uses parentheses instead of square brackets. But it doesn't return a list, set or dictionary like the comprehensions do but rather a generator which is a special function that uses `yield` instead of `return`, but it can be also used as an iterable for example in loops or the `list()` constructor, so there are overlap with the usages of comprehensions and generator expression.

* What is a `Counter` in Python?

    : Counter is a sub-class to create hash table from an iterable, which means a dictionary-like object where the keys are the unique elements of the iterable and their values are the frequency of these elements.

* What does the `+` operator mean when used with strings in Python?

    : When we use `+` with strings it returns a concatenation of the two strings.

* Explain f strings in Python?

    : f strings in Python is a relatively new language feature as it's introduced with Python 3.6. It's great to simplify string formatting. In an f string any braces can hold a Python expression and it's return value will be put in the string itself. It's important to note that an f string should start with the keyword `f` right before the quotation marks.

* What are iterables in Python?

    : Iterables are value types whose instances we can iterate over. The most known, built-in iterables are `set`, `list`, `dictionary`, `string` etc. Python expects iterables in several different contexts such as in for loops or unpacking operations. Technically speaking an object is an iterable if its `__iter__()` function returns an iterator.

* What are Python function annotations?

    : Function annotations in Python is a way to attach type information to function parameters and return values. Types written in annotations don't force any type checking on Python during runtime, they have only informational purposes, for example an IDE can use them for static type checking or to propose valid attributes according to the variable's type.

* What is the `dir()` function?

    : `dir()` function returns a list of the names of the object's properties and methods without their values. It helps inspect objects, modules and functions.


## Functions and Scopes in Python✔

* What scopes are there in Python and how do they work?

    : Scope in programming the scope of a name (variable) defines the region of a program where the code can access it. In Python there is global and local scopes. The former means that the name is accessible from everywhere with no restrictions, while the latter means it's accessible from its own scope. A scope can be the body function or lambda expression. A name is accessible from other scopes if they are nested into the name's scope.

* What is the "golden rule" of variable scoping in Python (context: LEGB)?

    : When there is a name in the line of the code is run by it, the interpreter starts to search it through the relevant scopes. It does in the order described by the LEGB rule. The first is the Local scope that contains the names those are defined in the function or lambda expression, the second is the Enclosing scope which is the scope of the outer local scopes the current local scope is in, the third is the Global scope, and the fourth is the Built-in scope where the built-in defined names are. This order is important because it's possible to have the same names in different scopes and which one is used is depends on the LEGB rule.

* What do `nonlocal` and `global` statements do?

    : These statements are used to modify the behaviour of a Python scope by using them on names. When you try to reassign a global variable it results in creating a new local variable with the same name. If you want to change this behaviour you can use `global` statement to declare a variable in the local scope as the very same as the global one with the same name. When you declare a non-existent global variable this way it will be created and this is called declaring variable lazily (and considered bad practice). The `nonlocal` statement is basically the same but for names in the Enclosing scope rather than the global one. However, `nonlocal` statement is required to be used on an already binded non local name, so it's not possible to declare variable lazily with it.

* What is `pass` keyword used for?

    : In Python a body has to have some code in it. If we don't want to do anything in that body we can use `pass` statement that does nothing. A body literally no code in it would results in an error.

* If you need to access the iterator variable after a for loop, how would you do it in Python?

    : Since loops don't have their own local scope like functions do, the variables declared in a loop belong to the scope where the loop itself declared, and can be accesseb within that scope. The iterator or loop variable hence can be accessed like any other variable in the scope, and will have the last value it was assigned to it.

* What are closures in Python?

    : In Python inner functions are functions those are defined in the scope of another function, and as such they access to the outer function's variables since it's their enclosing scope. A function like that is belong to the outer function scope and can be accessed only from inside it. However, if the outer function return the inner function then we create a closure with this act. A closure means that a function retains access to its enclosing scope even when it's executed outside of that scope (and also we call the functions like that closures). It is important to note that the variables in the scope belongs to the closure is binded to the variable pointing to the closure, and this means it "remembers" their states between calls until the variable is active.

* What do packing and unpacking mean in Python?

    : In a python function we can set the possibility to get N argument and the function will handle them as a tuple (positional arguments) or dictionary (keyword arguments). The syntax is `*` for positional arguments and `**` for keyword arguments as the first character of the parameter's name.
    Unpacking is the counterpart of this feature, when a function needs N positional and/or certainly named parameters and we pass these arguments in function call with an iterable or a dictionary. In these cases we should use `*` and `**` in the arguments' names (they are usually be referred as *args and **kwargs).

* What is the difference between `yield` and `return` in Python?

    : In Python `return` works similar to how it works in other languages. It means that the function stop and return the value we specified in the `return` statement. There can be multiple `return` in one function and they are used to have a return value for every control flow branch (e.g. if-else branches).
    `yield` is more interesting and it's used to create generator functions. A generator function use one or more `yield` statement. A `yield` will halt the execution of the function and return the value specified in the statement, but it remembers where it's halted and the next time it will continue from there. It's important to notice that calling a generator function returns a generator object, and can be run by iterating over it (with a for loop or its `next()` function).

* Does the order of the function definitions matter in Python? Why?

    : If we talk about only function definitions then it doesn't matter, a function definition can use another definition that is defined later in the code. That's because the interpreter doesn't look for the variable as we described above when a function is defined, but rather it will do it when the function's code is executed.

* What happens when you try to assign the result of a function which has no return statement to a variable in Python?

    : In Python if a function doesn't have an explicit return value in it's current execution then it returns `None` implicitly. It's important to note that a function can have an explicit return value somewhere in their code but if the current run doesn't step into any of those branches then it will still returns `None` implicitly.

* What are the different types of arguments in Python?

    : There are five type of function arguments in Python:
    1. Default argument: it has a default value hence it isn't required to use in a function call (it can and then it will be reassigned to that value).
    2. Keyword argument: they are passed by naming the parameters when calling the function.
    3. Positional argument: they are passed without naming the specific argument and are assigned to parameters according to its position.
    4. Arbitrary arguments: arbitrary arguments are a set of arguments those are packed into an iterable parameter. The exact number of these arguments can differ function call to call. They can be arbitrary positional or arbitrary keyword arguments.
    5. Lambda function argument: an argument passed to a lambda function.

* How can you enforce a function parameter to be only keyword or only positional parameter?

    : In the function definition to define positional-only parameters we can use a "/" character as a "parameter" after them. If we want to define keyword-only parameters we can use a "*" before them.

* What are lambda functions in Python? How do you define them (syntacically speaking)?
    
    : In Python lambda functions are anonymous functions. They are defined by using the `lambda` keyword and to call it later it needs to be assigned to a variable (with a `=` operator or passing to a functionas an argument).

* What are Python's magic methods (aka dunder methods or special methods)?

    : In Python magic method is a method that is called implicitly by Python to execute a certain operation on a type, such as addition or initialization. This means the real difference between magic and "regular" methods lays in the way we call them: the latters are called explicity in the form of their name and parentheses, while the formers are called in some other ways (for example when we use the `+` operator then the `__add__()` method will be called on the number on the left in the background with the number on the right as argument).
    Some examples for magic methods: `__init__()`, `__str__()`, `__call()__`, `__len__()`, `__add__()` etc.

* Explain the `map()`, `filter()` and `reduce()` functions! How do they work in Python?

    : These are built-in higher-order functions designed to iterate over an iterable and execute a lambda function on every instance. They all have two mandatory parameter, a lambda function and an iteerable.
    1. `map()` returns a special iterator object with the return values of the executions of the lamdba expression it has got as argument.
    2. `filter()` returns a special iterator object with the element those case the lambda expression's returned `True` (or a truthy value).
    3. `reduce()` returns an aggregation of the elements of an iterable, the aggregation itself is specified by the lambda function (which gets two argument, the accumulator and the element).

* What is function annotation in Python?

    : In Python function annotation is a way to attach type information to function parameters and return values. They are part of the fucntion signature and can provide information on the type of the argument or return value to type checking tools like Pylance or IDEs like VS Code.


## OOP in Python✔
* How do you define a class in Python?

    : You can define a class with the `class` keyword in Python.

* What is an `object` in Python?

    : In Python, `object` is an instance of a class, and has the members of the class (the data and methods of it). In Python every value (and basically everything) is object type, even the immutable and atomic data types like the numerics or the `bool`.

* What is a `metaclass` in Python?

    : In Python everything is an object, even classes themself. A class whose instances are classes is called `metaclass` (e.g. most built-in value type as a class are the instance of the `type` metaclass - and `type` metaclass is an instance of itself). If we define a new class in normal way it will be an instance of the `type` `metaclass`. To make the new class to be an instance of other (custom) `metaclass` we need to use the keyword parameter metaclass while define the class. To create a custom `metaclass` we need to create a class that is the subclass of `type`.
    In Python defining and using a custom `metaclass` is rarely necessary or even optimal, but it can be useful in some edge cases.

* What is the difference between function and method in Python?

    : Method is a member of a class and acts within this context, for example it can use other members of the class, and its first parameter is always the self which gets the instance as argument. In short, method is an OOP and class concept while function isn't part of them.

* What are the `__new__()` and `__init__()` function in Python?

    : They are magic methods (see above). The `__new__()` function is used to create an instance of a class, and have the class itself as first parameter. It gets called automatically when we want to create a new instance, and has to return the newly created instance. The `__init__()` method is to initializate the new instance, for example set up the instance variables' values, and its first parameter gets the instance itself as argument, and does not return anything.

* What different method types are in Python?

    : In Python there are three different type of methods:
    1. Instance methods: they belong to the instance of a class, and as such they can modify the instance and the class data and can be called only on an instance, not the class itself. Its first parameter gets the instance itself as argument. To create an instance method we only need to define it in a class' body without any decorator.
    2. Class methods: they belong to the class, and it can modify only the class' data as its first parameter get the class itself. To create it we need to define in a class and use the `@classmethod` decorator on it.
    3. Static methods: they also belong to the class somehow, but they can't modify class (or instance) data, since they don't get any of them as argument. They are used mostly for utility methods like utility aspects of a class when it works on external data. To create a static method we need to define it in a class and use the `@staticmethod` decorator on it.

* What is an abstract class in Python? How do you create one?

    : Abstract class is a class that can't be instantiated and designed to be used as a superclass. It can have abstract classes which must be implemented by the subclasses of the abstract class. To create an abstract class we need to define a class that inherits the ABC (Abstract Base Class) form the abc module of Python, and to create an abstract class we need to define a method in an abstract class and use the `@abstractmethod` decorator on it (which is also in the abc module).

* How should you named protected and private variables in a class? What are the consequences of these naming conventions?

    : In Python the protected variable of a class is named starting with one `_`, and it signale the other programmers that it should be used directly only within its class and its subclasses, but technically it doesn't have any consequences. If you use `__` at the start of a variable's name, however, it doesn't only signal that it's a private variable and shouldn't be used directly outside of its own class but the interpreter rename it in the form of class' name + variable's name. So, while outside the class itself we can't reach it directly with its "normal" name we can with it's renamed version. This procedure (the renaming) is called name mangling, and this is th only special behaviour triggered by using these naming conventions.

* How many superclass can a class have? What is the syntax for inheritance?

    : In Python a class can have multiple many superclasses. We need to set superclasses in a class' definition after its name and between parentheses. The order of the superclasses is important because when the interpreter looking for a class member it will look for it in the first superclass (after the class itself), and the second and so on. This means if there are multiple superclasses have class members with the same name the interpreter will use the one that is ahead of the queue (the interpreter will also look for it in the superclasses of the superclasses). This order is called Method Resolution Order or MRO.

* How can you call the superclass' method (e.g. the `__init__()`) in a subclass' method? What happens when there are multiple superclasses?

    : You can use the `super()` method that returns a temporary object of the superclass on which you can call the superclass' methods. In case of multiple superclasses the `super()` returns a temporary object of the first class of the MRO. However, it's important to note that when we call a method on the `super()`'s return value then the MRO will be applied to that method instead of the class. It's true even when we save the return value to a variable and call the method on it. It's because in the background what `super()` returns is an instance of the `super` type that instance is bound to the class and instance we called `super()`, and as this it can look through all the MRO of the class every time we call a method on it.

* Describe the two ways to create getters and setters for a variable (get_x/set_x and property/setter decorators).

    : Since access modifiers are more conventions than any other thing we can say the getters and setters are also mostly for conventional things rather than rules forced on developers. We can create setters and getters with regular methods, but we can use the `@property` decorator to create getters and `@property_name.setter` decorator to create setters. With them their methods will be called when we call the property and when we reassign it.

* What is a metaclass? How do you define a custom one?

    : In Python every class is an instance of a class, and we call these classes which have class instances metaclass. For example type is a metaclass and it will be a custom defined class' metaclass by default. To define a custom metaclass we need it to inherit from a metaclass and it should implement the `__new__()` method which is responsible to instanciate a metaclass i.e. create a class.

* How do you define a class with a specific metaclass?

    : To define a class with a specific metaclass we can use the metaclass keyword argument during class declaration.

* How do you define and use interfaces in Python?

    : In Python there are no interfaces as distinct language elements like in Java there are. However, since there is multiple inheritance in Python we can use an abstract class that has only abstract method members as interface. Because of multiple inheritance this way a class can have multiple interface-like abstract classes along wiht one or more normal superclass.

## Decorators✔
* What are decorators in Python?

    : From a functional perspective decorators are functions which modify the functionality of other functions, or in other words decorator is a design pattern to achieve this goal. In a more tachnical one, a decorator is a higher order function that creates a new function using the one it has got as a parameter and returns this newly created one - so essentially it's a wrapper function creator function. Using decorators is a common way to add extra functionalities to custom function.

* How do you define a decorator? How do you use it afterwards?

    : To define a decorator we don't need any syntactic speciality, we define it as other functions but according to the decorator pattern. The decorator function gets an other function as argument and create an inner function which calls the function passed as argument, and the decorator function returns this inner function.
    To use a decorator after its definition we have two method. First we can call the decorator function with the to-be-decorated function as argument and assign its return value to a variable (and later use this variable as the function we wanted to decorate). The other, syntactically more straightforward method created specifically to this problem is using the `@` keyword along with the decorator function's name right above the function definition.

* What happens when there are multiple decorators for a function?

    : It is possible to apply multiple decorators on a single function. In this case it will work as though we wrapped the decorated function with the last decorator and wrapped this with the first one. In practice this means that the first decorator's code will run first before the decorated function and last after it.

* How do you create a decorator with an argument?

    : To create a decorator that can receive an argument upon calling, we need to define it as a wrapper function that defines and returns the "normal" decorator function (the one that receive the decorated function as parameter), and this function can have any type of parameters. This decorator function can be used with the `@` keyword as we mentioned earlier.


## Flask✔
* What is Flask?

    : Flask is a slim Python web application framework. It's often called micro-framework because its core is a minimal framework with only the essentials, but it supports extensions which can cover these parts of a full fledged web framework. It uses the Werkzeug python utility library which is a toolset for the WSGI (Web Server Gateway Interface) which is a calling convention for python applications to forward requests.

* What are the key features of Flask?

    : 
    1. Maybe Flask's most prominent key feature is its minimalistic design, providing only the essential tools and let the developer to build with the components they need.
    2. Built-in development server for debuggind and quick testing, it provides a live developer server that reloads every time when the code is changed.
    3. Jinja2 template engine for dynamically generating html pages which provides a native solution to create frontend pages in Python.
    4. RESTful Request Dispatching: this means a mechanism by an app routes the incoming (HTTP) requests to the appropriate handlers based on the RESTful principles.

* What is Flask-WTF?

    : Flask-WTF is an integration library of Flask and WTForm so the latter (the library) can be used in the context of the former (the framework). WTForm itself is a form validation and rendering library for Python applications.

* why do we use the `__name__` argument in Flask constructor?

    : `__name__` is a built-in variable that serves as the name of the module in Python. Flask needs this as its first parameter so it knows what belongs to the application and can look for resources (e.g. static files or templates) from there.

* What is Jinja Template Engine?

    : Jinja is a template language engine for html code that has placeholders for Python-like code, so in a sense its role is similar to what lore JSX has in React. But Jinja is static, and it's considered a different template language rather than a language extension like JSX. So Jinja is for staticly rendered but somehow dynamic web pages where the dynamic part is written in Python-like syntax rather than JavaScript.

* How do you create a route with Flask?

    : Creating an endpoint for a route is quite simple in Flask, we can use the `@.route()` decorator on a function, where the name of the Flask instance should preceede the point in the decorator. This decorator's first parameter is always the path (the route) we want the endpoint to handle. Flask will forward the requests with this path to the route and call the function to handle them, and will create a response with the function's return value as its body and send it to the requester.

* What does `url_for` do in Flask?

    : The `url_for` method is to prepare an url for a function dynamically by passing this function as the first parameter of it. It's especially useful when we want to use an endpoint from another (e.g. redirecting a request) and we don't want to remember where that endpoint is used in the code in case we restructure the paths and rename the route for that endpoint. By using `url_for` it will always point forward the actual handler function.

* How do you handle cookies in a Flask?

    : Flask has built-in methods to set or get cookies. With the `set_cookie()` method of the Flask's response object we can set cookies for that response. To retrieve cookies from a request we can use the Flask's request object's cookies attribute which is a dictionary object that holds the cookies sent with the request to the server.

* What is the use of `jsonify()` function in Flask?

    : `jsonify()` is a built-in Flask function that converts Python dictionaries or lists into JSON response object. These response objects has the correct Content-Type attribute (application/json) and a proper HTTP status code (200), so this function can be used to easily create a response with a JSON object as its body.

* How do you create a Session in Flask?

    : In Flask a session is created automatically when the handler function set a value for the Flask's built-in session object. This session will be open until the client's browser is closed or when the handler function clears the session object. If the Flask is set o have permanent sessions then a session won't close when the browser closes but rather it will close when it expires.

* What are application context and request context in Flask?

    : The application context is the context that holds the set up of the Flask application which currently run. It can be reached via the `current_app` proxy because in some cases the current instance of the application cannot be imported directly. The request context has a similar role but for the actual request. It exists during the rewuest itself and the data on the request can be reached through it.

* Describe the Flask-JWT, Flask-SQLAlchemy and Flask-Bcrypt extensions!

    : While Flask is a lightweight framework it has a lot of extensions we can use to expand its functionality, for example these extensions:
    1. Flask-JWT is an extension for autentication and authorization functionality with JSON Web Tokens.
    2. Flask-SQLAlchemy is an extension that provides an interface to use SQLAlchemy, the most poplar ORM for Python in a Flask application.
    3. Flask-Bcrypt is an extension for password hashing and verification functionality for Flask applications.


## Pandas✔
* What is Pandas?

    : Pandas is an open-source library for Python for data manipulation and analysis first released in 2008. Its name is derived from the term "panel data". It's built on NumPy, another Python library for mathematical operations on large multi-dimensional arrays.

* What are the key features of Pandas?

    : Pandas has several features but its key functionalities are these:
    1. Data cleaning: Pandas has various functions to clean data we want to work with, for example fill or drop missing data or search for duplications.
    2. Data selection: Pandas allows for a range of fine filtering and selection functions e.g. `.loc()` or `.apply()` which help to filter and select data.
    3. Data aggregation: Pandas has a robust body of aggregator functions from the simple ones like `.sum()` or `.max()` to the grouping functions and the `.agg()` function that execute a custom aggregation function on the data.
    4. Data visualization: Pandas integrates with the popular data visualization library, Matplotlib.
    5. I/O operations: Pandas supports I/O operations on several popular file format e.g. csv, excel or JSON.

* Describe the `Series` and `DataFrame` Pandas data structures!

    : Pandas has two main data type. `Series` is a one-dimensional labeled array with homogenous data. `DataFrame` is a two-dimensional data structure with heterogeneous data by its columns (in a column the data is still homogeneous), so it works as a relational data structure. It's important to note that a column of a `DataFrame` is also a `Series`. In pandas there is a lot of function those have implementations for both data types and works differently (e.g. most of the aggregations works on `DataFrame` and will be applied to every columns one by one).

* How do you retrieve metadata of a `DataFrame`?

    : You can use the `.info()` instance method of `DataFrame` to get metadata of a `DataFrame` which will show the number of rows of it along with its columns with their attributes.

* How do you handle missing data in Pandas?

    : In Pandas there are built-in functions to handle missing data. We can use `.isnull()` method to find missing values, `.dropna()` to drop cells with missing values or `.fillna()` to fill these cells with some data (it can be an aggregation of the column's complete data).

* How do you filter rows in a `DataFrame`?

    : There are two common ways to filter data in a `DataFrame`:
    1. Boolean indexing: we can set a condition between square brackets after a `DataFrame` and it will return a filtered version of it. We can set multiple conditions combining them with the `&` keyword.
    2. `.query()` function: with it we can query the `DataFrame` allowing for more complex filtering.

* Explain the `groupby()` function in Pandas.

    : `groupby()` function returns a pandas groupby object with groups based on the argument we added to the function (e.g. one column of the `DataFrame`). This object acts like a `DataFrame` in many cases but not always. When we call an aggregator function on a groupby object it will be executed on every group.

* What are common file formats Pandas can read from or write to and what built-in functions should we use?

    : We can use built-in functions to read csv (`.read_csv()`), excel (`.read_excel()`), SQL (`.read_sql()`) and JSON (`.read_json()`) and other functions to write csv (`.to_csv()`) and excel (`.to_excel()`).

* What are the `.apply()` and `.applymap()` functions in Pandas?

    : `.apply()` function allows applying a function to all elements of a `Series` or all rows/columns of a `DataFrame`. `.applymap()` function is for only `DataFrames` and allows applying  function to all cell of it.

* How can you handle duplicate data in Pandas?

    : We can search for duplicate data with the `.duplicate()` method which returns a `Series` of `bool` values based on if an element (in case of a `Series`) or a row (in case of a `DataFrame`) is a duplicate or not. With this combining some filter methods we can filter out duplicates easily.


## Websocket and Socket.io in Python
* What is WebSocket, how does it differ from HTTP?
* What is some common use case for WebSocket?
* How does the WebSocket handshake work?
* What is the difference between WebSocket and SSE (Server Sent Events)?
* What are the ping/pong frames in WebSocket?
* What fallback mechanisms can be used instead of WebSocket if it isn't work?
* What is Socket.io?
* What are the key features of Socket.io?
* What is a socket id in Socket.io?
* How do you send a message to a specific client in Socket.io?
* How do you define an event handler in Socket.io?
* What are rooms in Socket.io, and how do you use them?
* What is `socket.broadcast.emit()` and when should it be used?

## C with Python
* What is CPython's Foreign Function Interface (FFI)?
* What is Python C API?
* What are the advantages of writing modules in C which can be used in Python code afterwards?
* What are the mandatory parts of a C extension module?
* How can you parse and use python objects in a C extension module?
* How can you use pandas objects in a C extension module? What is the difference between pandas and 'normal' python objects?
* How can Python Interpreter use a C extension module?
* What are the pitfalls of using Python C API?

## Cython
* What is Cython?
* What are the syntax variants for Cython? How do you use them, what are the advantages and disadvantages of them?
* How do you do static typing in Cython? Why is it important?
* What is the difference between `cdef` and `cpdef` in function declaration?
* How do you call C functions in a cython code?

## Seaborn

## Testing
* What are Python assertions?
* What is pytest and unittest?
* What is timeit module? How can we use it for testing?
