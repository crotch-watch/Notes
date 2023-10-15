# ***`this`*** Keyword

![[this_example_1.png]]
[**Code**](https://codesandbox.io/s/lively-leaf-6fs97g?file=/src/example1.js)

Here ***`myself.greet()`*** method logs **hey undefined** since **arrow functions** don't have a ***`this`*** in their variable environment and hence they borrow it from nearest neighbour who has a ***`this`***, which in this case is ***`window`***.

> **NOTE** : Try avoiding using arrow functions as methods unless necessary. Since they don't have ***`this`*** and **regular functions** can achieve the same.

![[this_example_2.png]]
[**Code**](https://codesandbox.io/s/lively-leaf-6fs97g?file=/src/example2.js)

In above example we have have a case where **`arrow functions`** can be used in **`objects`**.
***`one()`*** logs undefined since it is normal function and is not called from an object directly like ***`myself.one()`*** but since two is an arrow function it gets the ***`this`*** of nearest parent [[Execution Context]].

> **NOTE** : ref. line 5 in above example ***`const self = this`*** is used to capture reference of object to be in used in ***`one`***, if we try to grab ***`this`*** like a normal variable by just declaring it  inside function block it would be ***`undefined`*** since ***`this`*** is dynamically assigned inside every function's **variable environment** and can't be directly taken via **scope chain**. Since in trying to access it would be like trying accessing a **shadowed variable** since ***`this`*** explicitly would be dynamically re-assigned in ***`one`***'s variable environment .
