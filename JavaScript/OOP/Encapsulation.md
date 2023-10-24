# **Encapsulation**

 Keeping properties and methods **private** inside of the ***`class`*** inaccessible outside the ***`class`*** and rest of the methods are **exposed** as a **public interface**.

## **Why Encapsulate**

1. To prevent **code outside** of the class to change data **inside of the class**.
2. Since data is **private** and only available for private use we can change **inside code** knowing that outside code will be **unaffected**.

## **Example**

![[Encapsution_1.png]]
[**CODE**](https://codesandbox.io/s/lively-leaf-6fs97g?file=/src/OOP/Encapsulation/example1.js)

> **NOTE** :  Developers use a convention to put **underscore** before the property name to **indicate** it is supposed to be a **private property**. ***`this._movements`*** but this does not make field private.

Following the convention we can provide **public interface** for movements but **restrict mutations**. line 33.

## **Class Fields**

1. Public Methods/Properties
2. Private Method/Properties

There are ***`Static`*** version of above mentioned properties.  

**Fields** have to be **declared**  in ***`class`*** body's top level.

![[Encapsution_2.png]]
[**CODE**](https://codesandbox.io/s/lively-leaf-6fs97g?file=/src/OOP/Encapsulation/example2.js)

> **NOTE** : ***`get`*** accessor's name can't be same private field's name, unlike shown in [Example](#example).

**Hash names** can't be accessed outside of the ***`class`*** but can be seen via **developer tools**.

**Fields** behave like normal variables inside class can be **reassigned** like ***`let`*** and can be accessed via **scope chain** but only inside the ***`class`***.

Private methods are not added to **prototype** they are kept in JavaScript's **internal property** ***`[[PrivateMethods]]`***. Private methods are meant to only be accessed in the class and not outside.
