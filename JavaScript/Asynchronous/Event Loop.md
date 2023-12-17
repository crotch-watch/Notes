# **Event Loop**

It **orchestrates** which operation would be **pushed** onto the **execution stack** once it has finished execution.

![[event_loop1.png]]

***el.src = "dog.jpg"*** essentially means to load the image from the source which could take a lot of **time** as the image file could be **massive**, this is handed off to **web APIs environment** and next in ***el.addEventListener*** we attach a **listener** onto the **image load event** and when the event would be **emitted** then this **callback** would run

> **NOTE** :  The callback is **registered** in the **web API environment**.

Now let's assume image has finished loading which **emits load event** and the event listener callback will be pushed on the **callback queue** then the event loop checks whether the **call stack** is **empty** and if it is then callback is pushed onto the call stack where it will execute.

When a **callback** is pushed from a **queue** and placed onto the **call stack** this process is called an **event loop tick**.

assuming the data has been fetched from the server and the **promise callback** will be pushed onto the **microtasks queue**. Callbacks passed in the Promise are considered **microtasks** and placed in the **microtasks queue**, microtasks queue takes **priority** over the **callback queue** and  after an **event loop tick** if microtasks queue isn't empty then all microtasks are **sequentially pushed** and **executed** and only then the callbacks are attended.

> **NOTE** : If **microtasks spawn** other microtasks this can **starve** the callback queue.
