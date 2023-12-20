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

## **Dynamic import and code splitting**

We may not need all scripts initially some might only be required conditionally but when the script executes all modules in ***`<head>`*** will be fetched.

The way we are importing modules till now is called static imports since all of them are statically imported at runtime. If there are a lot of modules inside of project then fetching them would require a lot off network requests and there would be a lot off dead time where browser would
just be waiting for the responses, loading the incoming scripts into the browse.

In a simple setup that may not be a problem but in large and complex projects that would be a lot of wasted CPU time therefore we deploy the dynamic import technique.

![[dynamic_import_1.png]]

***`import()`*** passing in the file name which we want to import and this function returns a promise and fulfillment value of this promise is an object which has all imports from the file. Then we can inside the then method's callback access them.

Using ***`import()`*** these modules will only be fetched only when the import is called, reducing the total no. of requests at the initially.
