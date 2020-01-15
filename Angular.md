# Angular Single Page Applications (SPA): What are the Benefits?
* Single Page Applications are super easy to deploy in Production, and even to version over time!
* a much-improved user experience due to less full page reloads and a better overall performance because less bandwidth is needed.
    - On a SPA, after the initial page load, no more HTML gets sent over the network. Instead, only data gets requested from the server (or sent to the server).
    - So while a SPA is running, only data gets sent over the wire, which takes a lot less time and bandwidth than constantly sending HTML. 
* In a SPA after application startup, the data to HTML transformation process has been moved from the server to the client – SPAs have the equivalent of a template engine running in your browser!

# What is TypeScript and why would I use it in place of JavaScript? [closed]
* TypeScript is a superset of JavaScript which primarily provides optional static typing, classes and interfaces. One of the big benefits is to enable IDEs to provide a richer environment for spotting common errors as you type the code.

# Data Binding
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
    + We have seen that in one-way data binding any change in the template (view) were not be reflected in the component TypeScript code. To resolve this problem, Angular provides two-way data binding.
    + In two-way databinding, automatic synchronization of data happens between the Model and the View. Here, change is reflected in both components. Whenever you make changes in the Model, it will be reflected in the View and when you make changes in View, it will be reflected in Model. 
    + This happens immediately and automatically, ensures that the HTML template and the TypeScript code are updated at all times.
    + In two way data binding, property binding and event binding are combined together.
    + [(ngModel)] = "[property of your component]" 
    + Note: For two way data binding, we have to enable the ngModel directive. It depends upon FormsModule in angular/forms package, so we have to add FormsModule in imports[] array in the AppModule.

# Directives
* The Angular 8 directives are used to manipulate the DOM. By using Angular directives, you can change the appearance, behavior or a layout of a DOM element. It also helps you to extend HTML.
* Component Directives
    + it
    + Component directives are used in main class. They contain the detail of how the component should be processed, instantiated and used at runtime.
* Structural Directives
    + structural directives start with a * sign. These directives are used to manipulate and change the structure of the DOM elements. For example, *ngIf directive, *ngSwitch directive, and *ngFor directive.
* Attribute Directives: 
    + Attribute directives are used to change the look and behavior of the DOM elements. For example: ngClass directive, and ngStyle directive etc.

# What is service
* Most front-end applications communicate with the backend services over an HTTP protocol. Modern browsers support the two different APIs for making HTTP requests.
    - XMLHttpRequest interface and the 
    - fetch() API.
* We will use XMLHttpRequest for Angular application.
* If an angular app needs to interact with the back end server, then we can write the API calling code inside the service file.
* So, if we need to send a POST request to the server, then we import the HttpClient inside the service file and make an AJAX request to the server with the data object. After a successful request, the server sends a response back to the client.
* separate presentation of the data from data access by encapsulating the data access in the separate service and delegating to that service in a component.

# Life cycle hook and constructor
* constructor is executed when the class instantiated
    + The constructor should only be used to initialize class members but shouldn't do actual "work".
    + So you should use constructor() to setup Dependency Injection and not much else
* ngOnInit indicate that Angular is done creating the component
    + Called after the constructor and called  after the first ngOnChanges() 
    + Mostly we use ngOnInit for all the initialization/declaration and avoid stuff to work in the constructor

# How do you submit a form.
* use (ngSubmit)

# What is the difference between ngForm, FormGroup, FormControl.
* ngForm
    + Creates a top-level FormGroup instance and binds it to a form to track aggregate form value and validation status.
    + As soon as you import the FormsModule, this directive becomes active by default on all <form> tags. You don't need to add a special selector.
    + You optionally export the directive into a local template variable using ngForm as the key (ex: #myForm="ngForm").
* FormGroup
    + Tracks the value and validity state of a group of FormControl instances
    + A FormGroup aggregates the values of each child FormControl into one object, with each control name as the key. It calculates its status by reducing the status values of its children. For example, if one of the controls in a group is invalid, the entire group becomes invalid.
    + FormGroup is one of the three fundamental building blocks used to define forms in Angular, along with FormControl and FormArray.
* FormControl
    + Tracks the value and validation status of an individual form control.
    + It extends the AbstractControl class that implements most of the base functionality for accessing the value, validation status, user interactions and events.

# What's the 
* untouched: True if control has not lost focus yet.
* touched: True if control has lost focus.
* pristine: True if user has not interacted with the control yet.
* dirty: True if user has already interacted with the control.

# validation 
* Improve overall data quality by validating user input for accuracy and completeness.

# Immutability 
* Immutability is a design pattern where something can't be modified after being instantiated. If we want to change the value of that thing, we must recreate it with the new value instead.

# -----FAQ on Angular-----
# What are Route Guards in Angular?
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

# What is a module in angular, and what does it contain?




What are pipes? Give me an customized Pipe example that u write for your most recent project
Differences between Angular JS /angular 4 /angular 6
What is a component? Why would you use it.
Difference between component and directive.
What is a service in angular, and when will you use it.
How can I select an element in a component template?
How would you protect a component being activated through the router?
What is an observable? Observable vs Promise
What is bootstrapping module
What are angular component life cycle hooks?
Why should ngOnInit be used, if we already have a constructor?
How to bundle an Angular app for production?
What is difference between “declarations”,”providers” and “import” in NgModule?
What is Reactive programming and how to use it with Angular?
Why would you use a spy in a test?
What is TestBed?
What is Protractor?
What is AOT?
What is Redux and how does it relate to an Angular App?
What is Angular Universal?
How do you perform Error handling for HttpClient?
How do you do data binding in Angular?
How to set headers for every request in Angular?
How to detect a route change in Angular?
Name some security best practices in Angular?
What is tree-shaking?
What are Subjects and what are the different types of Subjects?
What is the difference between Subject and Observable?
What is the difference between BehaviorSubject vs Subject?
What is Content Projection in Angular?
What is dependency injection and how does Angular incorporate dependency injection into its framework?
What is the difference between authentication and authorization?
How do you do JWT authentication?
How do you do authorization in Angular?





2:40
FAQ on Javascript: What is coercion in JavaScript
What is Scope in JavaScript
Explain equality in JavaScript
Null / Undefined in JavaScript
What is strict mode in JavaScript
What is a Polyfill
Var / let / const
Explain event bubbling and how one may prevent it.
How to empty an array in JavaScript
How to check if an object is an array
How would you use a closure to create a private counter
Add(5)(10)(8) // return 23
Callback function example
How to iterating over object properties and array items?
Why we need to avoid touching global scope and how to avoid it.
DOM event DOMContentLoaded
Deep Copy in js
ES5 vs ES6
Undefined vs not defined
Rest operator vs spread operator
What is currrying in js
What is high order function

# what is obserable, why use it, example?
# component, communicate between it.
# immuteablity.
# formcontrol.
# redux, why use it.
# subject, @input, @output.
# redux
# lazy loading
# unit test, how to mock.
