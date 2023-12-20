# **JS Modules**

In order to keep ***`head`*** tag from getting unfeasibly large we can use JS Modules.

Modules are reusable piece of code that encapsulates the implementation details
usually a standalone file but doesn't have to be. We can export data from modules which can is stored as a value (expression), the code we export from a module is referred to as public API.

We try to encapsulate code inside of the expression we export abstracting all the low level details and only providing a high level functionality.

![[modules_3.png]]

We consume these public APIs by ***`import`*** them into other modules.

If we import data from another module into a module these imports are called import dependencies. They are dependencies as our code refers and requires them to run properly.

![[modules_2.png]]

We have to provide an entry point which is generally is main.js or index.js and on the script tag we have to add an attribute ***`type="module"`*** to indicate to the browser that files referenced inside this script are modules.

![[modules_1.png]]

We can add ***`export`*** keyword which signals this export is locked and is not globally available but only to the files which require it. Exporting this value should make it available outside this file.

By globally available we it is available on global Object which in browser in ***`window`*** object.

We can also **.mjs** which indicates module as an ES Module, there are other formats as well **.cjs** for commonjs.

There is no need to use the ***`defer`*** attribute ***`script`*** when loading a module script; modules are deferred automatically.

## **Code Execution inside modules**

When a module is imported the code is executed for the first time when script is read even if we use multiple imports from this module the code would never execute again.

In case of static imports this happens in first loading of script. While in dynamic imports it happens when the script is loaded dynamically and that too for the first time when script loads.

## **Module Scope and *`globalThis`***

Unlike scripts which are globally accessible, modules have module scope and values defined inside file is only scoped to the file therefore we can't add data to so called global object and modules run in ***`"use strict"`*** therefore ***`this`*** is undefined.

We can use ***`globalThis`*** which points to global object and it works in both node and browser.

We can access window via ***`window`*** and set values on global object but it will only be executed once we import the module therefore we might need to place the assignment carefully so as to not retrieve data before assignment.

> **NOTE** : Use ***`export`*** and ***`import`*** in modules to share data everywhere else and don't set it on global Object then access it.

## **Top Level *`await`***

when using modules instead of scripts we can use ***`await`*** at top level meaning we don't have to wrap an ***`await`*** in an async function. We can use it directly on top level.

If we ***`await`*** an expression at top level then script execution gets blocked till the promise is resolved.

> **NOTE** : If we use await in a module that exports the awaited value, any module that imports from it will have it's execution blocked as well

