# **Introduction**

Let's make an ***`identity function`*** and type annotate it. Here **function return type** is inferred.

![[identity1.png]]
[**CODE**](https://codesandbox.io/p/sandbox/cranky-mayer-zsg686?file=%2Fsrc%2FGenerics%2FIdentity1.ts%3A4%2C1)

If we type annotate with ***`string`*** type we can **only pass** string arguments. But we want to pass whichever type of value and preserve it's type, so when we save value returned from function it's type should inferred correctly.

One way of doing it could be **creating multiple functions** , for example make another ***`function`*** whose parameters are of type ***`number`*** but has same structure.

![[identity2.png]]
[**CODE**](https://codesandbox.io/p/sandbox/cranky-mayer-zsg686?file=%2Fsrc%2FGenerics%2Fidentity2.ts%3A4%2C1)

As seen we could **create multiple** functions whose types are different but  structures are same and ideally we would want to **DRY** them up.

> **NOTE** : Here we can't create a union and annotate it to parameter.
> **REASON : 1** Our function return type will also be the union and not the exact type argument that we pass in to the function.
> **REASON : 2**  It is not possible to write union of all possible types.
> **REASON : 3**  We can't anticipate ahead of time what what of argument would be passed into the function.

![[identity3.png]]
[**CODE**](https://codesandbox.io/p/sandbox/cranky-mayer-zsg686?file=%2Fsrc%2FGenerics%2Fidentity3.ts%3A9%2C1)

we can use ***`any`*** type, it would **accept all** argument types but value would also be of ***`any`*** type.

Our Objectives are :-

1. Create an ***`identity function`*** which returns the argument passed in it.
2. Preserve the type of argument.
3. Writing one function and not multiple with same structure but different type annotations, essentially **DRY** it up.
