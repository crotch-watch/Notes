# **OOP in Js**

## **Introduction**

All objects in JS are linked to a **prototype object**.

Each object has a **prototype** which has **methods** and **properties** which any objects linked with it can access and use, this behaviour is called **Prototypal Inheritance**.

In JS's case we have **instance inheriting from class** rather than ***`class`*** inheriting from ***`class`***

![[OOP_js1.png]]

In above **example** we have map which is ***`Array.prototype.map`*** and since every ***`Array`*** object is is linked to ***`Array.prototype`*** therefore array can access map.

## **Achieving Inheritance in JS**

![[OOP_js2.png]]

1. **Constructor Functions**
Creating objects **programmatically** using **functions** which is used for built in objects.

2. **Classes**
These are **syntactical sugar** over constructor functions,  just **abstraction** over **constructor functions**

3. ***`Object.create`***
