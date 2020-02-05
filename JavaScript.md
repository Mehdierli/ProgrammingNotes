## What is coercion in JavaScript
* it relate to type conversion, it can be implicit or explicit.
* explicit means we convert the type.
* implicit means interpreter do the conversion.
* explicit type coercion
    - point out which type convert to by code.
    - such as Number(value)
* implicit type coercion
    - values convert between differnent type automatically.
    - such as 1 == null, 
    - == will triger implict type coercion
    - === will not triger implicit type coercion
    - it allows us to write less code.
+ three type of conversion, only three types.
    - to string
    - to boolean
    - to number 
    - both primitive and object can only convert into those three way.
+ to string
    - explicit type coercion, with String()
        - such as String(-11.123) //'-11.123'
        - String(null) //'null'
        - String(true) //'true'
    - implicit type coercion, triggered by + operator, when any operand is a string
        - such as 'abc' + null
        - it will convert null to string firstly, with String(null)
+ to boolean
    - explicit, with Boolean()
        - only these values will convert to false, all others will convert to true.
        - Boolean(null) //false
        - Boolean(undefined) //false
        - Boolean('') //false
        - Boolean(0) //false
        - Boolean(-0) //false
        - Boolean(false) //false
        - Boolean(NaN) //false
    - implicit, it triggered by logical operators(||,&&,!)
+ to number
    - explicit, with Number()
        - NuNumber(null)                   // 0
        - Number(undefined)              // NaN
        - Number(true)                   // 1
        - Number(false)                  // 0
        - Number(" 12 ")                 // 12
        - Number("-12.34")               // -12.34
        - Number("\n")                   // 0
        - Number(" 12s ")                // NaN
        - Number(123)                    // 123
    - implicit, triggered by math operators. except + operator which will convert the type to string. 
    - two special rules:
        - NaN not equal to anything even itself.
        - null only equal to null and undefined under implicit type coersion.
* type coercion for objects
    - for Boolean, all obejct convert to ture.

## Explain equality in JavaScript
* we have two equality operator,
* strict and loose equality operator. 
* strict will not cause the type coercion
* loose will be caues the type coercion
* coercion is relate to the type conversion
* it will automatically convert the data type.
* coercion usually caused by operators.
* strict equality operator
    - no type conversion applied.
* loose equality operator 
    - it will do some type conversion, and then comparison.
    - that means, it will automatically convert the two different data type into same data type, and then compare them.

## What is Scope in JavaScript
* scope determine the visibility of the resources, such as variable, function.
* here we have some defination of scope,
* global scope
    - only one global scope in javascript document, 
    - it is the most outside of the file. it is the window.
    - all the variable defined in global scope can be accessed in any other scopes.
* local scope
    - it is function scope or block scope.
    - it is the area that inside the function or a block.
* function scope
    - function scope is declare the variable inside a function.
    - var is the keyword to define a functin scope variable.
    - if you declare a variable inside a function. and the function is visible only within the function. you cannot access it outside the function. 
* block scope
    - is the area within if, switch or for, while loop, 
    - generally, if you see curly brackets, it is a block. 
    - let and const keywords define the variable with block scope.
* lexical scope
    - lexical scope means the children scope could access the variables defined in parent scope.

## Null / Undefined in JavaScriptshit
* null is a value, it represent no value.
* null can be assign to a variable.
* undefined means you declared a variable, but did't initialize it or didn't assign it a value.

## What is strict mode in JavaScript
* strict mode declared by adding 'use strict' directive at the beginning of a script or a function.
* purpose of using strict mode
    - eliminates some js silent errors by throw error.
    - fixes mistake that make it difficult for js engine to perform optimizations.
    - sometimes could run faster than unstrict mode.
    - prohibits some syntax.

## What is a Polyfill
* polyfill is a piece of code that provide modern feature to older browers.

## Var / let / const
* variable declared by Var has function scope
* let and const use for block scope
* the different between let and const is that
* we must be initialize the const variable, 
* and we cannot reassign another value to it.
* however, if the value we assigned to const variable is complex type
* we could change its element or property inside it.

## Explain event bubbling and how one may prevent it.
* when an event happens on an element, it first run the handler on it, then it run on all the ancestors who has same event from innner element to outer element.
* we have two method to prevent it. first one is stopPropagation, this method allow other handler on the same element execute, but will prevent the handler on its ancestor elements. another method is stopImmediatePropagation, it will prevent every event.

* event.target
    - the most deeply nested element that caused the event is called a target element, accessible as event.target
    - this is the current element, the one curretly running the handler
    - event.target is the target element that initiated the event, it doesn't change through the bubbling process.
* stop bubbling
    + event.stopPropagation()
        - it will stop the move upwards, but if the current element has multiple handler, all other handlers will run.
    + event.stopImmediatePropagation()
        - stop the bubbling and prevent handlers on the current element from running, means no other handlers execute.
    
## How to empty an array in JavaScript
* assign an empty array to the variable, it acctually will create a new empty array to the variable, it means the original array not effect.
* second method is change the array's length equal to 0, that will delete everything in the array, all the reference to this array will be affect.

## How to check if an object is an array
* we could use instanceof to check, such as, [1,2] instanceof Array
* also we could use isArray method of Array to check it.

## How would you use a closure to create a private counter
* we could create a function that allows you to update a private variable but that variable cannot be access from outside of the function. 
* so we should be return some helper function to access the variable or change the variable.
'''
function counter() {
  var _counter = 0;
  // return an object with several functions that allow you
  // to modify the private _counter variable
  return {
    add: function(increment) { _counter += increment; },
    retrieve: function() { return 'The counter is currently at: ' + _counter; }
  }
}
'''

## callback function example
'''
function foo(cb){
    cb();
}
function cb(){
    console.log('i am callback')
}
foo(cb);
'''

## How to iterating over object properties and array items?
* for Array, we could use forEach, or for loop, or while loop.
* for object, we could use for...in loop or the keys() method from object.
    - for (const property in object){console.log(property,object[property])}
    - Object.keys(obj);
    * one most important thing is that no matter how you declare the property, if the keys is same, the returned value from keys() will have same order.
        '''
        obj={1:1,3:3,2:2}
        obj1={3:3,2:2,1:1}
        for (const property in obj){
            console.log(property,obj[property])
        } //1 1,2 2,3 3
        for (const property in obj1){
            console.log(property,obj1[property])
        } //1 1,2 2,3 3
        '''
## Why we need to avoid touching global scope and how to avoid it.
* because in javascript, all code share one global namespace, everyone could access it and modify it， also its hard to read the code, or have name clash.
* we could explicit define the variable, such as use let or const.

## DOM event DOMContentLoaded
* after the html document loaded and parsed, it wiil be run, it doesn't wait other resource.
* this event fired when the initial html document has been completely loaded and parsed.
* it doesn't wait the stylesheet, images, and subframe to finish loading.

## load
* this event run after the whole page loaded.
* this event fired when the whole page loaded, include stylesheet, images, and all other dependent resouces

## Deep Copy in js
* deep copy is copy everything, new memory space will be allocate to the new variable. in this case, if the old variable changed, the new variable will not be effected.

## showllow copy
* the new object just has the memory addredd copied, if old obejct is change, the new object also change.

## ES5 vs ES6
* ES is standardised scripting language for javascript.
* es5 and es6 have some syntax different.
* such as arrow function
* promise
* blocking scoping
* object manipulation

## Undefined vs not defined
* undefined is you declared a variable, but didn't assign a  value to it.
* not defined is an error, it happened when you invoke a variable that not declared.

## Rest operator vs spread operator
* rest parameter is an array, it have indefinite number of arguments.
* spread operator allows an iterable or object expand in place.
* such as expand an array in another aray, or expand an object in another object.

## What is currrying in js
* Currying transforms a function with multiple parameters into a sequence of functions, each take a single parameters. 
* the most inside function will use the parameters from all the previous function to do some task, because of the closure, the most inside function have reference to the previous function's parameters. 
* write little code modules that can be reused and configured
* avoid frequently calling a function with the same argument.

## What is high order function
* it take one or more function as argument,
* return a function as a result.

## what is relationship between Object and Function
* function is a Function object, which belong to Object.
* In JavaScript, functions are first-class objects, 
* because they can have properties and methods just like any other object. 
* What distinguishes them from other objects is that functions can be called. 
* In brief, they are Function objects.

## what is first class function
* function is treat like any other variable, you can return a function, you can assign the function to a variable, you can pass the function as a argument to another function.

## what is closure
* closure is formed by function.
* a closure is the combination of a function and its lexical environment within that the function was declared. 
* which means, inner function could access the outer function variable.
* that is, we could create private variable.

## dom lifecycle
* DOMContentLoaded event – DOM is ready, so the handler can lookup DOM nodes, initialize the interface.
* load event – external resources are loaded, so styles are applied, image sizes are known etc.
* beforeunload event – the user is leaving: we can check if the user saved the changes and ask them whether they really want to leave.
* unload – the user almost left, but we still can initiate some operations, such as sending out statistics.

## what is callback use for
* Note, however, that callbacks are often used to continue code execution after an asynchronous operation has completed — these are called asynchronous callbacks.

## what is prototype?
* it is an object.
* it is a property of constructor function, we could add property or method to it.
* so all the instance could be share the method or property in the prototype.
* prototype chain is use for the inheritance.

## storage, sessions on browser
* local storage, cookies, session storage.
* local, session provide by browser.

## cookies, 
* Cookies were once used for general client-side storage, Cookies are sent with every request, so they can worsen performance 
* each domain have its own cookie
* main purpose communicate between cli and server
* cookies will store some data.
* data store in cookies will be sent with XMLHttprequest call.
* limitation, the size, cannot store to much data.

## local storage
* not disappear, if you close browser
* the data will be store forever, if you not clear it.

## session storage
* after close brower, the data will be remove.

## Object.defineProperty
* The static method Object.defineProperty() defines a new property directly on an object, 
* or modifies an existing property on an object, and returns the object.
* set
    - for complex type, the set function will check the address of the property to see whether it is changed, such as Array.
* get

## SPA dynamic

## what is promise
* promise is an object using for handle the asynchronous task.
* it will finally produce resloved value, or reject vlaue.
* promise have three state, first is pending, its the initial state,
* second is fullfilled, means promise resloved some value
* third is rejected, means promise rejected some value. 

## meta tag
* viewport, seo, charset

## sematic html
* 508 policy, aria

## iframe / a target / window.location / window.navigator
## async await / promise / fetch

## XMLHttprequest
* use to request data from a web server, and update a part of the page.

## event bubbling / capture

## event.preventdefault
* cancel the event, means the default action that belong to the event will not occur.

## event.delegation
* use for add same event for many similar element.
* add event to the elements' parent, then all the element could trigger the event.