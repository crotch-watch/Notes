# **Constructor Functions**

**Constructor functions** are **regular functions** but we call them using the ***`new`*** keyword.

> **NOTE** : There is a **convention** in OOP, constructor functions are written in **Pascal Case**. Built-in contructors like ***`Array`***, ***`Map`*** also follow this convention.

We can only use **Function Declarations** and **Function Expressions** since arrow functions dont have a ***`this`***.

When we call a ***`function`*** with ***`new`*** following 4 steps take place

1. Creates a blank, plain JavaScript object. For convenience, let's call it ***`newInstance`***.

2. ***`{}`*** is linked to a ***`prototype`***

Points ***`newInstance`***'s ***`[[Prototype]]`*** to the constructor function's ***`prototype`***  property, if the ***`prototype`*** is an ***`Object`***. Otherwise, `newInstance` stays as a plain object with ***`Object.prototype`*** as its ***`[[Prototype]]`***.

3. ***`function`*** is called and ***`this`*** is set to the **newly created empty object**. In the execution context of the ***`function`***, ***`this`*** points to empty object. ref. step 1.

Executes the constructor function with the given arguments, binding `newInstance` as the ***`this`*** context (i.e. all references to ***`this`*** in the constructor function now refer to `newInstance`).

4. ***`function`*** automatically return the empty object ***`{}`*** and inside the function body we can operate on ***`{}`*** and modify it.

![[constructor_example1.png]]
[**CODE**](https://codesandbox.io/s/lively-leaf-6fs97g?file=/src/OOP/Constructor_example1.js)

> **NOTE** : convention is to create a property on ***`{}`*** which we pass as argument in **constructor**. In our case ***`firstName`*** and ***`birthYear`***

we can use ***`instanceof`*** operator to check whether an object is **instance of** provided **constructor**. Properties created on all **instances** of a **contructor** are called **Instance Properties**.

> **NOTE** : Don't define methods inside of the constructor functions since they will be created everytime the constructor is called and results in duplicacy. Instead they should be inside ***`prototype`***.
