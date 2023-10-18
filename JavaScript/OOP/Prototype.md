# **Prototype**

Each ***`function`*** in javascript has a property called ***`prototype`***.

The ***`prototype`*** property of a ***`Function`*** instance is used when the function is used as a **constructor** with the ***`new`*** operator. It will become the new object's **prototype**.

Every object created by **Constructor Functions** will get access to the properties defined on prototype property of contructor function 

When a function is called with ***`new`*** the constructor's ***`prototype`*** property will become the resulting object's prototype.

above ***example*** solves problem of redundancy by defining calcAge in **Constructor's body**.

> **NOTE** : ***`Person.prototype.calcAge`*** happens in execution phase

***`me.__proto__`*** is the prototype of ***`me`*** object which is **prototype property** of ***`Person`***.

***`__proto__`*** is linked to ***`prototype`*** property when calling with ***`new`***. ref step 2 OOP 

key is not on obj. it is on proto