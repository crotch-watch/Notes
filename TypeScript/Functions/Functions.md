# **Functions**

### **Parameter Type Annotations**

When you declare a ***`function`***, you can add type annotations after ***`each parameter`*** to declare what types of parameters the function accepts. Parameter type annotations go after the parameter name:

> **NOTE** : TS errors when provided arguments differ from required arguments as in how many are provided.

![[functions1.png]]

In order to add **optional parameter** we append ***`?`*** after declare the **parameter's name**.
### **Return Type Annotations**

You can also add return type annotations. Return type annotations appear after the parameter list:
***`(saluation: string, name: string): string`***

Much like variable type annotations, you **usually** don’t need a return type annotation because TypeScript will **infer** the function’s return type based on its ***`return`*** statements.

![[optional_params1.png]]

> NOTE: in above example wherever we are annotating types we can also annotate with type aliases both **Parameters** and **Return Type**
