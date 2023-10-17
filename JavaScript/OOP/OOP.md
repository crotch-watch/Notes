# **Object Oriented Programming**

## **Introduction**

![[OOP_intro1.png]]

**Object oriented programming** helps to organize code, otherwise **spaghetti code** is hard to maintain in larger projects and adding additional functionality is cumbersome.

There are other programming paradigms as well like **Functional** and **Procedural**.
What we were doing prior to this was using **object literals** but in OOP we need to make objects **programmatically**.

## **Class**

![[classes_intro.png]]

***`Class`*** can be considered as a **template** from which object can be created.

This **template class** is an abstract concept from which objects can be built, which is a **description** of what should objects contain.

All objects created from a class are called **instances** of that class.

There are 4 fundamental principles to keep in mind when **designing/modelling** classes

1. **Abstraction**

2. **Encapsulation**

3. **Inheritance**

4. **Polymorphism**

## **Abstraction**

To hide details behind from user which grants us an **overview perspective/easily understandable usage** of inner workings.

**example** :- ***`addEventListener`*** is an abstraction where all lower level details have been extracted away from user and we only provide code for what we want to happen and don't **lower level details**.

![[abstraction_intro.png]]

## **Encapsulation**

Keeping **methods** and **properties** inside the ***`class`*** only accessible inside the ***`class`*** and not outside of it.

Some methods are available for outside code to interact with properties of an **object**  these are called **Public Interface**.

![[encapsulation_intro.png]]

This helps to prevent manuplation of data inside of the class from outside

> **NOTE** : Private properties and methods can be used for **internal interactions** of class and code that we doesn't belong outside the class line in above **example** we have ***`checkSPAM`*** method

## **Inheritance**

If we have class which are related to each other but are created as **separate entities** we might end up with a lot of **duplicate code**.

In above case we can have one ***`class`*** inherit another so they can **share logic** between each other **reducing redundancy**.

This creates a **hierarchical structure** in which **parent class** shares it's logic with it's lineage.

## **Polymorphism**

![[polymorphism_intro.png]]

In above **example** we have **different login methods** for **children classes** and we have **overridden** parent's login method.
