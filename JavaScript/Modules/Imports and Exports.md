# ***`export` and  `import`***

We can add ***`export`*** keyword which signals this ***`export`*** is locked and is not globally available but only to the files which require it, by globally available means it is avaible on global object which in browser in window object.

![[export-1.png]]

It would import when it needs it at runtime when the module runs. Also we would have to specify  ***`type="module"`*** on script  otherwise we receive an error.

Exports which are being exported from the module are named exports and in the module we import them we must use the names as they were in the module.

## ***`as` keyword***

![[as-1.png]]

***`as`*** keyword is used to alias the import/export names and then we only have access to the alias name not the real name of the import/export.

## ***`*`** export all

We can bundle all exports from a module into a single value then import one object which contains all exports as values and methods on that object.

![[import-2.png]]

## **Default Exports**

One module can have only 1 default exports as it would not make sense to have multiple default exports.

Unlike named exports, default export doesn't need to have a name as there can be many named export therefore while importing we will have to specify which value we want from a module but as there is only one default export therefore only default export will be imported when using appropriate syntax.

![[default-export-1.png]]
