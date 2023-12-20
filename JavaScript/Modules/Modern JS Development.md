# **Modern JS development**

![[js-dev-1.png]]

## **Modules**

Rather than writing a single huge file we separate them into modules

## **Build process**

We are implementing simple build process of 2 phases

1. Bundling
2. Transpiling/polyfilling

### **Bundling**

Old browser don't support modules hence we bundle all modules in a single file, bundle also removes unused code and compresses code which improves performance, it improves performance as there is only one file fetched which in itself has minified and bundled code

### **Transpiling/Polyfilling**

We transform code to a target ES version which is commonly ES5 since our site may ran on older browsers and they don't have access to newer js features.
