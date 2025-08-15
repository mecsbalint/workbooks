
# TypeScript

## TypeScript basics and types✔

* What is TypeScript?

    : TypeScript is a strongly typed programming language that builds on JavaScript. It's syntax is basically the same as JavaScript's but with an addition to handle types, hence it's called a syntactic superset language which means it's an addition of another language syntactically - that also means every JavaScript code is valid TypeScript code but not the other way around. TypeScript doesn't exist during runtime as it needs to be compiled to JavaScript before run. TypeScript is especially useful for greater projects with large JavaScript codebase since it makes easier with the tpye system to maintain them.

* What are the advantages and disadvantages of TypeScript?

    : TypeScript's type system has several advantages over a dynamically typed language like JavaScript. The error detection is easier with TypeScript since the compilator can serve us with more detailed error messages. It also helps to create more organized code structures. With it an IDE can be more helpful to catch typing problems during code creation rather than runtime since it can check the type compatibility during it. But we could mention other tools an IDE can have for a staticly typed language such as autocompletion or type hints.
    There are drawbacks of using TypeScript of course. It have a longer compile time than JavaScript. Some JavaScript libraries aren't prepared for TypeScript which means sometimes we need to declare types to using them (fortunately it is a less important problem nowadays since TypeScript become more widely used). It has to be set up on top of the regular set up a JavaScript project requires. And it certainly has a learning curve.

* What is structural type system and how does it differ from nominal type system?

    : Structural type system is a class of the programming type systems where the compatibility or equivalence is determined by the actual structure of the types. This means if an object has the structural attributes for a type (e.g. it's an object with the required fields) it is seen as compatible with said type or it is considered as an instantiation of the type. The nominal type system is another class where the compatibility or equivalence is decided based on the names or explicit declarations (such in Java where we can only use explicitly declared instanciations for certain types).

* What is type inference?

    : Type inference in TypeScript means the type of a variable is deduced from the value it's assigned to the variable. This means we don't need to declare the types of a variable in trivial situations. If a variable is declared with `let` then it will get the type of the value, if we use `const` intead then it will get the actual value as literal type.
    This assignment is also called implicit type assignment in contrary to the explicit where we state the type of the variable explicitly written on the left hand of the `=`.

* What are the differences between `any`, `unknown`, `object`, `void` and `never`, types in TypeScript?

    : In TypeScript there are some special types that may not refer to a specific type of data:
        - `any` type means the value be anything, essentially this type disables type checking of TypeScript
        - `unknown` type is similar to `any` and is a later addition to TypeScript. It is also means that any value can be assigned to it but it can't be used until it is asserted or narrowed into an other type. It is also used as a bridge to assert a value's type to another one which isn't considered compatible.
        - `object` type represents all non-primitive values in TypeScript, in contrast with `Object` type which describes the functionality of all objects.
        - `void` type represents the case when a function doesn't return anything explicitly - it returns `undefined` implicitly, however. While in JavaScript there is no difference between an implicitly returned `undefined` and one which is returned explicitly, in TypeScript the former considered `void` type while the latter is `undefined`.
        - `never` is a bit similar to `void`, but it represents a case when a value couldn't occur. For example if a function never returns anything not even implicitly then it has a `never` return type. Or if we narrowing (see below) every possible occasions of a type (for example narrowing out `string` and `boolean` from a `string` | `boolean` union type) then in that branch the value has `never` type. A `never` is assignable to any other type, but none of them are assignable to it.

* What are the drowbacks of using `any` type?

    : TypeScript is all about types and their advantages, while `any` type is somehow the negation of it. It makes possible to use any type of value in a place, but it also eliminate the effective use of TypeScript. Using `any` means we don't have the type safety, and the overusing of it can be lead to harder to maintain the code. Using `any` also means the IDE can't use autocompletion or type hints based on the type.

* What is the difference between interface and type alias?

    : Type alias is basically a named declaration of a type. The type can be anything, not just object type, and it is important to note that it is really just an alias. We can extend a type alias with intersection and we can't declare a type alias more than once.
    The interface declaration is another way to name an object type. We can extend it with the extends keyword and we can declare an interface multiple times (this is especially useful for imported interfaces or in other cases when we can't or don't want to modify the original interface). The difference between extending and declaring multiple times effectively is that with extension we create a new interface which inherits the superinterface's properties while with multiple declaration we change the original interface.

* What are generics in TypeScript?

    : Generics is a tool to define functions, types or interfaces with type which isn't defined in declaration but rather later when it's used. A good example is the Array which has a generic type, and this type is declared when we use the Array - when we set up what type it should hold. For staticly typed languages like TypeScript generics is an essential tool to construct reusable and modular code. The TypeScript compiler handle generics as though they can be anything, but we can declare generics by determining what types it can be with the `extends` keyword and a union type.

* What are union types?

    : Union types are a way to composing types from existent ones in TypeScript. They can contains literal types, named types or even inteerfaces. A variable declared with a union types can get any of the members of the union types - if we declare a variable with `string` | `number`, it can be a string or a number. TypeScript compiler constrains the use of a union types variable to all of its possible type, so in most cases we will need to narrowing (see below) before we use it.

* What is type assertion?

    : Type assertion is used to tell TypeScript a variable is belong to a certain type. As such it effectively switch off type checking of TypeScript, but in some cases we have information about the type of a variable wich cannot be known by TypeScript. For example with DOM manipulation, event handling or a http response's body can be an element which comes from a different structure that TypeScript can't see.
    TypeScript only allows type assertions which convert to a more specific or less specific version of the type. To bypass this we can assert a type into `any` and assert it inot our desired type after that.

* What are literal types?

    : A variable can have not only general types like `string` or `number` but we can assign them specific one which are called literal types. For example a specific string can be a literal type and a variable with this type can only have the specific string as value. This is especially useful when we use them in combination of union types, for example when we only want to let specific words to be assigned to a variable.

* What does it mean that `Enums` are not a type-level addition?

    : Most features of TypeScript are tied to its type-level, and `Enums` are one of the few exception. `Enums` allow a developer to define a set of named constant, and contrary to most of the TypeScript additions it produce javascript code which exists during runtime, contrary to the type-level additions which exist only until the compiling is finshed.

* What is the non-null assertion operator?

    : The non-null assertion operator (`!`) placed right after the variable or expression tells TypeScript that its value isn't `null` or `undefined`. Basically it switch off a part of the type checking for this speficif variable or expression, and as such it should be used with great caution.

* What is narrowing in TypeScript?

    : When a variable or expression has different possible types (e.g. a union types or `unknown`) then the TypeScript compiler will check every action with them with all the possible types. To avoid this and more importantly to ensure that the variable will be used in corresponse of it's actual runtime type we use narrowing, which means we rules out some of the possible types using JavaScript tools like `if-else`, `typeof` or `instanceof`. It is important that this narrowing should work during runtime which means we can't use TypeScript-specific tools which exist only until the end of compile time. But TypeScript compiler recognize the code structure as narrowing and accept that in certain branches the variable/expression has different types.

* How does TypeScript handle objects that have more properties than the type?

    : It depends on where we use the object that has extra properties. In a literal assignment it considered as an error for TypeScript, but if we assign a variable to another it doesn't matter if the former has all the required properties.

* What do the `readonly` and `optional` modifiers do when applied to an object's properties?

    : `readonly` modifier means a property can't be reassigned after the assignment of the object. However, it doesn't matter if the object itself is reassigned.
    `optional` modifier (`?`) means the property isn't required for the instantiation of the type. However, when we want to use this property we want to narrowing out the `undefined` type since a not assigned property will be `undefined`.


## How TypeScript works?✔

* What does a TypeScript compiler do?

    : TypeScript compiler transpile the TypeScript code into JavaScript; this is necessary since TypeScript doesn't exist during runtime, it has to be transpiled into JavaScript code what can be run by Node.js or the browser. TypeScript compiler does this in three main steps:
    1. Doing static type checking. It checks the code against the TypeScript's expectations, and if it fails it stops and displays error.
    2. It transpiles to JS mainly by stripping out the type definitions (type-level additions) to get a pure JavaScript code.
    3. If there are not type-level additions of the TypeScript code (e.g. Enums) then it creates them in JavaScript. It can also make the code compatible to older JS versions.

* What does `emit` means in TypeScript?

    : When the TypeScript compiler transpiles the code into JavaScript and save it to a file or files that's called emitting. By default the compiler emits the files even if the type checking has failed but it's up to the setting `noEmitOnError`.

* How can we configure the tsc's behaviour?

    : We can configure it's behaviour in the tsconfig.json config file. When input files are specified in the command line this config file is ignored, however.

* What is `ts-node`?
    
    : `ts-node` is an npm package and developer tool which can streamline the compilation+run route. It compiles the TypeScript files, uses the tsconfig.json, doesn't emit JavaScript files and run the code. It's very useful for development when we write and rewrite the code constantly hence a lot of compiling is needed, however, it isn't necessary for production since there only one compile time is needed and we don't want to do it every time someone or something runs the code.

* How can you define a type that can have exactly specified values?

    : We can use literal types for type definition with alias or interface. This means we don't set a type (like string or boolean) as the type, we set a literal value (or values if we use union types) instead. For example we can set "GET" as a type, and since every instance of this type has to have this exact value. If we set up a variable's type in implicit way the if we declare it with `let` it will get the normal type of the assigned value, but if we do with `const` then it will get the value as literal type.


## Handling NPM packages and runtime APIs in TypeScript✔

* What are the type declaration files in TypeScript?

    : The TypeScript in transpiled (JavaScript) form looses its type declarations. If we only use the code to run it it doesn't mean any problem, but if we want to share our TypeScript code in compiled form (e.g. as an npm package) we probably want to do it along with the type declarations. That's what type declaration files are good for. Their extension is d.ts and they hold the types extracted fromt the .ts file. It can be used for static type checking when someone uses the package as an external library. Declaration files can be also made for JavaScript projects by hand so these projects can be used as TypeScript packages. There is a GitHub repo named DefinitelyTyped where the community creates these type declaration files.

* What are the different methods to provide the type declaration files for your application for the external packages?

    : If the package is written in TypeScript then it contains the type declarations since the compilation creates them, and they can be used out of the box. If it wasn't but it has Definitely Typed support then you can install the definitions separately with the `npm install @type/*` command (the * is the package's name). If neither option is available then you have to create the declarations manually in your project in a .d.ts file.

* What are the possible pitfalls of these methods?

    : When the package is TypeScript-based there are no such pitfalls, however there are a lot of packages which weren't written in TypeScript. When you use DefinitelTyped community declarations there is a chance that they aren't up-to-date with the package's current state since it is maintained by other people. You should always check the version of the definitions if they are the same as the pacakge's. When you create the definitions yourself it is a lot of work to write and understand the type system of the package, while if you have the types by default they can be make it easier to understand the code itself. You can ensure the created types are up-to-date, however.

* What are the differences between the core JS features and the runtime APIs?

    : The core JS features are supported by default, so there are types to use them in TypeScript. However, the runtime APIs such as WebAPI or Node.js are not so if we want to use their features in TypeScript we need to install their type definitions separately from DefinitelyTyped. Obviously if we use one of these we assume that the code will run in that runtime environment (e.g. if we want to use WebAPI's features we need to know that our code will be run by a browser).

* How can you set up the proper JS code version for a TypeScript project?

    : You can set two properties in the tsconfig.json to manage this. The `compilerOptions.target` decides to what version of JavaScript should the compiler transpile the code, and the TypeScript can use that's version's features. The `compilerOptions.lib` array holds the versions the compiler's type checking based on.

* How can you set up runtime input validation with Zod?

    : There are values TypeScript can't have information of their real runtime value (e.g. user inputs or http responses) and it can't check and validate them since TypeScript doesn't exist during runtime. Libraries like Zod provide a solution for this problem. With it you can define schemas and validate values with them. The `schema.parse(variable)` will throw an error during runtime if the variable doesn't meet expectations. You can set up a varies of expectations in schema such as maximum and minimum value for number, literals or even default values for optional properties.
    Obviously when you define a schema independently to the original type of the variable you define the same data structure twice which is suboptimal. Fortunately, you can extract type from a schema, so you can derive both of them from the same definition. Unfortunately, for some uncomprehensible reason it isn't possible to extract a schema from a type.


## TypeScript and React✔

* What are the benefits of using TypeScript with React?

    : React is a JavaScript framework to create reactive one-page web applications, and as such one of the most widespread solution. For TypeScript's benefits see above. Both of them are really useful for developing frontend code, and using them together doesn't cancels out their benefits. And they are compatible, TypeScript supports javascript language extension which is a crucial part of React, and types for React elements can be easilly installed. The most popular React build tool, Vite also supports TypeScript making the set up of a React TypeScript project quite trivial.

* How would you define types for props and state of React component with TypeScript?

    : You can define the structure of props with type alias or with interface in the same file as the component. After that you can explicitly set the component's one parameter (the props object) as this type or interface. The naming convention for it is component's name + "Props".
    If your props have child elements then you should create an interface which extends the React.PropsWithChildren interface (or if your props has only children element just use this built-in interface).

* How would you type hooks with TypeScript?

    : Hooks are an important part of React and as such they are supported in `@types/react`. For example useState can be typed implicitly by its initial value or explicitly with a generics. For custom hookks you should create custom type/inteerface for the return value of the hook.

* What's the difference between `JSX.Element`, `ReactNode` and `ReactElement`?

    : `JSX.Element` is a type which represents a JSX expression. It should be used as a component's return type when it returns pure JSX. `ReactNode` can represents anything React can render: `undefined`, `null`, `boolean`, `ReactElement` etc. It should be used when the component can return various type of children. `ReactElement` refers to an object representation of a virtual DOM node. It includes both elements created through JSX and with `React.createElement()`. It is useful when you want to exclude the non-element types.


## TypeScript type system deep dive✔

* What are utility types?

    : TypeScript has utility types for common type transformations. Some of them, like `Awaited<>` are to provide a type for specific use cases like an async function `Promise` return value. Others, like `Partial<>`, `Required`, `Pick<>`, `Omit<>` etc. are for extract a new type from an original one - in other words to transform and manipulate types.

* Write at least four types of Utility types and for what they can be used!

    1. `Pick<Type, Keys>` creates a new type from Type but only with its properties set in Keys (Keys is a union type)
    2. `Partial<Type>` creates a new type from Type but all of its properties are optional
    3. `ReturnType<Type>` creates a new type from the return type of the function type Type
    4. `Required<Type>` creates a new type from Type but all of its properties are required

* What are the common methods for type manipulation?

    : There are several ways to manipulate types in TypeScript. One of the common ways to manipulate types is using utility types (see above). Another way is the `keyof` operator, which returns the keys of a type as a union type. Or the `typeof` operator which returns the type of a variable. And there are the conditional types: we can decide what a type should be depending on a conditional statement about an interface is extendable to an interface or not (this is especially useful when we work with generics)


* What are discriminated unions?

    : When we want two different set of data to use in the same place we can use discriminated unions, this basically means we define a type as a union type where the members are also types (it makes sense only if we use object types for this not primitive ones). After that we can use the newly defined type as parameter type for example, and narrowing in the function to get what version of it we currently use. It works similar to inheritance and subclass-superclass pairs in nominal type systems like Java.
    There is a similar way in TypeScript when we use type intersection to create partially same types, but in that case the TypeScript wouldn't now about the particular properties of the types.

