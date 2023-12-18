
# **Promise**

Promise is an **object** which will have result of **eventual completion** of an **asynchronous operation**.

## **Promise Life Cycle**

It has **2 states** which are **time sensitive** meaning they change at some interval.

1. **Pending** - when the asynchronous task is still being performed behind the scenes and promise will remain in this state.
2. **Settled** - when the task is finished then it shifts to settled. Settled Promise has 2 further types
    1. **Fulfilled** - It indicates the task has **successfully finished** it's execution also provides a **result**
    2. **Rejected** - It indicates the task has **errored out**.

![[Promises_1.png]]

> **NOTE** : once the promise has been settled it's state **never changes** it either stays fulfilled or reject throughout it's existence.

### **Consuming Promises**

3 methods are available to us for consuming a promise :-

> **NOTE** : In all 3 methods we pass a **callback** which gets executed when each method's **specified criteria** is met.

first is ***then*** it accepts 2 callbacks, ***onFulfilled*** - It is fired if promise gets fulfilled then we can retrieve data by accepting an argument inside the callback which is the result of the task. ***onRejected*** - It is fired when the promise gets rejected and we can accept and an argument which provides the **reason** of rejection.

![[then_1.png]]

> **NOTE** : Here log represents ***onFulfilled*** and error represents ***onRejected***.

Then method always returns a promise and the value which is return from callback becomes fulfillment value of the returned promise. We can return a promise from inside the promise and chain them.  

second is ***catch*** - Instead of providing each then with their own onReject callback we can use ***catch*** method which catches any errors which fall to the bottom and handle them with provided callback. It also uses ***onRejected*** callback format

![[catch_1.png]]

lastly ***finally*** - Above mentioned methods only run conditionally but finally executes after either of two are run and it always runs at the end.

![[finally_1.png]]

## **Promise Combinators**

### ***`Prmoise.all`***

![[combinators_1.png]]

It accepts an array of promises and runs them simultaneously and returns a promise whose fulfillment value would be an array with fulfillment values of promises passed into ***`Promise.all`***.

> **NOTE** :  It will short circuit as soon as any promise rejects and it errors out.

### ***`Promise.race`***

![[combinators_2.png]]

It accepts an array of promises and runs them simultaneously and returns a promise whose fulfillment value is earliest settled promise even if it is rejected.

### ***`Promise.allSettled`***

Same as ***`Promise.all`*** but does not short circuits and returns result of all promises.

### ***`Promise.any`***

It accepts an array of promises and runs them simultaneously and returns the first value that is fulfilled ignoring all rejections.
