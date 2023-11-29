# **Functions**

### **Parameter Type Annotations**

When you declare a ***`function`***, you can add type annotations after ***`each parameter`*** to declare what types of parameters the function accepts. Parameter type annotations go after the parameter name:

> **NOTE** : TS errors when provided arguments differ from required arguments as in how many are provided.

![[functions1.png]]

In order to add **optional parameter** we append ***`?`*** after declare the **parameter's name**.

![[optional_params1.png]]

### **Return Type Annotations**

You can also add return type annotations. Return type annotations appear after the parameter list:
***`(saluation: string, name: string): string`***

Much like variable type annotations, you **usually** don’t need a return type annotation because TypeScript will **infer** the function’s return type based on its ***`return`*** statements.

![[optional_params1.png]]

> NOTE: in above example wherever we are annotating types we can also annotate with type aliases both **Parameters** and **Return Type**

## **Function Type Expressions**

The simplest way to describe a function is with a **function type expression**. These types are **syntactically** similar to arrow functions:

***`type GreetFunction = (greet: string) => void;`***

The syntax ***`(greet: string) => void`*** means a function with one parameter, named ***`greet`***, of type ***`string`***, that doesn’t have a return value. Just like with function declarations

We can type annotate any variable where function is being stored as a value whether it is **function  expression** or **arrow function**.

![[function_type_expression1.png]]

## Call Signatures

In JavaScript, functions can have **properties** in addition to being **callable**. However, the function type expression syntax **doesn’t allow** for **declaring properties**. If we want to describe something callable with properties, we can write a **call signature** in an object type:

> **NOTE** : Here we are annotating ***`function`*** as  a callable object.

![[call_signature1.png]]
