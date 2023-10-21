# **Accessor Properties**

## **Introduction**

All objects have **Getters** and **Setters** these are called **accessors** and other normal properties are called **data properties**.

**Getters** and **Setters** are functions that get and set a value but from the outside they look like a property and not method. To make a method a **Getter** or **Setter** we simply prepend it with ***`get`*** or ***`set`*** keyword

## **Getters**

***`get`*** accessor can't have parameters and **Getters** can  useful when we need to do some **Operations** and then access a result as a **Property**.

**Getters** and **Setters** are available in ***`class`*** and work in same way as **Constructor functions**

![[accessor_properties1.png]]
[**CODE**](https://codesandbox.io/s/lively-leaf-6fs97g?file=/src/OOP/Accessor_properties/example1.js)

> **NOTE** : Three dots in console output means it is only calculated when it is clicked.

## **Setter**

**Setter** can used for **Performing Operations** before setting the property and making it look like a **Assignment** rather than a method. They only have one **parameter**.

> **NOTE** : In ***`class`*** body we have properties to be added to ***`Constructor.prototype`*** but since ***`constructor`*** method will only be executed when it is called with ***`new`***.Till then class body will be parsed and properties will be added to ***`Constructor.prototype`***. Therefore when ***`constructor`*** would be called we would already have the properties in ***`Constructor.prototype`*** so they can be accessed in constructor.
> Hence when we can ***`new Person()`***  we have access to ***`fullName`*** set accessor. **line 3**

In above example we would get an infinite loop on **line 37** when setting the ***`fulllName`*** property via ***`set`*** accessor.

>**REASON** :  If a property is **Unavailable on Object**, then it is searched in **Prototype Chain**.
   when we initialize ***`me`***, inside the constructor ***`firstName`*** is absent at time of **Assignment** therefore **Prototype Chain** is seached and there we find the ***`firstName`*** ***`set`*** accessor which in it's block has ***`this.firstName = firstName`***.
   when it is executed we arrive at a similar point where in ***`this`***, ***`firstName`*** is absent therefore we go into ***`this`*** prototype which is refers back to same ***__proto__*** which we initially looked into and searching starts again we don't find the property which starts searching again and so on.....

So we do following changes
***`this._firstName = firstName`***  line 3, 20   [**CODE**](https://codesandbox.io/s/lively-leaf-6fs97g?file=/src/OOP/Accessor_properties/example2.js)

This is a convention where we change prepend ***`_`*** before property name ***`_firstName`*** which we keep inside the object, But using **Setter's** name as ***`firstName`*** we make it look like as if we are still access the ***`firstName`*** property.

We also remove conflict this way since data property is ***`_firstName`*** and accessor is ***`firstName`***.
