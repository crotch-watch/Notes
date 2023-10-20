# **ES6 Classes**

Classes are an abstraction over the **Constructor Function**.

First add a ***`constructor`*** method to the ***`class`*** and it has to be called ***`constructor`*** and we pass arguments to it like **Constructor Functions**, which are the properties which we want to add to the object.

We call ***`class`*** using the ***`new`*** keyword which calls the **Constructor Method** on the ***`class`***.

Similar to the constructor functions, ***`this`*** keyword inside the **Constructor Method** will be set to the **Empty Object** created as a result of calling it with ***`new`*** keyword.

We add methods onto the ***`class`*** body which is similar to adding them to ***`constructor.prototype`***

![[es6_classes1.png]]
[**Code**](https://codesandbox.io/s/lively-leaf-6fs97g?file=/src/OOP/ES6_Class/classes1.js)

***`class`*** is treated as **First Class Citizens**, we can pass them into **Functions** and ***`return`*** them from **Functions**.

The **Class Body** of a ***`class`*** **declaration** is executed in ***`strict mode`***. The ***`class`*** declaration is very similar to ***`let`***.

- ***`class`*** declarations are scoped to **Blocks** as well as **Functions**.

- ***`class`*** declarations can only be accessed after the place of declaration is reached (see **Temporal Dead Zone**) For this reason, ***`class`*** declarations are commonly regarded as **Non-Hoisted** unlike **Function Declarations**.

- ***`class`*** declarations do not create properties on ***`globalThis`*** when declared at the top level of a script (unlike **Function Declarations**).

- ***`class`*** declarations cannot be **Redeclared** by any other declaration in the same scope.

Outside the class body, ***`class`*** declarations can be **Re-Assigned** like ***`let`***, but you should avoid doing so. Within the class body, the binding is constant like ***`const`***.
