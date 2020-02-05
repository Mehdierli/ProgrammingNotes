## Angular Single Page Applications (SPA): What are the Benefits?
* Single Page Applications are super easy to deploy in Production, and even to version over time!
* a much-improved user experience due to less full page reloads and a better overall performance because less bandwidth is needed.
    - On a SPA, after the initial page load, no more HTML gets sent over the network. Instead, only data gets requested from the server (or sent to the server).
    - So while a SPA is running, only data gets sent over the wire, which takes less time and bandwidth than constantly sending HTML. 
* In a SPA after application startup, the data to HTML transformation process has been moved from the server to the client – SPAs have the equivalent of a template engine running in your browser!

## What is TypeScript and why would I use it in place of JavaScript?
* TypeScript is a superset of JavaScript which primarily provides optional static typing, classes and interfaces. 
* it will compiles to plain javascript
* One of the big benefits is to enable IDEs to provide a richer environment for spotting common errors as you type the code.

## Data Binding
* define the communication between a component and the DOM
* String interpolation
    + String Interpolation is a one-way databinding technique which is used to output the data from a TypeScript code to HTML template (view). It uses the template expression in double curly braces to display the data from the component to the view
    + {{ data }}
* Property Binding
    + Property Binding is also a one-way data binding technique. In property binding, we bind a property of a DOM element to a field which is a defined property in our component TypeScript code.
    + <input type="email" [value]="user.email"> 
* Event Binding
    + In Angular 8, event binding is used to handle the events raised from the DOM like button click, mouse move etc. When the DOM event happens (eg. click, change, keyup), it calls the specified method in the component. In the following example, the cookBacon() method from the component is called when the button is clicked: 
* two way binding
    + In two-way data binding, automatic synchronization of data happens between the Model and the View. When you make changes in the Model, it will be reflected in the View and when you make changes in View, it will be reflected in Model. 
    + In two way data binding, property binding and event binding are combined together.
    + This happens immediately and automatically, ensures that the HTML template and the TypeScript code are updated at all times.
    + [(ngModel)] = "[property of your component]" 
    + Note: For two way data binding, we have to enable the ngModel directive. It depends upon FormsModule in angular/forms package, so we have to add FormsModule in imports[] array in the AppModule.

## Directives
* A class that can modify the structure of the DOM or modify attributes in the DOM and component data model.
* The Angular directives are used to manipulate the DOM. By using Angular directives, you can change the appearance, behavior or a layout of a DOM element. It also helps you to extend HTML.
* Component Directives
    + Components use @Component() (an extension of @Directive()) to associate a template with a class.
    + Component directives are used in main class. They contain the detail of how the component should be processed, instantiated and used at runtime.
* Structural Directives
    + modify the structure of the DOM.
    + structural directives start with a * sign. These directives are used to manipulate and change the structure of the DOM elements. For example, *ngIf directive, *ngSwitch directive, and *ngFor directive.
* Attribute Directives: 
    + modify behavior and appearance of page elements.
    + Attribute directives are used to change the look and behavior of the DOM elements. For example: ngClass directive, and ngStyle directive etc.

## What is service
* Service is a broad category include any value, function, or feature that application needs. A service is typically a class with a narrow, well-defined purpose. It should do something specific and do it well.
* The injector is the main mechanism. Angular creates an application-wide injector for you during the bootstrap process, and additional injectors as needed.
* For data or logic that isn't associated with a specific view, and that you want to share across components, you create a service class.
* A service is used when a common functionality need to be provided to various modules.
* extract common functionality out of component to have better modularity.
* Most front-end applications communicate with the backend services over an HTTP protocol. Modern browsers support the two different APIs for making HTTP requests.
    - XMLHttpRequest interface and the 
    - fetch() API.
* We will use XMLHttpRequest for Angular application.
* If an angular app needs to interact with the back end server, then we can write the API calling code inside the service file.
* So, if we need to send a POST request to the server, then we import the HttpClient inside the service file and make an AJAX request to the server with the data object. After a successful request, the server sends a response back to the client.
* separate presentation of the data from data access by encapsulating the data access in the separate service and delegating to that service in a component.

## Life cycle hook and constructor
* constructor is executed when the class instantiated
    + The constructor should only be used to initialize class members but shouldn't do actual "work".
    + So you should use constructor() to setup Dependency Injection and not much else
* ngOnInit indicate that Angular is done creating the component
    + Called after the constructor and the first ngOnChanges() 
    + Mostly we use ngOnInit for all the initialization/declaration and avoid stuff to work in the constructor

## How do you submit a form.
* use (ngSubmit)

## What is the difference between ngForm, FormGroup, FormControl.
* ngForm
    + Creates a top-level FormGroup instance and binds it to a form to track aggregate form value and validation status.
    + As soon as you import the FormsModule, this directive becomes active by default on all <form> tags. You don't need to add a special selector.
    + You optionally export the directive into a local template variable using ngForm as the key (ex: ##myForm="ngForm").
* FormGroup
    + Tracks the value and validity state of a group of FormControl instances
    + A FormGroup aggregates the values of each child FormControl into one object, with each control name as the key. It calculates its status by reducing the status values of its children. For example, if one of the controls in a group is invalid, the entire group becomes invalid.
    + FormGroup is one of the three fundamental building blocks used to define forms in Angular, along with FormControl and FormArray.
* FormControl
    + Tracks the value and validation status of an individual form control.
    + It extends the AbstractControl class that implements most of the base functionality for accessing the value, validation status, user interactions and events.

## What's the 
* untouched: True if control has not lost focus yet.
* touched: True if control has lost focus.
* pristine: True if user has not interacted with the control yet.
* dirty: True if user has already interacted with the control.

## validation 
* Improve overall data quality by validating user input for accuracy and completeness.

## Immutability 
* Immutability is a design pattern where something can't be modified after being instantiated. If we want to change the value of that thing, we must recreate it with the new value instead.

## What are Route Guards in Angular?
* Route guards allow to grant or remove access to certain parts of the navigation. Another route guard, the CanDeactivate guard, even allows you to prevent a user from accidentally leaving a component with unsaved changes.
* A guard's return value controls the router's behavior:
    + If it returns true, the navigation process continues.
    + If it returns false, the navigation process stops and the user stays put.
    + If it returns a UrlTree, the current navigation cancels and a new navigation is initiated to the UrlTree returned.
* The router supports multiple guard interfaces:
    + CanActivate to mediate navigation to a route.
    + CanActivateChild to mediate navigation to a child route.
    + CanDeactivate to mediate navigation away from the current route.
    + Resolve to perform route data retrieval before route activation.
    + CanLoad to mediate navigation to a feature module loaded asynchronously.

## What is a module in angular, and what does it contain?
* In Angular, a module is a mechanism to group components, directives, pipes and services, in such a way that can be combined with other modules to create application.
* There are two types of modules, root modules and feature modules.
* in an application we only have one root module and zero or many feature modules
    + An easy way to identify a root module is by looking at the imports property of its NgModule decorator
    + If the module is importing the BrowserModule then it's a root module
    + if instead is importing the CommonModule then it is a feature module.
* In the same way that in a module we have one root component and many possible secondary components

## NgModule
* Angular apps are modular and Angular has its own modularity system called NgModules.
* NgModules are containers which have components, service, and other code files. 
* They can import functionality from other NgModules, and export functionality.
* Every Angular app has at least one NgModule class, the root module
* most apps have many more feature modules
* An NgModule is defined by a class decorated with @NgModule(). The @NgModule() decorator is a function that takes a single metadata object, whose properties describe the module.
* The @NgModule decorator requires at least three properties: imports, declarations and bootstrap.
    + imports: Other modules whose exported classes are needed by component templates declared in this NgModule.
    + declarations: The components, directives, and pipes that belong to this NgModule.
    + bootstrap: is where we define the root component of our module

## Lazy loading
* load module on demand
* Lazy loading modules helps us decrease the startup time. 
* With lazy loading our application does not need to load everything at once, it only needs to load what the user expects to see when the app first loads.
* Modules that are lazily loaded will only be loaded when the user navigates to their routes.

## What is an observable? 
* An Observable is a Producer of multiple values, "pushing" them to Consumers.
* It is lazy that can synchronously or asynchronously return zero to multiple values over the time.
* Observable is lazy, that means only after you subscribe to it, it will execute and return value. 
* Subscribing to an Observable is similar to calling a Function.
* What is the difference between an Observable and a function? 
    + Observables can "return" multiple values over time, something which functions cannot.
    + Functions can only return one value
* Conclusion
    + func.call() means "give me one value synchronously"
    + observable.subscribe() means "give me any amount of values, either synchronously or asynchronously"
* Creating Observables
    + The Observable constructor takes one argument: the subscribe function.
    + Observables can be created with new Observable. Most commonly, observables are created using creation functions, like of, from, interval, etc.
* Subscribing to Observables
    + When calling observable.subscribe with an Observer, the function subscribe in new Observable(function subscribe(subscriber) {...}) is run for that given subscriber. Each call to observable.subscribe triggers its own independent setup for that given subscriber.
    + Subscribing to an Observable is like calling a function, providing callbacks where the data will be delivered to.
    + A subscribe call is simply a way to start an "Observable execution" and deliver values or events to an Observer of that execution.
* Executing Observables
    + The code inside new Observable(function subscribe(subscriber) {...}) represents an "Observable execution", a lazy computation that only happens for each Observer that subscribes. The execution produces multiple values over time, either synchronously or asynchronously.
    + There are three types of values an Observable Execution can deliver:
        - "Next" notification: sends a value such as a Number, a String, an Object, etc.
        - "Error" notification: sends a JavaScript Error or exception.
        - "Complete" notification: does not send a value.
    + In an Observable Execution, zero to infinite Next notifications may be delivered. If either an Error or Complete notification is delivered, then nothing else can be delivered afterwards.
* Disposing Observable Executions
    + When observable.subscribe is called, the Observer gets attached to the newly created Observable execution. This call also returns an object, the Subscription: const subscription = observable.subscribe(x => console.log(x));
    + When you subscribe, you get back a Subscription, which represents the ongoing execution. Just call unsubscribe() to cancel the execution.

## Observable vs Promise
* Observable
    + observable is lazy, it execute when you subscribe to it.
    + observable is asynchronous or synchronous. 
    + observable can emit multiple values over time.
    + rxjs operators could apply to observable
* Promise
    + promise is eager, it callback will execute once the promise created.
    + promise is always asynchronous.
    + promise may provide only a single value.

## what is subject.
* An RxJS Subject is a special type of Observable that allows values to be multicasted to many Observers. While plain Observables are unicast
* A Subject is like an Observable, but can multicast to many Observers. Subjects are like EventEmitters: they maintain a registry of many listeners

## what are operators
* Operators are functions. There are two kinds of operators:
* pipable operator
    + A Pipeable Operator is a function that takes an Observable as its input and returns another Observable. It is a pure operation: the previous Observable stays unmodified.
    + the operator that canbe piped to observables buy using .pipe() function.
    + the pipable operator do not change the existing observable instance, they return a new one.
    + such as filter.
* creation operator
    + functions that used to create an observable with some common predefined behavior.
    + like of(), from()

## Differences between AngularJS /angular 4 /angular 6
* AngularJS
    + it write application in mvc architecture
    + based on javascript
    + based on controller concept.
* Angular
    + based on typescript
    + based on service/controller
    + conponent based UI approach
* Angular 4
    + Introducing httpclient for http request.
* Angular 6
    + 

## What is a component? Why would you use it.
* Components are the most basic UI building block.
* a component's job is to enable the user experience and nothing more.

## Difference between component and directive.
* A component is a directive-with-a-template.
* Component
    + Component used to create UI.
    + Component is used to break up the application into smaller components
* Directive
    + Directive is used to add behavior to the DOM element
    + Directive is use to design re-usable components

## What is metadata?
* metadata is used to decorate a class, it represented by decorators.
* Decorators are functions that modify JavaScript classes.
* class decorators
    + such as @Component, @NgModule
* Property decorator
    + use for perperties inside classes.
    + such as @Input, @Output
* Method decorators 
    + Used for methods inside classes
    + such as @HostListener
* Parameter decorators
    + Used for parameters inside class constructors
    + @Inject
## what is angular CLI
* command line interface
* creating new project
* generate component, service, pipe, etc.
* running the project.

## What is dependency injection and how does Angular incorporate dependency injection into its framework?
* Dependency injection is an important application design pattern which a class asks for dependencies from external sources rather than creating them itself.
* Dependencies are services or objects that the class need to perform its function.
* DI make your apps flexible, efficient, and robust, as well as testable and maintainable
* Dependency injection (DI) lets you keep your component classes clean and efficient. They don't fetch data from the server, validate user input, or log directly to the console; they delegate such tasks to services.
* The DI framework lets you supply data to a component from an injectable service class, defined in its own file.
* In Angular, the DI framework provides declared dependencies to a class when that class is instantiated.
* @Injectable decorator mark it as a service that can be injected.
* You can tell Angular to inject a dependency in a component's constructor by specifying a constructor parameter with the dependency type.

## What are template expressions?
* A template expression produces a value and appears within the double curly braces, {{ }}. 
* Angular executes the expression and assigns it to a property of a binding target;

## What are template statements?
* A template statement responds to an event 
* It's how you update application state from user action.

## What are pipes?
* pipes to transform data before it is displayed
* Pipes are simple functions that accept an input value and return a transformed value
* impure pipe
    + Angular executes an impure pipe during every component change detection cycle
* pure pipe
    + Angular executes a pure pipe only when it detects a pure change to the input value.
    + A pure change is either a change to a primitive input value or the object reference 
## What is a parameterized pipe?
* A pipe can accept any number of optional parameters

## What is a bootstrapping module?
* Every application has at least one Angular module, the root module that you bootstrap to launch the application is called as bootstrapping module.

## What is HttpClient and its benefits? How do you perform Error handling for HttpClient?
* HttpClient is an http api based on XMLHttpRequest interface, it enable angular to communicate with backend services.
* use catch function. or inside the subscribe function to handle it.

## How can I select an element in a component template?
* set local reference to an element, and use @ViewChild to access the element.

## How would you protect a component being activated through the router?
* use router guard. 

## What is bootstrapping module
* the root appmodule, the application launch from that module. it import the BrowserModule, and have a bootstrap array which specific which component we bootstrap from.

## @ViewChild
* DOM query mechanism 
* return a reference.
* template reference variable ##, to naming dom element, and then using ViewChild decorator to query it in class.

## What are angular component life cycle hooks?
* Directive and component instances have a lifecycle as Angular creates, updates, and destroys them.
* Developers can manage lifecycle by implementing one or more of the lifecycle hook interfaces in the Angular core library.
* Angular creates and renders components along with their children, checks when their data-bound properties change, and destroys them before removing them from the DOM.
* Angular offers lifecycle hooks that provide visibility into these key life moments and the ability to act when they occur.
* A directive has the same set of lifecycle hooks.

## How to bundle an Angular app for production?
* use command under CLI: ng build --prod
* will produce a dist folder with index.html, style.css, and runtime.js, polyfill.js, main.js files

## What is difference between “declarations”,”providers” and “import” in NgModule?
* declarations, Declares which components, directives, and pipes belong to the module. 
* import, Imports other modules with the components, directives, and pipes for the current module.
* providers, Provide service for component to use

## what is ngrx, 
* NgRx is a framework for building reactive applications in Angular.
* NgRx provides state management for creating maintainable explicit applications, by storing single state and the use of actions in order to express state changes.
* Action
    + Actions are one of the main building blocks in NgRx. Actions express unique events that happen throughout your application.
* Reducers 
    + responsible for handling transitions from one state to the next state in your application. Reducer functions handle these transitions by determining which actions to handle based on the action's type.
    + Reducers are pure functions in that they produce the same output for a given input. 

## What is Reactive programming and how to use it with Angular?
* An Angular application is a reactive system. 
* the application react to the event and update the model
* state
    + state is a single value that varies over time.
* event
    + Event streams are sequences of values produced over a period of time
* reified reactive programming
    + access to a concrete object representing the act of observation
    + And having these concrete objects is powerful because we can manipulate them, pass them around, and compose them.
* reactive programming transparent
    + developer only interacts with the most recent value, and the act of observation is hidden in the framework.

## pure function, impure function
* An impure function is a function that mutates variables/state/data outside of it’s lexical scope,
* Pure functions don’t modify external variables/state/data outside of the scope, and returns the same output given the same input.

## switchMap
* Projects each source value to an Observable which is merged in the output Observable, emitting values only from the most recently projected Observable.

## debounce
* Emits a value from the source Observable only after a particular time span determined by another Observable has passed without another source emission.

## Why would you use a spy in a test?
* Jasmine spies are used to track or stub functions or methods. 
* Spies are an easy way to check if a function was called or to provide a custom return value. 
* We can use spies to test components that depend on a service and avoid actually calling the service’s methods to get a value. 

## What is TestBed?
* The TestBed is the most important of the Angular testing utilities. The TestBed creates a dynamically-constructed Angular test module that emulates an Angular @NgModule.

## What is Protractor?
* Protractor is an end-to-end test framework for Angular and AngularJS applications. Protractor runs tests against your application running in a real browser, interacting with it as a user would.

## What is AOT?
* AoT, it stands for the Ahead-of-Time compiler 
* it moves the compilation from run-time to the building process

## What is Redux and how does it relate to an Angular App?
* Redux is a predictable state container for JavaScript apps.
* It helps you write applications that behave consistently, run in different environments (client, server, and native), and are easy to test

## What is Angular Universal?
* renders Angular applications on the server.
* Angular Universal executes on the server, generating static application pages that later get bootstrapped on the client. 

## How to set headers for every request in Angular?
* use HTTP interceptors
* With interception, you declare interceptors that inspect and transform HTTP requests from your application to the server. 

## How to detect a route change in Angular?
* you can subscribe to router to detect the changes.

## Name some security best practices in Angular?
* 

## What is tree-shaking?
## What are Subjects and what are the different types of Subjects?
* An RxJS Subject is a special type of Observable that allows values to be multicasted to many Observers. While plain Observables are unicast
* BehaviorSubject 
    * It stores the latest value emitted to its consumers, and whenever a new Observer subscribes, it will immediately emit the latest value to the subscriber.
* ReplaySubject
    + A ReplaySubject has a buffer to records multiple values from the Observable execution and emit them to new subscribers.
* AsyncSubject
    + only after the execution completed, the last value of the Observable execution is sent to its observers.

## What is Content Projection in Angular?
* Content projection is a way to import HTML content from outside the component and insert that content into the component’s template with ng-content

## What is the difference between authentication and authorization?
* Authentication means confirming your own identity, 
    + Authentication factors determine how the system verify the identity.
    + Single- Factor Authentication: This is the simplest form of authentication method which requires a password to grant user access to a particular system such as a website or a network.
    + Two- Factor Authentication: This authentication requires a two- step verification process which not only requires a username and password, but also a piece of information only the user knows.
    + Multi- Factor Authentication: This is the most advanced method of authentication which requires two or more levels of security from independent categories of authentication to grant user access to the system.
* authorization means being allowed access to the system.
    + Authorization occurs after your identity is successfully authenticated by the system
    + authorization is about whether the user have the permission to access the resource.

## How do you do JWT authentication?
* JSON Web Token using for securely transmitting information between parties as a JSON object. This information can be verified because it is digitally signed.

## When should you use JSON Web Tokens?
* Authorization
    + Once the user is logged in, each subsequent request will include the JWT, allowing the user to access routes, services, and resources that are permitted with that token.
* Information Exchange
    + JSON Web Tokens are a good way of securely transmitting information between parties.
* JSON Web Tokens consist of three parts separated by dots (.),
    * Header
        + The header typically consists of two parts: the type of the token, which is JWT, and the signing algorithm being used, such as HMAC SHA256 or RSA.
    * Payload
        + JSON object with a few properties, these properties are attributes about the user. 
    * signature
        + this signature is based on a secret that exists on the server.
* In authentication, when the user successfully logs in using their credentials, a JSON Web Token will be returned. 
* we could use localStorage to store the jwt to restart session
* Now on the client, we can use this token to identify the user.
* we should include the jwt in the request header.

## component, communicate between it.
* Passing the reference of one component to another
    + This solution should be used when components have dependency between them. For example, dropdown and dropdown toggle
* Communication through parent component
    + Can be used when it’s easy to control shared state between components through their parent component
    + @input, @output
* Communication through Service
    + Finally, this option is useful and should be used when you have component that is controlled, or its state is asked from multiple instances.

## Immutability.
* Immutability is a design pattern where something can't be modified after being instantiated.
*  If we want to change the value of that thing, we must recreate it with the new value instead
* immutable 
* mutable
    + meaning their value can change without having to recreate it.

## Template Driven Forms
* both validation and binding are all setup at the level of the template.
* The upside of this way of handling forms is its simplicity
* On the downside, the form validation logic cannot be unit tested
* The only way to test this logic is to run an end to end test with a browser

## Reactive Forms, Functional Reactive Programming in Angular
* formGroup, formControl
* We can now unit test the form validation logic
* the form controls and the form itself now provide an Observable-based API. such as valueChange()
* Everything can be done in both form types, but some things are simpler using reactive forms

## lazy loading 
* lazy-loading—that is, loading modules on demand—to minimize the amount of code that needs to be loaded at startup.

## tdd 
## bdd 
* behavior test
## CI/CD pipeline
* continuous integration/ continuous delivery
* DevOps handle cicd
* travis/ jenkins

## unit test
* focus on js
* test function itself inside component.

## shallow test.
+ test js, also test html check the dom change.

## testbed
* simulate angular component.

## integration test
## e2e test

## jasmine-karma/ jest / 
* Jasmine as the testing framework, it is behavior driven testing. to write readable testing code.
* Karma as the test runner.