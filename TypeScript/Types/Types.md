# **Types**

## **Introduction**

Providing or defining type to a **variable** is called **type annotation**. We can't change ***`type`*** once it is assigned.

> **NOTE** : we read ***typeErrors*** from **right to left** example :- type ***`number`*** is not assignable to type ***`boolean`***.

![[types_example1.png]]

A ***`type`*** is a definition assigned to a **variable** that defines the things we can do and what you can't with **that kind** of a variable, that means which **methods** and **behaviours** are **accessible** on that type of data.

![[all_types.png]]

## ***`any`***

Can be of literally any **type** from above shown diagram. This can be considered as default type in JavaScript. We use TypeScript to avoid ***`any`*** type and be precise with our **types**.

***`any`*** can **reassigned** to any other type **without any restriction**.

It is used as a last resort, when we don't know the **type** of incoming data.

Compiler option is linked to ***`any`***, ***`noImplicitAny`*** which throw error if we have annotated ***`any`*** type to  a value.

> **NOTE** : Trying to annotate type **after declaring** the variable results in **error**/**awkward behaviour**.

## ***`unknown`***

It is similar to ***`any`*** in the sense that we don't have **exact type** of **data** stored in the variable.
It is better than ***`any`*** as in ***`any`*** **TypeScript** stops caring about the **type** but in ***`unknown`*** we are implying that the value is **unknown** as of now but in future it **can be available**.

TypeScript will throw an **error** till type is defined a **bit precisely** than ***`unknown`*** this way we can initially expect an ***`unknown`*** type but then **narrow** it down for operating on it.

![[unknown_example1.png]]

TypeScript **forces** us to check what **type** of data is in variable which has been annotated ***`unknown`*** and **handle it accordingly** but ***`any`*** **bypasses** all type checking.

## ***`boolean`***

Only ***`Boolean`*** values can be stored in the variable. Values can be ***`true || false`*** or be the **result** of an **expression** which **returns** a Boolean value.

type ***`null`*** or ***`undefined`*** are not considered falsy values hence can't be assigned.

## **`number`**

**Expressions** which result in a ***`number`*** can be assigned.

## **`bigint`**

***`bigint`*** can be declared in 2 ways :-

1. Via constructor

2. adding ***`n`*** suffix. but target has to be at least ES2020.

Need for ***`bigint`*** is in JavaScript we can only represent **whole numbers** till **2^53** and operating on numbers larger than that becomes **unsafe**.

> **NOTE** : bigints can't have decimals and builtin Math constructor can't be used on them.

## **Type Inference**

TypeScript automatically tries to **extract** the **type** of value at **assignment**.

example :-  ***`const number = 85`*** since ***`const`*** doesn't change, **type** is **85 number**. similar for strings
***`let number = 85`*** is set to number only and not 85 since let declaration can change values.

**Simple** type annotations should be inferred by TS since explicit declaration makes them redundant.
Only explicitly add types when needed.

## ***`Object`***

It contains of **object literal** syntax and **property name** with their respective type is declared, then we describe the **structure** of object. The object has to **follow** the **defined structure** and if properties are **missing** then TS will throw an **error** saying object needs all property names and should match their defined types.

![[object_example1.png]]

For optional properties add ***`?`*** prefix before semi-colon. ***`prop?: string`***

## **Type Aliasing**

![[typeAlias_example1.png]]

We can **define** types **inline** with object but we can't reuse the type definition elsewhere without typing it again. Therefore we can store types using ***`type`*** keyword, then we can alias our structure into a type which we can name and use elsewhere. we can assign **alias** by simple annotation.

> **NOTE** : it can be considered a type expression

## **Union Types**

![[union_example1.png]]

**Object**
Multiple type **aliases**  can be unionized by piping these **aliases** and then we can use **any** of the types or **combination of properties** defined in their aliases.

> **Note** :  All properties of **at least 1** type must be **present**  It must **incorporate complete type** of any 1 types which were **unionized**.

**Primitive**
With primitives it acts as **Logical OR** but for types.
