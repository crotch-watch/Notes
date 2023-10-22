# **Inheritance**

## **Inheritance in Constructor Functions**

![[inheritance_constructor1.png]]
[**CODE**](https://codesandbox.io/s/lively-leaf-6fs97g?file=/src/OOP/Inheritance/Constructor_function.js)

Since student function will need access to ***`firstName`*** and ***`birthYear`*** as well since when we call ***`Student`*** we don't explicitly call ***`Person`*** as well that does not make sense as we would have to call every ancestor constructor when instantiating a constructor, Therefore we have to pass parameters for every constructor we inherit.

But calling it with a new keyword we will face an error since this inside of the function will be undefined. Therefore we also need to pass a ***`this`*** context to the Person which can be done by calling it via a call method. Since this inside of the Student will be reference of empty object there for Person would execute as intended.

But we still need to link the prototype property of Student to where we want JS to look it up if it is not found. hence we need to link ***`Student.prototype.__proto__`*** to ***`Person.prototype`***

> **NOTE** : ***`__proto__`*** works as an **entry point** to where we want **JavaScript** to look up when it does not find  property in current prototype.

We can do it manually by assignment or via ***`Object.create`***.

***`Student.prototype.constructor`*** will point back to Person since constructor property does not exist on ***`Student`*** so it looks up the **prototype chain** and it is present on the ***`Person`***.

## **Inheritance in *`Class`***

To implement inheritance between classes there are only 2 prerequisites

1. ***`extends`*** :-  
	links the prototypes of the classes.

![[inheritance_classes1.png]]
[**CODE**](https://codesandbox.io/s/lively-leaf-6fs97g?file=/src/OOP/Inheritance/classes.js)   [**CODE** ***`Person`***](https://codesandbox.io/s/lively-leaf-6fs97g?file=/src/OOP/ES6_Class/classes1.js)

2. ***`Super`*** :-
	In the ***`constructor`*** body of a derived class (with ***`extends`***), the ***`super`*** keyword may appear as a "function call" (***`super(...args)`***), which must be called before the ***`this`*** keyword is used and before ***`constructor`*** returns. It calls the parent class's ***`constructor`*** method.

We don't need to call ***`constructor`*** or ***`super`*** in case child ***`class`*** does not accept any arguments. In that case ***`constructor`*** will be called automatically.

## ***`Object.create`***

![[inheritance_objectCreate1.png]]
[**CODE**](https://codesandbox.io/s/lively-leaf-6fs97g?file=/src/OOP/Inheritance/ObjectCreate.js)
