## **Prototypal Inheritance**

When a property can't be found on the object, then it is looked into object's ***`[[prototype]]`***

Object's ***`[[Prototype]]`*** points to ***`Person.prototype`***. Object's ***`[[Prototype]]`*** just stores the address of ***`Person.proto`*** i.e. ***`Contructor.prototype`***.

This behaviour of storing properties and methods in ***`Parent.prototype`***  is called **Prototypal Inheritance**.

![[prototypal_inheritance1.png]]

> **NOTE** : Storing methods and properties in **one place** only and referring them is essential for **code performance** since creating these properties for each object does not make sense. **DRY** principle.

## **Prototype Chain**

![[prototypal_inheritance2.png]]

In **Prototype Chain** each ***`object.prototype`*** points to its ***`parent.prototype`*** and this continues till the **property is found** or **chain reaches the end** on ***`Object.prototype`*** which points to ***`null`***.
