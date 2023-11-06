# **Types**

## **Introduction**

Providing or defining type to a **variable** is called **type annotation**. We can't change ***`type`*** once it is assigned.

> **NOTE** : we read ***typeErrors*** from **right to left** example :- type ***`number`*** is not assignable to type ***`boolean`***.

![[types_example1.png]]

A ***`type`*** is a definition assigned to a **variable** that defines the things we can do and what you can't with **that kind** of a variable, that means which **methods** and **behaviours** are **accessible** on that type of data.

Types have no runtime elements attached to them when they are transpiled to JS. Therefore if we can offload our logic to TS rather than JS it could be beneficial since there would be no code that would require it to be run, it would only be present at development time.

![[all_types.png]]

## ***`any`***

- Can be of literally any **type** from above shown diagram. This can be considered as default type in JavaScript. We use TypeScript to avoid ***`any`*** type and be precise with our **types**.
- ***`any`*** can **reassigned** to any other type **without any restriction**.
- It is used as a last resort, when we don't know the **type** of incoming data.
- Compiler option is linked to ***`any`***, ***`noImplicitAny`*** which throw error if we have annotated ***`any`*** type to  a value.

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

2. Adding ***`n`*** suffix. but target has to be at least ES2020.

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

## **Type Alias**

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

## **Intersection Types**

These are complete **exhaustive combination** of all **unique properties** and **common properties** of intersected types.

> **NOTE** : Unlike **union types** these require us to have all unique properties to be explicitly mentioned. Intersection types results in a ***`never`*** when intersected types are primitives.

## **Index Signature**

![[index_signatures1.png]]

Sometimes you don’t know all the names of a type’s properties ahead of time, but you do know the shape of the values.

In those cases you can use an index signature to describe the types of possible values.

Only some types are allowed for index signature properties: ***`string`***, ***`number`***, ***`symbol`***, template string patterns, and union types consisting only of these.

While string index signatures are a powerful way to describe the **dictionary** pattern, they also enforce that all properties match their return type. This is because a string index declares that ***`obj.property`*** is also available as ***`obj["property"]`***. In the following example, ***`status`***  type does not match the string index’s type, and the type checker gives an error:

![[index_signatures2.png]]

However, properties of different types are acceptable if the index signature is a union of the property types:

![[index_signatures3.png]]

## **Array**

![[array1.png]]

> **NOTE** : As a rule of thumb try to keep array of only one type and not a union because then we would have to test whether element inside is of which type.

## **Tupple**

These are heterogeneous arrays which have a defined structure.

![[tupple1.png]]

## **Readonly**

Constructs a type with all properties of **Type** set to ***`readonly`***, meaning the properties of the constructed type cannot be reassigned.

![[readonly1.png]]

> **Note** :  Example given in **Tupple** can still can **mutate** the array, by making it ***`readonly`***  array we can ensure the length of the array since it can't be changed.

## ***`null`*  and   *`undefined`***

- ***`undefined`*** in JS refers to a value that has not been defined as of yet.
- ***`null`*** expresses a lack of identification, indicating that a variable points to no object. In APIs, ***`null`*** is often retrieved in a place where an object can be expected but no object is relevant.

### **Non-null Assertion Operator (Postfix *`!`*)**

TypeScript also has a special syntax for removing ***`null`*** and ***`undefined`*** from a type without doing any **explicit checking**. Writing ***`!`*** after any expression is effectively a **type assertion** that the value isn’t ***`null`*** or ***`undefined`***:

![[null_undefined1.png]]

## ***`void`* and *`never`***

***`void`*** represents the **return value** of functions which **don’t return** a value. It’s the **inferred type** any time a function doesn’t have any ***`return`*** statements, or doesn’t return any **explicit value** from those return statements.

> **NOTE** : only value that can assigned to type ***`void`*** is ***`undefined`***.

The ***`never`*** type represents values which are **never observed**. In a **return type**, this means that the function throws an **exception** or **terminates execution** of the program.

> **NOTE** : **Code** below the function whose return type is ***`never`*** will be marked as unreachable code, since it will **never** complete it's execution.

![[void_never1.png]]

> **NOTE** : ***`never`*** also appears when TypeScript determines there’s nothing left in a union.

## **Recursive Type**

Here we have a nested data which has same recurring structure which is a nested ***`number[]`***.

![[recursive1.png]]

If we create an alias which stores this **nested *`number[]`***, we would have to exactly the nesting level and what type of values should the nested array have.

For first level, we want an array which contains ***`number`*** only.

![[recursive2.png]]

For second level, we want an array which contains ***`number`*** or ***`numbers[]`***.

![[recursive3.png]]

> **NOTE** : Here we can't put ***`number[][]`*** since it would indicate an array of array which has number ***`[[1, 2]]`*** and if we **add numbers** to **upper array** it would show a **type error** since it is expecting **an array of numbers** in upper array. We also can't remove the grouping ***`()`*** of type, if we do ***`type Nested = number | number[][]`*** then we are telling TS that we want either a ***`number`*** or ***`number[][]`*** since union ***`|`*** would be place after ***`number`*** but if we group the ***`(number | number[])[]`*** then it would read as array of ***`number`*** or array of ***`number[]`***.

For third level, we want an array which contains the array at second level ***`(number | number[])[]`*** or ***`number`***.

![[recursive4.png]]

We just can't simply **nest** the array ***`[7, 8, 9]`*** if our type is ***`(number | number[])[]`*** as that **level of nesting** is absent in our type and it would throw type error.

So we can conclude for every level of nesting we specifically have to mention the nesting on our type as well which gets cumbersome to write and difficult to understand for others, therefore we can simplify this with **recursive type syntax**.

![[recursive5.png]]

***`let nested: Nested = 1`*** at first it either be a number which satisfies the union.

***`let nested: Nested = [1]`*** if it not ***`number`*** then it has to be an **array**, **array of** ***`Nested`***, ***`Nested[]`*** which contains ***`number`*** hence it **satisfied** the union type for first array.

TO BE COMPLETED.....

![[recursive6.png]]

## **Type Assertions (Casting)**

Sometimes you will have information about the type of a value that TypeScript can’t know about.

For example, if you’re using ***`document.getElementById`***, TypeScript only knows that this will return ***some*** kind of ***`HTMLElement`***, but you might know that your page will always have an ***`HTMLCanvasElement`*** with a given ID.

In this situation, you can use a ***type assertion** to specify a more specific type:
***`const myCanvas = document.getElementById("main_canvas") as HTMLCanvasElement`***

Sometimes this rule can be too conservative and will disallow more complex coercions that might be valid. If this happens, you can use two assertions, first to ***`any`*** (or ***`unknown`*** ), then to the desired type:
***`const a = expression as unknown as T`***

## **Literal Types**

These are the type which are the literally a string or a number. These restrict our options to  assign a value into a variable to only defined string | number | boolean.

We define these types similar to the other types we just annotate the value instead of the type.
***`type LiteralsUnion = 10 | 20 | "Hello" | false`***
***`let correct: LiteralsUnion = 10`***
***`let wrong: LiteralsUnion = 12`***  any other values will throw an error.

## **Function Type**

We can use the  ***`Function`*** i.e. ***`type func = Function`*** but that does not provide any specifics of the functions whether it be the parameters or return type. Therefore we can annotate the signature for a function.

***`type func = (arg:1 string, arg2: number) => string`***

### **Optional Parameters**

If we do not require ***`arg2`*** to be explicitly available to us in order to execute the function then we can add it as an optional parameter, otherwise if we just dont pass the argument then we will get an error.

***`type func = (arg1: string, arg2?: number) => string`*** by prefixing the type annotating of ***`arg2`*** with ***`?`*** we make it an optional parameter.
