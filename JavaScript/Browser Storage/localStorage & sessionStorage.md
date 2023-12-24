# ***`localStorage` & `sessionStorage`***

When we do ***`localStorage.setItem('key', value)`*** both arguments are set is set using ***`.toString()`*** method so if we try to store an object then it will return ***`[object object]`***. we can only store data which can be converted to string, we can ***`JSON.stringify`*** the object since JSON itself is JavaScript object wrapped in a string.

![[localStorage-1.png]]

> **NOTE** : only JSON accepted values are reflect in string and all others are converted to null or in case of functions they are completely  removed.

***`sessionStorage`*** is similar to ***`localStorage`*** in terms of API but ***`sessionStorage`*** only stores data until our page is open, as soon as we close the page or browser window then the data is lost. However ***`sessionStorage`*** persists data after page refreshes.
