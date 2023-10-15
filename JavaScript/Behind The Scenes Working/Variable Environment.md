# **Variable Environment**

## **Hoisting**

![[Variable_Environment_intro.png]]
**HOISTING** introduction and basics

## **Why was TDZ  introduced**

![[TDZ, let and const.png]]

- Makes it easy to avoid and catch errors since accessing variables before declaration can lead unexpected results.

- To make ***`const`*** concept work they should not be re-assignable. it should not be first undefined and then be assigned the value.

- **`consts`** are assigned only when code execution reaches the line of declaration.

> **NOTE**  hoisting was introduce to implement **`mutual recursion`** and var's hoisting was a side effect.

![[TDZ_example.png]]  
[***Code***](https://codesandbox.io/s/jovial-grass-2ptp8c?file=/src/index.html:0-272)

TODO: try giving or linking or both example that can be copied.

in above example we access variables before declaring and get an error

TODO: try implementing linking from img to code nd keywords to their pages

![[unexpexcted_behaviour.png]]
above example shows how **`var's hoisting`**  can cause unwanted affects like deleting products instead of saving them.

## ***`Arguments`*** Object

![[arguments_object_example1.png]]
[**Code**](https://codesandbox.io/s/lively-leaf-6fs97g?file=/src/Arguments_Object/example1.js)

***`arguements`*** don't exist in arrow function and it was used to handle arguments passed to the function. An example would be an **add function** which in theory could take **infinite arguments** but we can't account for all passed arguments in function to store them since we would never know the exact number. In that case we can use arguments to gather all values. 

> **NOTE**: We have **rest operator** that is  ***`...`*** 3 dots next to one another to handle these scanarios.
