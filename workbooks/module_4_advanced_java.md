# Advanced Java

## Web development✔

* What is an API?

    : API or Application Programming Interface is a connection between computer programs, in contrast to a User Interface which connects a person to a computer. In other words an API is a layer which with two computer commuicate.

* What is a REST?

    : REST or Representational State Transfer is a software architectural style which describe and defines the structure of World Wide Web. REST means that a server will respond a request with a representation of the resource which contains hypermedia links. This means we only has to know the actual source we request and the other connected resources become available via the links in the response.

* What is a cookie?

    : A cookie is a small piece of data the server sends to the client which is managed by the client (most likely a browser) after that. It is used to store state information about the client's activity in the web app (the http protocol is stateless by default). It is also used to help the server identify the client/browser itself. Some alternative to store data about state nowadays is `localStorage`.
    Cookies are sent with every request so it's important for them to be small in size and have a limit of the number of them per website (most browsers have these limits).

* Describe the HTTP protocol and its methods.

    : HTTP or Hypertext Transfer Protocol is a protocol to fetch resources, it is the foundation of data exchanges on the Web. It is built on the exchanges of requests and responses instead of a stream of data between the client and the server. An HTTP request has different parts, like the request line (method, uri, http version), the headers and the body.
    The HTTP request methods are to indicate the purpose of the request and the client's expectations on the response. The GET method represents a request for a specific resource, the POST is for submitting a specific resource, the PUT is for replacement, the PATCH is for modification, the DELETE is for deletion. A server usually can differentiate between requests with different methods and response them accordingly.
    

* How do you identify unique resources on the web?

    : We can identify unique resources with the URI (Unified Resources Identifier) which is some kind of address of a resource. Specifically in the web we use URL (Uniform Resource Locator) to reach resources like web pages. A URL has different parts like the protocol (most likely https), the top level domain, IP address and ports, path, query string and fragment identifier.

* What are the main frontend languages on the web? Describe them briefly.

    : The main frontend languages for web development are the HTML, the CSS and the JavaScript. The HTML is for the base structure of a web page, the CSS is for controlling the appearance of HTML elements, and the JavaScript is for dynamic behaviour of websites.

* What is JSON?

    : JSON (JavaScript Object Notation) is a file format which is human-readable and (despite of its name) language-agnostic. It has only six data type (array, object, number, string, null and boolean) and it's used to store and transfer data. It is the most common form to transfer data through the web. 

* What operations are fundamental to most data-driven applications?

    : For a data-driven application the most important functions are the CRUD operations: create, read, update and delete. These operations describe the forms of access and manipulate data of a persistent storage. These operations are implemented by databases (e.g. by the SQL statements) and the HTTP methods (POST, GET, PUT/PATCH, DELETE).

* Briefly describe at least two communication technologies that enable a server to push data to a client in a web application.

    1. WebSocket API: it makes a simultaneous two-way communication channel between the client's browser and    the server, make it possible for the server to push data. It starts with an HTTP "handshake" and using one TCP connection after that.
    2. SSE (Server-Sent Events): it's a server-push technology which enable the server to push updates to a     client via HTTP connection. It's unidirectional (only the server can send messages to the client), persistent connection and if the connection drops the client (browser) automatically tries to reconnect.


## Spring and Spring Boot✔

* What is Spring Framework and what are its core features?

    : Spring framework is meant to be a platform which provide infrastructure support. With it we can build application from POJOs (Plain Old Java Objects) but we can also add modern enterprise services to the application. Spring core concepts are Dependency Injection (see below), Inversion of Control (see below) and Aspect-Oriented Programming. The latter means Spring enables the modularization of cross-cutting concerns.
    Some of the important Spring modules are Core Container, Spring AOP, Spring Web (or MVC), Spring Data, Spring Security etc.

* Explain the main differences between Spring and Spring Boot.

    : Spring Boot is basically an extension for Spring (or Spring applications) which helps minimize the necessary configuration of a Spring app. It achives it by Convention Over Configuration which means it has a default set up for everything the Spring needs to set before starting. It also configurates automatically based on the app's dependencies.

* How does Spring Boot simplify the configuration of Spring applications?

    : As we stated above Spring Boot uses auto-configuration and opinionated (default) settings. It also creates components for the application based on the project's dependencies - for example if the project has the spring-boot-starter-web dependency then Spring Boot will automatically create and configure a Tomcat web server.

* What is a dependency injection (DI) and how does Spring support it?

    : Dependency Injection is a design pattern for create loose coupling between components. It is the way we add dependencies to the component from outside of it instead of create these dependencies in the component itself, make the component more modular (e.g. we can define an interface in the component and add any implementation of it as dependency from outside). Spring streamlines this process, it instanciates every component with appropriate annotation and do this in an order what takes into account the dependencies between these components. There are three ways to usethe  Dependency Injection in Spring (the Spring will try to inject these fields if it has a fitting instance in it pool, the IoC container):
        1. Field Injection: We can use it with the @AutoWired annotation using it on a component's field.
        2. Constructor injection: when we add parameter to a construction and define the component's field with it.
        3. Setter Injection: it works quite similar to Constructor Injection but we use a setter method instead of a constructor.

* How can you define a bean in Spring? Provide examples.

    : In Spring the beans are the objects what are managed by the IoC container, they are the base components of the Spring application. We can define a bean with the @Component annotation (in class level) or with the @Bean annotation (in method level). The instance of the class or the return value of the method will be created and stored in the ApplicationContext which serves as an IoC container at the start of the application.

* What is inversion of control (IoC) and how is it implemented in Spring?

    : Inversion of Control is a principle which says that the control of objects or components should be at the hand of a container or framework instead of the developer of the actual program. In Spring it's implemented by the Dependency Injection when the dependency is handled by the Spring itself (using its ApplicationContext) instead of the actual components (see above).

* What is a RESTful API, and how can you develop a Web API using Spring Boot?
    
    : RESTful API is a web service that follows the REST style (see above) and most likely implements the CRUD operations. It usually uses HTTP, and everything is seen as a resource which is identified by an URL. In Spring Boot we need to create at least a controller and a model/entity (but for persistence we should implement some kind of database too). The controller controls the endpoints of our web API and the HTTP requests through them, and the model(s) define the structure of the resources the API controls. In short we can achieve this via the Spring MVC module of the Spring.

* How do you handle HTTP requests in Spring MVC? Give an example.

    : We can control the HTTP request through an endpoint which is set up in a controller component (class annotated with @Controller or @RestController). An endpoint is handled by handler methods annotated with request mapping annotations (e.g. GetMapping or PostMapping). If we use the @RestController annotation then the handler method can have a return value of any java data type the Spring Web will set up a response for it with appropriate details, parse the return value into a json file and add to the response as its body.


## Entity Relationships, ORM, Spring Data✔

* What is ORM (Object Relational Mapping)? What are the benefits, when to use?
    
    : ORM is a programming technique with which we translate objects and classes in oop programs to relational database elements (records and tables) and vice versa. With it we can abstract the handling of the sql database (the actual queries) and use the data as objects instead of sql elements while we can store this data in a relational database. It is on higher level of abstraction than traditional data access techniques where the actual program has to implement the handling of relational database.

* What is JPA?

    : Jakarta Persistence API is a specification for ORM in Java which standardizes how we persist Java objects to relational database. It uses entities (marked by the annotation @Entity) which are classes to map into database tables. With it we can set up and handle a relational database which holds the data from a Java application with using only Java.

* What is the difference between JPA and Spring Data JPA?

    : JPA or Jakarta Persistence API is a specification or standard that defines a ruleset for object-relation mapping in Java (and later in other languages). Spring Data JPA is an integration of the JPA standard with the Spring Data's repository abstraction (Spring Data itself is a part of the Spring to handle database connaction and persistence in a Spring app). 

* What is the difference between Hibernate ORM and Spring Data JPA?

    : Hibernate ORM is the most widespread ORM implementation for Java. Spring Data JPA is an integration of the JPA standard for Spring Data and for this it uses the Hibernate ORM (so the Hibernate is part of the Spring Data JPA but it's also an independent library - it can be used outside of Spring).

* How can you configure database connection properties in a Spring Boot application?

    : One can use the application.peoperties configuration file where we can set variables and other settings for the Spring application, specifically the credentials for the database we want to our application to (as spring.datasource.url, .username, .password). With these credentials and with the necessary dependencies installed the Spring can connect to the database.

* Explain the concept of cardinality in entity relationships. How does it impact the design and mapping of entities?

    : Cardinality in entity relationships means the numerical relationship between two entity, so how many entity can be connected from one table to an other table's entity. It can be One-to-One, Many-to-One or Many-to-Many. It has a huge impact the design of the database entities since these relationships are defined different ways. A One-to-One relationship is defined by a foreign key column which point to an entity from the other table. But a One-to-Many relationship is defined by a foreign key in the Many side of the relationship. The Many-to-Many relationship is mapped with an extra table called juntion table of which entities has Many-to-One relation to both table we want to connect with a Many-to-Many relationship. This junction table's sole purpose usually is to handle the other two's relationship so it only consists two foreign key columns (but sometimes an other table with other funcionalities can have this role and as such it has more columns).

* How to create a custom repository in Spring Data JPA?

    : First we need to create the base repository (the one which extends the JpaRepository interface). Second we need to create an interface what does not extends the JpaRepository, and define method signatures in it. After that we can create a class what implements this second interface and name it in this form: baseRepository + Impl. Finally we need the base repository to extends the second interface.

* What is the difference between FetchType.Eager and FetchType.Lazy?

    : When there is a relationship between two entity (see above) and when the JPA load one of them from the database then the other entity (or entities in case of One-to-Many relationship) can be loaded alongside it or not according to the set up. The Cardinality annotations (e.g. @One-to-Many) has a fetch parameter what can be set to FetchType.Eager or FetchType.Lazy. The former means the JPA load the entities realted to the originally loaded one alongside of it, the latter means it only loaded it on demand (when we use the get method for example). The lazy way can save resources while the eager way ensures the integrity of our data (the entity will have all its field).


## Spring Security✔

* What are some essential features of Spring Security?

    : Two of the biggest features of Spring Security are authentication and authorization. The former is how we verify the identity of the client (e.g. a user), and the latter is how we decide if the client can access to the resource it want to get or modify in its request. If we don't want some resource to be used by anybody then the authorization process has to be preceeded by an authentication process. In Spring Security we can set up request based (in the security filter chain) and method based authorization (on an actual method in a controller using the @PreAuthorize annotation).
    Another feature is the protection against common exploits like the CSRF (cross-site request forgery). It isn't an out-of-the-box feature but they are implementable in Spring Security.

* How can you secure a Spring Boot application using Spring Security?

    : With Spring Security we can add an authentication/authorization layer to the servlet filters, and we can configure it in Security configuration. We can set up what path should be used by users with some kind of authorization and the check of the credentials of loginning users. After login the server can create a secure token (e.g. a JWT) and pass to the client via response; after that every subsequent request should contain this token and the server side can validate it, using it to authentication without the necessity to store the user credentials (cuch as the password) in the frontend and send it with every request.

* Explain how the security filter chain works.

    : The servlet filter chain is between the client and the server and every request (and potencially the response) goes through every component in the chain one by one and they process it. A filter can modify a request or terminate the filter chain's current run so the order of it can be quite important.
    Spring Security is installed in the servlet filter chain as a FilterChainProxy, which means it's also a filter chain with multiple filters. In Spring Boot the security filter chain is a bean in application context and we can define our own.
    A filter in a filter chain basically can do three things with the request: it can modify and pass it, pass it without doing anything or can block the further processing of the request.

* What is JWT (JSON Web Token), and how can you use it for authentication?

    : JWT is an open standard for securely transmitting information as JSON object. It is mainly used for authorization and authentication, or securely transmitting other information between parties.
    It has three part and when passed as a string these parts are separated by dots.
        1. Header - it contains metadata of the JWT itself as a (stringified) JSON object, typically contains the data of the type of the token (JWT) and the signing algorithm being used.
        2. Payload - this is the "body" of the JWT, where the claims are stored; these claims are statements about the entity and additional data usually on the authorization level of the claimant.
        3. Signature - this is derived from the content (from the payload and the header) of the JWT using a key which is hold only by the server. Since it depends on the content of the JWT and cannot be decrypted without the key it ensures that the content of the JWT isn't modified by anyone who isn't the JWT provider (the server).
    We can use JWT for authentication in a way when the client provides some valid credentials, the backend after the authentication process can send it a JWT with the credentials and other claims. After that for every other request the client can use the token for authenticcation and authorization and the server can be sure that the claims are valid ones. It eliminates the need to store user credentials on the client side and use them for every request or the need to store session state on the server (which would really hurt scalability of a web application).

* Explain the concept of authentication and authorization in Spring Security.

    : In Spring Boot both authentication and authorization (for definitions see above) are part of the security filter chain process. The authentication is done by the UsernamePasswordAuthenticationFilter, which use the AuthenticationManager for this. After a successful authentication the SecurityContext is populated with the user's information. After this in the authorization phase the AccessDecisionManager decide if the user is authorized for the request or not, and in the case of the latter it throws an exception (blocking the process).

* How can you implement method-level security using annotations in Spring?

    : We need to use annotations on two places for this:
        1. On the Web security config class (or on the  main application class) we should use the @EnableMethodSecurity annotation.
        2. On methods using as endpoints we should use some of the method-level security annotations. For example we can use the @PreAuthorize annotation and we can set the necessary attributes to be authorized for the using of the endpoint, for example "hasRole:('ADMIN')" - this means only users with ADMIN role can use it. Alternatively we can use the @PostAuthorize annotation which runs its checking mechanism after the method has been executed (contrary to the @PreAuthorize which runs beforehand). This is particularly useful when we want to define the authorization based on the data the response would hand to the client (e.g. we want to hand data to only the owner of it).


## Integration testing✔

* What is integration testing, and how does it differ from unit testing?

    : While a unit test is testing only a well separable and self-contained element or layer (so a unit) of the application and an end-to-end test is testing the whole application itself in real-world scenarios, the integration test is basically everything between them. If there is at least two unit what communicate each other during the test and we test this cooperation but there are parts of the app we don't use or mock them then we can call it an integration test. An integration test is typically more resource-demanding than the unit tests hence we use them less frequently and/or for cases can't be tested by unit tests (e.g. edge cases during a cooperation of two layers).

* How can you configure and set up integration tests in a Spring Boot project?

    : First we need to create at least one class for integration tests, in a maven project it should be in the test package. It is important for the file which contains the class to its name must not includes the 'Test' word or the maven will recognize it as a unit test and we want to avoid it. We have to use the @SpringBootTest annotation what will bootstrap the entire container, or in other words it will start the application. It will use the IoC container of the original Spring Boot application but we can add it other elements with annotations (e.g. the @AutoConigureMockMvc annotation will add a MockMvc to it). We can also make this new elements to be injected insted the "original" ones, so we can mock out dependencies we don't want to test in the actual integration test. We can also set up a new property source with the @TestPropertySource annotation
    After these set ups we can write test methods similar to unit tests. The difference is the environment we run them, in the case of a unit test we mock out everything else but for an integration test only some part of the application.

* How do you perform an HTTP request in an integration test for a Spring Boot application?

    : We can use MockMvc which performs full Spring MVC request handling, so we can perform mock http request to the Spring Boot application. For example we can use the MockMvc's perform method for this and set up the request's fundamental properties like the request method, the uri or the body etc.

* How can you mock dependencies or external services in Spring Boot integration tests?

    : see above

* How do you configure an embedded H2 database for integration testing in Spring Boot?

    : We can do it in three steps. First we need to add H2 as a dependency to the project (in case of a maven project we can define it in the pom.xml file). Second we need to set up a new property source (most likely we want to use other database for the app itself and we want to use H2 only for testing), and last we want to define the attributes of H2 in this test property source such as datasource.url or datasource.driver-class-name. After this setup the Test version of our app will connect to the H2 database according to its own property sourcce's content instead of the other database we set up in the original property source.


## DevOps✔

* What is CI/CD (Continuous Integration/Continuous Deployment), and what are its benefits?

    : CI is a development practice or attitude where the developers merge their changes to the main branch as often as possible. To avoid integration challenges every merge has to run tests (most likely unit tests and integration tests only) before it can happen, and because the merges are often the tests should be automated. In some sense the whole CI/CD is about automating this pipeline itself as much as possible.
    CD contains the CI process, but after that it has also an automated release process which deploy automatically the new build we created and tested during the CI phase. It is important to note that releasing doesn't necessary means release the build into production.
    The main benefit of this development practice is that with this we can avoid integraation hell when developers have to merge branches which was developed independently for a relative long time and as such they contain a lot of merge conflict. With the CI/CD we can break this huge process into small pieces and every merge conflict or bug is catched close to its "creation" hence it can be fixed more easily. It also makes possible to release new versions of an app very often. The other big benefit of it is that the process itself is automated which means the developers (and the QA) spend less time with bug finding and deploying a new version of the app is faster and easier.

* What is Docker and Docker Compose?

    : Docker is an open-source project with that we can deploy an application with all of its dependencies in a standardized form. A Docker container works similar to a virtual machine but it uses some part of the computer's OS (while a VM run completely independently of it), but in practice a Docker container would run on any mainline OS. In other words a VM is a virtualization of the hardware while the containerization isn't.
    Docker Compose is a tool to running multi-container applications. Docker images are for services we want to run and handle in isolation (e.g. an application's backend API or a database) and we usually want to keep them separated hence modular, but we also need to run them together and make them capable to interaction even if they are containers. Docker Compose solve this exact problem. It run multiple containers and make it more easy for them to communicate with each other.

* Explain the difference between an image and a container in Docker.

    :  A docker image is an image file on an app or service with its dependencies (there are readymade templates but everyone can create one for their own application), in other words an image is a read-only template for docker engine. A Docker container is the running of an image in isolation from the other parts of the OS. A working metaphor for their relationship is that image is a class and the container is an instance of it.

* What is a Dockerfile?

    : Dockerfile is a file contains the series of commands we want the Docker to execute when it builds a Docker image. In some sense it is a template or the definition of the actual image. We can set up the linux distro and the software environment of the image and run terminal commands in it. In a Dockerfile we can define multi-staged build too, which means during the build process there will be multiple builds and Docker will only keep in the final image the files we explicitly want it to do. It is useful when we want to build an app in an image but we don't want to keep the build tool in the final form of the image only the runtime environment. E.g. we can build a Spring boot app with maven but to run it we only need the JRE and the .jar file, the maven itself and the source code isn't needed in the final image.

* How can you set up a basic CI/CD pipeline for a Spring Boot application?

    : For this we can use the Github Actions platform and define a workflow with two jobs, one for the integration part and one for the delivery part. In a workflow we can set what actions should trigger the workflow itself (in this case we want it to run when a push or pull request happen in the main branch). After that we can define the first job which is building the Spring Boot app. If we use maven this also means the run of unit tests are part of this process so it will check if the new version broke anything in the app, hence it works like the CI part of CI/CD.
    After this we can define the second job (and make it to depend on the first one) which will build a Docker Image and push it to DockerHub. If not in the first part then at least now we will need some credentials we don't want to be openly available. For this there is the Github Secrets which works like environmental variables for the GitHub repository itself.

