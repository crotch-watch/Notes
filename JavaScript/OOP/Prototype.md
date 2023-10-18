# **Prototype**

Each ***`function`*** in javascript has a property called ***`prototype`***.

The ***`prototype`*** property of a ***`Function`*** instance is used when the function is used as a **constructor** with the ***`new`*** operator. It will become the new object's **prototype**.

Every object created by **Constructor Functions** will get access to the properties defined on prototype property of contructor function

When a function is called with ***`new`*** the constructor's ***`prototype`*** property will become the resulting object's prototype.

![[prototype_exxample1.png]]

above ***example*** solves problem of redundancy by defining calcAge in **Constructor's body**.

> **NOTE** : ***`Person.prototype.calcAge`*** happens in execution phase

***`me.__proto__`*** is the prototype of ***`me`*** object which is **prototype property** of ***`Person`***.

***`__proto__`*** is linked to ***`prototype`*** property when calling with ***`new`***.

**Own Property** of an object is directly defined on it, this excludes properties on objects's ***`[[Prototype]]`***.

***`isPrototypeOf`*** method checks whether objects ***`[[Prototype]]`***  is ***`prototype`*** property of **Constructor** and ***`hasOwnProperty`*** method checks whether provided argument is an **own property** of object.
