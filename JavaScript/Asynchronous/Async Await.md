# **Async Function**

We can make any function an async function by using the ***`async`*** keyword. The ***`await`*** keyword is permitted within the function body, enabling asynchronous, promise-based behavior to be written in a cleaner style and avoiding the need to explicitly configure promise chains.

![[async_func1.png]]

Each time when an async function is called, it returns a new ***`Promise`*** which will be resolved with the value returned by the async function.

![[async_func2.png]]

Async functions can contain zero or more ***`await`*** expressions.

Await expressions make promise-returning functions behave as though they're synchronous by suspending execution until the returned promise is fulfilled or rejected. The resolved value of the promise is treated as the return value of the await expression.

The body of an async function can be thought of as being split by zero or more await expressions. Top-level code, up to and including the first await expression (if there is one), is run synchronously. In this way, an async function without an await expression will run synchronously. If there is an await expression inside the function body, however, the async function will always complete asynchronously.

![[async_func3.png]]

> **NOTE** :  We can handle errors in async function via the ***`try`***, ***`catch`***, ***`finally`*** blocks
