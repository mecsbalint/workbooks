# OOP Basics with Java questions

## Java ecosystem✔

- What is the JVM?

    : Java Virtual Machine is a special platform which runs the platform-independent bytecode program created from the code written in Java (see below). We call programs with this function interpreter. JVM itself isn't platform-independent but there is a version of it for every main OS. JVM has an important component called the Garbage Collector which delete objects from the memory during runtime when they are no longer needed.

- What does Java compilation mean?

    : Compilation is a process that converts Java source code into bytecode which can be run by the JVM. First the Java compiler check if the syntax and semantics of the code is correct, the exceptions that occur during this time we call compilation-time exceptions. If there is no problem with the code then the compiler translate it into bytecode and write it into .class files.

- What is Java bytecode?

    : Bytecode is a platform-independent programming language which isn't human-readable. The source code written in Java is translated into this language and the JVM interpreter run this code. Bytecode is the reason the Java can be a platform-agnostic language but it runs nearly as fast as native applications.

- What is the difference between the JRE and the JDK?

    : JRE or Java Runtime Environment is a set of tools with which we can run Java program on our system. It includes JVM and integration libraries to achieve this goal. JDK or Java Development Kit is a toolset to compile, debug and run a program written in Java (or other language which is translatable to Java bytecode). Therefore JRE is a part of JDK, but the latter also contains a compiler, a debugger, an archiver along with some cardinal packages like java.util or java.lang.

- What is the `Iterable` interface?

    : It is a commonly used interface introduced with JDK 1.5. If a class implements it make its components iterable. Collection is a subinterface of iterable, so every class which implements Collection or one of its descendants can be iterated over.

- What is the `Collection` interface?

    : The Collection interface is one of the root interfaces of the java collections framework. it isn't implemented directly but most of the commonly used collection classes implement one of its subinterface such as List, Queue and Set. Basically Collection is the base of the common language on which we use lists in Java. A Collection can't hold primitive type values so in case we want to use one of its implementation on primitive types we have to use one of the wrapper classes (see below).

- What is the `Map` interface?

    : Map interface maybe the only widely used interface for collectibles which isn't a subinterface of Collection. A class implementing Map interface is the closest thing to a JS object (or more like Map). It is a series of key-value pairs where the key has to be unique and both the keys and values has to be the same types (but the two group's type can be differ, hence we has to give two value type during declaration). Null is considered one valid value in case of reference types. We can reach the value of a key with the Map's name and the key. Map implementations doesn't have a fix order by default.

- Compare sets, lists, and queues in Java.

    : All of them are the subinterfaces of Collection, but they have different goals. List interface is to create a dynamic list which is iterable and has a fix (or repeatable) order and elements can be removed from or pushed to anywhere in the list itself. Queue is for lists where the starting element can be removed and element can be added to the end (and vica versa in the case of its subinterface Deque). Set is for a list where every element is unique. It is important to note that a lot of classes implement not only one of them but multiple number of them (e.g. LinkedList implements Deque and List). While in most cases all or most of them are capable to handle a list of elements in our application it is recommended to always choose the class which is the most suitable for the intended role.

- Compare `ArrayList` and `LinkedList` in Java.

    : ArrayList and LinkedList are both implementations of the List interface (though LinkedList also implements Deque). So they have the same goal but they achieve it with different solutions. ArrayList stores its elements in an array and create a new one if it becomes too small for the elements. It is optimal in memory usage and faster if we want to iterate over the elements. LinkedList stores its elements in a data structure doubly linked list which basically means a chain of elements where every element stores its value and the previous and next element in the list. With this solution there is no need to store the elements in a static array hence it doesn't need to create a new, bigger one and migrate the data to it. LinkedList is optimal to modify the list (especially when we want to remove from or add to the middle of the list).

- Are sets sorted in Java?

    : No, Set interface doesn't require of implementation of some kind of sorting method or mechanism. However, there are classes which implemented the Set interface (hence functioning as sets) while implemented another interface with this functionality. The TreeSet is one of them which can be sorted, but it's not a feature inherent to the Set interface.


## Language features✔

- What control statements are available in Java?

    : There are three types of control statements in Java:
        1. decision making statements (if-else, switch) where the code decides which part executes
        2. loop statements where a block of code is executed repeatedly as long as the condition is true. While and do-while loops are designed to repeat themself for unforeseen times (e.g. until a search function doesn't find the wanted item) while the for and for-each loops are designed to run for a certain amount of times (in the case of the latter this number is the length of the iterable)
        3. jump statements (break, continue) transfer the execution control to other part of the program, in other words they break the current flow of the program. Break statement terminates the loop or switch statement and transfer the control tho the next part of the code. Continue terminates only thee current iteration of the loop but doesn't terminate the loop itself.

- Compare the different looping constructs in Java.

    : There are four type of loops in Java:
        1. for loop: it has an initialization, a condition and an increment part. The first is executed only one time before the first iteration, the condition is checked before every iteration, and the increment is executed after every iteration. This loop is for repeate a code a certain amount of times, but it is also flexible.
        2. for-each loop: it iterates over an iterable and for every iteration it has the current element of the iterable. It is good for executing a code on every items in a list for example.
        3. while loop: it has a condition which is checked before every iteration and it runs repeatedly until the condition is true. This is the most basic and hence the most versatile type of loops which can be used for any purpose. However because of the other more specialized loops it is mainly used for repetition when the desired amount of repetition at least partly depends on some kind of external influence (e.g. user input, or the iterable's true length isn't known at the start of the while loop etc.).
        4. do-while loop: works very similar to the while loop but it's condition is checked after every itration, which in practice means that the code will be executed at least one time.

- Compare the different conditional constructs in Java.
    
    : There are four conditional constructs in Java:
        1. if: it execute the condition part of the statement and if it returns true then it execute the code in the body.
        2. if-else: it works similar to if but when the execution of the condition returns false it executes the code in the else's body.
        3. else-if: it is a variant of the else statement in if-else conditional construct, we can add another if statement as the executable body of the ele statement. With it we can make if-else-if statement with indefinite length.
        4. switch: it doesn't have a condition but an expression which has a value which can return any type of value not only booleans. The switch statement has case or cases and every one has a value, and this value is compared to the expression to say if they are the same. If they are and hence the comparison returns true then the code is executing from there until it is terminated with a break or the switch statement ends. There is a special part of the switch which is the default, which works similar to a case but has no value and its code will be started executing if the switch isn't terminated before that.

- What is a `while` loop?

    : see above

- How do you manually break out of a loop?

    : with the break statement which terminates the loop and pass the control to the next element of the code

- What does the `var` keyword mean?
    
    : The var is actually not a keyword but a reserved type name which can be used for dynamic-like typing in the othervise static typed Java. It isn't true dynamic though because a variable declared with this type will get its "true" or final type during compilation time. The compilator will assign a type to this variable which is compatible with every value it can get during the run (e.g. if there is an if-else statement which is a dependent what value will be assigned to this variable then both branch will be considered). One quite limiting use case for var is when we try to cut off word repetition during variable declaration with assignment of a constructor's return value. E.g. when the line is Book book = new Book() we should just write var book = new Book() which is more readable especially if the class' name is long and complicated. But the var should be only used if the type of the variable is evident for a different reader.

- What are _lambda expressions_? How are they used in Java development?
    
    : Lambda expression is a way to instantiate a functional interface (which is an interface with only one method signature). During an instantiation like this the method passed as lambda expression will be the implementation of the sole method of the interface and with this it creates a full implementation of it. This solution is the most used (and only?) way to create higher order functions where one of the argument is a method itself. A lot of videly used library's tools use it (e.g. Streams' map, reduce etc methods) to create versatile methods with more generalized use cases. In other words it's crucial in functional programming in Java.



## Type system✔

- What are primitive types in Java? Give some examples.

    : There are eight primitive value type in Java. They are not considered as objects and they are immutable non-reference value types.
        1-4. bytes, short, int, long - they hold an integer number and the only difference between them is their size (8, 16, 32 and 64 bits) hence their range. Their default value is 0 (0L in the case of the long).
        5-6. float, double - they hold a floating point number. While float occupies 32 bits it can store a floating point with up to 7 decimal digits. The double's corresponding values are 64 bit and 17 decimal digits. Their default values are 0.0F and 0.0D.
        7. boolean holds a boolean value which is either true or false. Its default value is false.
        8. char is a single 16-bit unicode character. Its default value is 'u/0000'.

- What is the difference between primitive types and reference types?

    : Primitive value types' actual value is stored in the stack, they are immutable. They have an actual size in the memory (though it's size isn't always the same) which they can't exceed, if we try to add a value to a primitive bigger than it's size limit the variable will overflow. There are eight primitive value types in Java and can't be created more by a programmer.
    The reference value types value is a reference/memory address which points to an object in memory. There can be many reference type, some of them are Array, String, classes, interfaces, enums etc. We can create classes which are reference data types. They are mutable.

- What is a class in Java?

    : Class is kind of a blueprint/constructor for objects as data structures. We can define what kind of data an instance of the class should have and how can an instance act. A class has members, which are the components's of it: most of them are field, constructor or method. Class along with the object is the most important construct in an Object Oriented Language. In practice there are classes not for more instances to create from them but to act with its methods. They can be even used without any instanciation.

- What is an object in Java?

    : An object is an instance of a class. It is instanciated by the rules of the class. An object can have its actual values for fields of the class but it shares the methods and the static fields with the othr class instances. An object can inherit its class' superclasses' members. We can imagine the class-object relation as the value type-value relation.

- What is a constructor?

    : The constructor is a special method in a class which is used to create instances of the class. It has no name (only return value which is a class instance obviously) and can be called with the new keyword and the class' name. Every class has a base constructor which only instanciates an object of the class, and it runs before the custom constructor we actually called. In a subclass we can call the superclass' constructor with the super() keyword.

- What is an `enum` in Java?

    : Enum is a special kind of class which can't be instanciated but it has constants which are works like prefabricated instances of the class. We usually use enums for predefined static data, for example the roles in our company if the app shouldn't change them or add to them a new one. An enum constant can have properties which can be used with the enum's fields and constructor. With them the enum will "instanciate" every constant it has. We can get an array of all constants (or the "instances" of them) with the .values() method.

- Explain the difference between a class and an enum.

    : Enum is a special class which is for predefined "instances", while class is a broader category (see above) and it is for create data blueprints which can be used and instanciated during runtime.

- Explain the difference between a class and a record.

    : A record is a special class type with the purpose of hold data. It is created with the record keyword instead of the class one and it has at least one parameter (these parameters become private final fields and a record can't have normally declared instance field), and it automatically generates constructor and getter, tostring(), hashvode() and equals() methods. We can define other methods and static fields, but the above methods are "built-ins" in a record. We can define another constructor but it has to call the generated one.
    These particularities show how the record differ from a regular class.

- What are interfaces? Why should we use them?

    : Interface is an abstract class-like type with a different purpose from class. It can have only public constant fields and public abstract methods (though it is possible to define a default implementation of an abstract method in the interface) along with static methods. Hence an interface most likely doesn't hold any logic to implements its own method signatures and its purpose is to being implemented by classes (a class can implement multiple interfaces). When a class implements an interface it has to implement all methods of it (except for abstract classes but their subclasses inherit this obligation). We can call it a contract between the class and the outside world which contract is enforced during build time. An other class which want to use an interface functionality on a class can depend on this contract that the said class will have the methods it wants to use (and hopefully they are implemented in a meaningful way).

- What is inheritance?

    : Inheritance is a concept tied to the classes and interfaces. It means that a class (subclass or child class) inherits the members of another class (superclass or parentclass), this means it doesn't inherit the constructors but it can call them with the super keyword. A subclass can override a superclass' methods (except if they are final) and has an obligation to implement abstract methods of its superclass (except if the subclass itself also an abstract class). A class can have only one direct superclass but can have as many subclass as we like. A class is declared as another class' subclass in its class signature with the extends keyword and the superclass' name. It is important to note that although the subclass inherit all members of the superclass but inside the subclass we can reach only the public and protected members by default (and the package-private ones if the subclass is in the same package as the superclass).
    If a class doesn't have a declared superclass then its direct superclass will be the Object class, this means that every class is a subclass of the Object class indirectly or directly.

- Is multiple inheritance allowed in Java?

    : Not directly because a class can have only one direct superclass. However, since a subclass inherits its members from its superclass therefore a class always inherit all members from all ascendant class because its parent already has them.

- What is a static class member?

    : Static class members are members with class-wide instances unlike the regular members which are object-wide instances. This means there is only one copy of a static class member which is used commonly by all class instances (and subclass instances). A static member can be called without instanciation of the class (using the class' name) and while they also can be called with class' instance the former is considered better cleancode-wise.

- Can a static method use non-static members?

    : No because a static method doesn't need an instance to be called while a non-static member is tied to the actual instance of the class, so calling a non-static member in a static method could cause incomprehensible code. 

- What does the `final` keyword mean in Java?

    : Final keyword can be used for variables, methods or classes - these are different contextes but they are similar in the sense that this keyword is to make the element impossible to change. A final variable can't be reassigned (although its value still can be modified in case of reference types); a final method can't be overriden; and a final class can't be a superclass. A final variable has to be initialized during the declaration or by the class' constructor.

- What does the `abstract` keyword mean in Java?

    : Abstract keyword can be used for methods or classes. An abstract class can't be instantiated and only an abstract class can have abstract method. The latter can't have body and works similar to an interface's method signature - it has to be implemented if a non-abstract class inherited it.

- What is _overloading_ in Java?

    : In Java a method has to have a unique method signature (or the name + parameters part of it), which means there can be two methods with the same name in the same scope if their parameters differ in number and/or in type. This means we can create similar methods with different parameters but with the same name to achieve the same (or similar) goal, and this is called overloading. It is particularly useful since the Java is a static typed language. It is important to note that constructors (since they are special methods) can also be overloaded which is useful when we want to have multiple way to create an instance of the class.

- What is _overriding_ in Java?

    : Overriding means when a subclass implements a method which is already defined in its superclass (so it is not an abstract method's implementation). To override a method the new method's whole signature has to match the to-be-overriden method's (except access modifier which can be more permissive in the overriding method). Final and static methods can't be overridden but a static method can be hidden (shadowed) by a static method in the subclass.

- What is the difference between overloading and overriding?

    : As we saw above they are quite different phenomenons, the method overloading is for create multiple different methods with the same name and use them, while overriding is for create a subclass-variant of an already defined method which can be used with this subclass' instances. The former is part of the compile time polymorphism while the latter is runtime polymorphism.

- What is `null`?

    : Null in Java is a special value which can be assigned to reference type variables and this is the default value of a reference type variable - a primitive variable can't have null as its value. Null basically means there is no object tied to the variable (it doesn't have the object's reference as its value). It is to show when a variable's object "does not exist".

- Compare the access modifiers in Java.

    : In Java there are four access modifier for class' members which are incrementally permissive:
        1. private: the most strict modifier, this means the class member is only accessible in the class itself
        2. default or package-private: it means the class member is only accessible in the class and in other classes in the same package. There is no keyword for this modifier and if there is no other access modifiers in a member declaration it will be default.
        3. protected: the member is accessible for the class itself, the other classes in the package and in the subclasses.
        4. public: the member is accessible from everywhere
    Classes can also have access modifiers but only two kind: public and default.

- What is the default access modifier in a class?

    : The class' default access modifier is the same as class member's, the package-protected which means the class is accessible only from the same package.

- What is the purpose of the `equals()` method?

    : equals() is the Object ancestor class' method which therefore can be implemented by any other class. This method exact work will differentiates by these implementations but its intended use is to make objects comperable by their value.

- What is the difference between `==` and `equals()`?

    : The `==` is an operator in Java which returns a boolean based on if the two side is the some or not. It can be used a various purpose but it is good for comparing variables. However, while comparing primitives with this operator is pretty straightforward using it for reference types could lead to unwanted reasults. The `==` operator will compare the variables very value (which is the value stored in the stack) and this means that reference types will be compared by the reference they hold and not the data their objects' has. So it is possible that if we compare two reference type variable which point to two different, but in their inherent values equal object it will return false while we should want other result.
    This is where the `equals()` method differs from the `==` operator. As we said above it's actual works denpends on the implementation in the actual class but usually it is implemented in a way that it checks if the values a class' instance holds are are same as the ones in the object they compared to and if they are the same class' instances. However, the method's original definition in the Object class simply use the `==` operator on the two objects so it isn't differ from plainly using the `==` operator.

- What is the difference between `long` and `Long`?

    : Sometimes we want to use primitive values where only reference type values are acceptible. For situations like this every primitives has a wrapper class counterpart (Integer for int, Character for char etc.) and for long it is the Long class. It also has a series of useful methods to deal with a long number. Long holds a single long value.

- Which can store bigger numbers, `long` or `Long`?

    : Because Long stores its number data in a long type field (since it is a wrapper type class) the biggest number they can hold is the same.

- What kind of packages do you know under `java.util.*` ? Bring at least 3 examples.

    1. stream package: this package has the tools to use functional-style operations on streams of elements.
    2. random package: this package contains tools for random number generation.
    3. regex package: this package has classes for use regular expressions with character sequences in Java.


## Architecture✔

- Explain the Single Responsibility Principle.

    : SRP is one of the SOLID principles which is a guideline to build software with Object Oriented Programming. This principle says that a class should have only one responsibility instead of multiple of them. A class with multiple responsibility what are independent (or at least separable) from each other is harder to understand, modify or replace in the software. It is also really good for unit testing.

- Explain the Interface Segregation Principle.

    : ISP (the I in SOLID) says that a class shouldn't have to implement methods it doesn't use. If there is an interface with more methods and we want to use only some of them with a class then we should create more interfaces to achieve this goal (e.g. we can create a superinterface with only the necessary methods and a subinterface with the others for other classes to implement).

- What is _composition over inheritance_?

    : This is a design principle especially useful in OOP which says that in some cases we should pass to a class functionality by creating a field in it with another class' instance (composition) instead of creating a subclass for it (inheritance). In real-life examples deciding which to use is quite simple: if something is a subcatergory of the other (e.g. dog and animal) then we should use inheritance to establish the relationship between them; if it is the part of the other (e.g. tail and dog) then we should use composition. With composition it is easier to create more modular code especially if we also watch for the Dependency Inverson Principle (see below). It is also useful in testing where we can easily replace this kind of class instances with mocks or fakes. Lastly it is useful when we want to use the functionality elsewhere.
    However, in cases when the relation is clearly subcathegory-y then we should use inheritance. 

- What is a model class?

    : Model class is a class of which main purpose is to hold information of a real world (= outside of the program's scope) object with only minimal low level business logic. In Java there is an ideal and somehow limited built-in solution for this, the record.

- What is a service class?

    : Service class is a class in Java and its main purpose is to provide a way for the client to interact with some of the software's functionality. It usually doesn't have instance field since it has no purpose to hold data on its own but instead it is a "platform" to use data through one or more model classes. A service class usually serve as a connection between (mostly model) classes.

- Explain the Open/Closed Principle.

    : This principle (the O in SOLID) says that a class should be open for extension, but its functionality shouldn't be changed. If a class already has a function then removing this function could affect the system and cause problems.

- Explain the Liskov Substitution Principle.

    : This principle (the L in SOLID) says that a subclass should be used as its superclass. In other words a subclass should have the functionality of its parent. This principle is inherently supported by Java since subclass instances can step into the superclass position and every subclass inherit every member of a superclass.

- Explain the Dependency Inversion Principle.

    : This principle (the D in SOLID) says that a class using another class as a tool should not depend on it, and a functionality's implementation should depend on the abstraction not vice versa. This means when we use composition the high-level class' field shouldn't wait for a specific low-level class but an implementation of an interface this low-level class implements. With this it's easy to replace the class with another which implements the same interface and the high-level class can remain untouched (this is especially useful in unit testing).

- What do we mean by the Gang of Four (GoF) Design Patterns? Can you name some of these patterns?

    : The GoF Design Patterns are a set of OOP-led solutions for common programming tasks or problems defined in a textbook in 1994, the 'Design Patterns: Elements of Reusable Object-Oriented Software' (its four author's called Gang of Four). In this book there are three groups of design patterns:
        1. Creational Patterns (e.g. Factory Method Pattern, Abstract Factory Pattern or Singleton Pattern): these patterns are for the part of the program which is responsible to create objects.
        2. Structural Patterns (e.g. Adapter Pattern): these patterns are to putting together different parts of the code to build something bigger and more complex.
        3. Behavioural Patterns (e.g. Chain of Responsibility Pattern): these patterns are to set up how the different parts of the software should work together.

- What are the risks associated with using the GoF design patterns?

    : There are some mistakes we can do while try to using design patterns, for example we can use design pattern where it's not necessary or not use the right design pattern. We can also add unnecessary complexity to the code when we misuse a design pattern which also hurts the readability of the code. Another pitfall of these design patterns is when we concentrate too much on them instead of the actual design problem we want to solve - so we can easily become too didactic.

- What do we mean by YAGNI?

    : It literally means 'You aren't gonna need it' and is a principle of extreme programming. It says a functionality should be implemented only when and if we want to use it, otherwise there will be occurences of unnecessary works.

- What do we mean by SLAP?

    : SLAP (Single Level of Abstraction Principle) says that a method (or class) should operate in one level of abstraction. This in practice means that it should not have logic which belongs to lower level operations relative to its highest level of abstraction. A method can avoid it by call other methods (likely but not necessarily from other classes) which will do the lower level job for it. In terms of class we can use dependency abstraction to avoid it, use an interface implementation in the class and let the implementation itself to handle the lower level task.

- What do we mean by KISS?
    
    : Its an abbreviation for 'keep it simple, stupid' and is a principle what is somehow similar to Ockham's razor. It says that a structure (e.g. a software) should be built as simple as possible to have the capability it should have. It seems a bit contradictory with some OOP principles but if we think about it as not a structural paradigm but as a principle for what functionalities a software should possess then there isn't much contradiction. So, if a software should be able to do A and B we don't need to program the functionality of C.

- What is the Repository Pattern?

    : Repository Pattern is a popular pattern in software development and is used to have an abstract layer between the app and the stored data and also to have the data access logic in one place. It has three main components, the repository interface, the implementation of this and the entity model (or models) which represent a business entity (e.g. a user, a product etc.) and holds the data that was read from the database (or from where we store the data). The implementation is made specifically for this kind of database and data, but in the other parts of the software it is abstracted away with the interface. With this pattern we can make it relatively easy to replace the way we store, reach and manipulate data.
    The difference between DAO and Repository pattern is that the latter is a higher level abstraction. The DAO is for execute one action on a database (like get all the books or delete a specific one) while Repository is for use these retrieved data to perform some more complicated business logic. The Repository usually has some kind of DAO internally.

- What is a CRUD interface?

    : A CRUD interface is an interface which has the methods for basic data manipulation (create, read, update and delete). A DAO object, for example usually has these functionalities but it can have others too. A CRUD interface is a good tool to abstract these basic functionalities in a software structure and delegate their implementation to the actual data handling object (e.g. a DAO object).



## Unit testing✔
- Why is unit testing a good practice?

    : Unit testing basically means one tests the software's different parts separately, not the whole. It helps to determine the source of the error by this separation, but it also helps to think the different parts of the code well, differently. Unit tests can funtion as code documentation since it can be seen as a string of expectations how should the code work in different situations, and as such it is a good tool for other people to understand the structure and logic of your code. Using unit testing effectively also kind of forces the developer to build up their project in a more separable manner, in this sense it helps in refactoring the program to a more versatile and flexible one. Another good thing about unit testing is it is supposed to be faster than other kind of tests. E.g. when we want to test a software which has database using but the test's scope isn't cover it then we can ignore that part by mocking for example.

- What is JUnit?

    : JUnit is the most popular test automation framework for Java (it has its counterparts for other languages either). It has a powerful vocabulary of assertions as well as annotations to identify the different parts of a JUnit test (e.g. test cases, tasks to be performed before every test cases etc.). JUnit promotes the concept of testing during the coding process alternately doing them as well as write test cases before implementation. Unfortunately it is incapable to test UIs or database interactions directly.

- What is a parameterized test?

    : Parameterized test is a test form where the test case is run multiple times with different parameters. It is especially useful when we want to test a code part's behaviour in different scenarios. It helps to avoid code repetition and all the negative effects it has. A parameterized test is run as many times as the number of parameter sets.

- What options do you have in JUnit to create parameterized tests?

    : We can use the JUnit's `@ParameterizedTest` annotation instead of the regular `@Test` to create a parameterized test. After it we need a source of parameters and for it JUnit has a series of annotations (e.g. `@CsvSource` or `@ValueSource`) which will define the parameter data or the source of it (e.g. a method in case of `@MethodSource` annotation). There can be multiple source for one test case. The test case method with these annotations has to have the appropriate number (and type) of parameters.
    Alternatively we can use JUnitParams and `@Parameters` but it is considered an older solution which is replaced by `@ParameterizedTest`.

- What is _mocking_?

    : Mocking in unit testing means creating a test double for a unit (in Java it is most likely a class) on which the to be tested unit depend. A mocking object mock the original to an extend in its interaction with other elements but its internal operation is wastly differ (optimally it is much more simplistic).

- What is the difference between _mocking_, _stubbing_ and _faking_?

    : There are different kinds of mocking objects (or test doubles). The stub usually means a the test double has some predefined behaviour which doesn't depend on the input it receives - e.g. it has a method which is callable, it can have parameters but it will return the very same value or execute the same action. The mock more or less the same but its behaviour can differ based on the input it receives. And fake is an implementation of the same functionality as the to be mocked element has but in internal operation it has some shortcuts (and shortcomings compared to the original). For example a fake object of a DAO class wouldn't use any database source but it will store the data it receives the same way in the memory.
    It is important to note that these expressions are not completely formed or matured and in many cases they are used differently, interchangeably or swapped.



## Databases✔

- What are relational databases? What are their advantages and disadvantages?

    : A relational database is a collection of data organized in predefined relationship. The data is stored in relations of attributes and records where each record has a value which belong to an attribute. Usually records represent elements, objects or units which are to be stored as data and attributes are the, well, attributes of these objects. These relations (tables) can be interconnected (related) each other by having a common attribute (most likely an id dedicated for this purpose).
    One of the most advantages of a relational database is data integrity because to a relational database it's relatively easy to apply constrains like unique ids etc. Another advantage of this database model is the SQL itself which is a strong and standard interface to use data stored in relational database. A relational database is also easily expandable without interfering applications which is already using it. And lastly it is a widespread form of storing data which is an advantage by itself.

- How do you associate entities to each other in a relational database model?

    : They are associated to each other by one of their common attributes. From records of two entities we can create one series of records where one has the attributes of both entities and the values are based on the records connected to each other by the common attribute. There can be one-to-one, one-to-many and many-to-many relations between tables, and for the latter it is needed to have a junction table as an intermediary.

- What are tables in a relational database?

    : Tables (or relations) are the base entities of a relational database. It is basically a set of records that share the same attributes.

- What is a _primary key_?

    : Primary key is an attribute which is also a unique id of the record. By this every record is identifiable from outside or from an other relation. In most relational databases every record must have a value for this attribute and most database programs create them automatically when a new record is inserted to the table.

- What is a _foreign key_?

    : Foreign key is an attribute in a table which refers to another table's primary key attribute. This connection makes it possible to associate two table to each other. A value belonging the foreign key attribute has to exist in the foreign key's counterpart primary key attribute.

- What does the SQL abbreviation stand for?

    : SQL means Structured Query Language, this is the most used language to manage data stored in relational database (it is a domain-specific language made only for this purpose).

- What are some of the SQL database providers that you’ve heard of?

    : Maybe the most popular opensource providers are MySQL and PostgreSQL while the popular commercial ones are Microsoft SQL Server and Oracle.

- What are SQL data types? Are there any differences in data types between different SQL databases?

    : In relational databases each attribute must have a name and a data type and records can only store data from this type in this attribute (column). This ensures that the data from each attribute are comparable and seriazable which is crucial in the expansability and extensive usability of the database. It is also improves performance because the search algorythm can depend on what kind of data it has to use. There are numeric, character/string, date/time, binary, boolean and other special data types in an SQL database. Different SQL databases (providers) have different data types but the common ones are similar.

- What are _constraints_ in SQL?

    : Constraints are rules deciding what kind of data an attribute can have. Aside from data type there are more specialized constraints such as primary key, foreign key, unique or not null. There can a custom constraint also be created by the `CHECK()` keyword. These constraints have to be set during the attribute creation.

- How can we program different SQL databases in Java?

    : First we need the Java Database Connectivity driver for the specific database provider we want to use (in case of a Maven project the dependency of the database provider usually contains it). After this we need to establish the connection between the database and the Java program (we can use the `DataSource` and `Connection` interfaces for this). After this we can create and execute SQL statements (queries) in the Java program and handle the results (it is recommended to use `PreparedStatement` for this is sake of query purity).

- Which SQL statement is used to create tables? Describe the syntax briefly.

    : We can create table with the `CREATE TABLE` statement following by the table's designed name and lastly the set up uf the columns between parenthesis (the order for each column is column's name, data type, constraints, default value).

- Which SQL statement can be used to insert values? Describe the syntax briefly.

    : With the `INSERT INTO` statement followed by the table's name and columns' names we want to set up data for the new row. After this we can use the `VALUES` keyword to set up the actual values for the new row.

- Which SQL statement can be used to update values? Describe the syntax briefly.

    : We can use the `UPDATE` statement followed by the table's name. It has two other keyword, the `SET` followed by the columns' names and the value we want to change the current ones, and the `WHERE` keywors with which we can set up the conditions of the query. This query will change every row's data which is met with the conditions. If we skip the `WHERE` part then the query will update all the rows from the table.

- Which SQL statement can be used to delete rows?. Describe the syntax briefly.

    : We can use the `DELETE FROM` statement followed by the table's name and the `WHERE` keyword which works similar to the one after the `UPDATE` statement.

- Which SQL statement can be used to create queries?. Describe the syntax briefly.

    : We can use the `SELECT` statement to create a queries followed by the columns we will want to get from the table or table's and the `FROM` and `JOIN` keywords to specify from which tables we want to get these columns (obviously a query can have other keywords and set up).

- How can you join tables together in SQL? When should you do it?

    : We can do this with the aforemetnioned `JOIN` keyword in a query followed by the table's name we want to connect to the one set up with the `SELECT` statement. After this we need the `ON` keyword and set up what cloumns the query has to compare to each other in the two tables (in most cases they are a primary and a foreign key). We need this method if we want to use data from more than one table.
