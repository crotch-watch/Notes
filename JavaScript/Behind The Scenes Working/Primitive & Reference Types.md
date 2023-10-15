# **Primitive & Reference Types**

![[variable_storage.png]]

Primitives are stored in execution contexts whereas reference types are stored in **heap memory**.

![[primitives_reference_mutation.png]]


From **variable name** a **unique ID** is created then a piece of **memory** is allocated with some  which has some **memory address**.

**identifier** doesn't stores value but in actual it stores the memory address. 

if copy first variable value into another only the **address** is copied.

if we change the value of first variable then the **value** at that **address** will not change but **piece of memory** is created and the original variable **points to the new address**. 

so when we say primitives are immutable that means the value that is stored at the memory address does not change when we operate on the variable simply a new memory with new value is created.

when we create a **reference type**, it is created inside **heap** and the variable does not directly store the **heap memory address** but the **value** is the **memory address** in heap which stores the object.

so when we copy the object we copy the value which is the address of object in heap. Hence when we mutate the object we dont actually mutate the value stored in the exe, context but the value in heap..

> **NOTE** : even the ***const*** variable can mutate the objects because the value in **execution context** never changes, what changes is the **value in heap**. 
