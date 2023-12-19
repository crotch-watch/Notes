
# **Why Modules ?**

## **Code Splitting**

If we keep all code in a single file it gets massive & unmaintainable after a while therefore splitting our code into smaller chunks is a better option.

We add files via script tags and in this approach we have to make sure the order in which script tags are placed is such that dependencies are placed before wherever they are required.

![[code_splittng1.png]]

If scripts are are haphazardly placed then we might not have the required dependency for currently executing scripts.

If we try to access the code which is in a script which has not been loaded yet then there would be reference errors.

![[code_splittng2.png]]

If **classes.js** files requires method then there would be a conflict since methods would not have been loaded when classes.js is executing.

So we at all times would have to keep in mind the order of script tags and our header tag where we add scripts would get massive quickly and not feasible to maintain.

> **NOTE** : When we use scripts tags then the code is global scoped.

In this approach, one problem of large files was solved but another problem of header getting bigger gets introduced.

![[code_splittng3.png]]
