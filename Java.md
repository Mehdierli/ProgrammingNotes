## What is the difference between interface and abstract class?
* main difference is in interface everything is abstract, and abstract class could have implementation for the method.
* variable in interface by default is final.
* method for interface by default is public.
* interface should be implemented by using keyword implement. abstract class use extends keyword.
* a class could implement multiple interface, and one extend on class.

## Why to override equals and hashCode methods?
* hashCode() method is used to get the hash Code of an object. hashCode() method of object class returns the memory reference of object in integer form. 
* equals method is used to check that 2 objects are equal or not. This method is provided by Object class.
## What is overloading?
* multiple method which have same name, but its signature is defferent, by the number of parameter is different or the parameter is different or both.

## What is overriding?
* in the child class it implement a method that already implement by the parent class. And the medthod should be same name same signature.

## What is garbage collection?
* In Java the programmer do not need to care for the object that no longer in use. garbage collector will destory these object. 
* the main purpose of garbage collector is free the heap memory by destory the unreachable object. which unreachable object is that there is no reference to it.
* and the garbage collector always running in background.

## What is an immutable class?
* means after we create the instance, we cannot change its content.
* the class must be declared with final keyword.
* members in class must be declared with final keyword.
* no setter method.

## Are parameters to functions passed by value or reference?
* pass by value, for primitive type, it pass a copy of the value to the function
* for object, if we create a instance and assign it to a variable, the variable in fact store the memory address, which is reference.
* when we pass an obejct into a function, it will pass a copy of the reference to the function. that is we copy the reference from the varibale, and pass it into the function.

## What are final variables, final methods and final classes in Java?
* final
    + keyword could use for class, method, and attribute.
    + attribute cannot be change after initalized 
    + method cannot be override
    + class cannot be subclassed.
* finally
    + using in the try catch finally,
    + that meaning, the finnaly block will execute anyway.
* finalize
    + this method will be called before the garbage collector delete the object.
    + Object class contain this method

## What is the internal implementation of HashMap in Java?
* A bucket is one element of HashMap array. It is used to store nodes. Two or more nodes can have the same bucket. In that case link list structure is used to connect the nodes.

## How to do thread safety in Java?
* Thread safety in java is the process to make our program safe to use in multithreaded environment
* Synchronization is the easiest and most widely used tool for thread safety in java.
* use lock
* Using thread safe collection classes

# You worked on backend spring boot? ->Java version, modern java features
* yes, use spring boot, and java 8.
* some new features, such as map, reduce, filter.
* Optional class to replace null checks.

# You have experience in spring boot,which module?
* built restful api

# Data access layer? Hibernate JDBC
* for each table in database, we build a interface that extends JpaRepository, also we could write some query inside the interface.
* hibernate is orm technology. each table is a class, each column is attribute, each row is instance.

# Java Generics, why is it useful,
* similar to the template in C++
* we could use it for functions, classs, interface. 
* for example, generic functions that can be called with different types of arguments based on the type of arguments passed to generic method.
* advantage
    + code use, we could write one method/interface/class for different data type.
    + type safety, show the error at compile time.

# Difference == isEqual
* double equal sign is operator, isEqual is a method.
* they are using for compare obejct, different is 
* == check the memory address.
* isequal check the content of the object.


# comparator comparable 
* comparable is an interface, we implement it in the class in order to compare its instance.
* comparator usually passed as argument to some high order function, such as sort method. it is a class, we new a instance and pass the instance to the high order function.


# Springboot how do you build restful application from scratch
* create spring boot project with dependencies
* configure database connection
* create an Entity class correspond to the table
* create JPA Data repository layer
* create service layer to manipulate the database
* create restful api layer to use service.
* finannly is unit testing for api request.

# Micro service from scratch, how do you build a microservice application from scratch.
* it is the microservice architecture, that structure an application as a collection of services.

# Integration with ORM,
# Database experience
* some experience with relational database.

# tell transaction in spring
* not fimilar with that.

# Dependency injection

# what are  difference bean scope, default bean scope: singleton
* singleton
    + by default，only one instance created for the spring container.
* prototype
    + a new instance created for each request from spring container
* request
    + similar to prototype, however the new instance created for each http request.
* session
    + a new bean created for each http session.
* global-session
    + use for create global session beans.

# 17 How do use AOP: 
* AOP breaks the program logic into distinct parts (called concerns). It is used to increase modularity by cross-cutting concerns.

# Operator in observable you use map, pipe,
20 how do you create rest api in angular: services => components => html
21 how do you build api, use api in details
22 lifecycle of angular: ngInit, ngDestroy, how do you destroy? 
23 what’s event emitter
24 AOT tree-shaking?
25 difference ngOnsubmit ngOnClick
