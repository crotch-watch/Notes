# **Cookies**

![[cookie-1.png]]

***`document.cookie`*** gives access to all cookies, setting ***`document.cookie = "age=12"`*** will add to the cookies not override all cookies with ***`"age=12"`***, only replaces cookie with the same key

Cookies are only available if the webpage is being served by a web server. File protocol will not grant access to cookie storage.

> **NOTE** : Cookies are sent with http request but server should doing something with them otherwise it won't do anything.

Similar to ***`localStorage`*** & ***`sessionStorages`*** we can only add data to cookies which is correctly converted to string. therefore we would have to ***`JSON.stringify()`*** non-primitives.

We don't have elegant retrieval API for cookies, we just retrieve the string separated with semicolon ***`;`*** and then try to extract relevant data with operating on string.

![[cookie-2.png]]

Cookies expire automatically after session ends and if we want cookies to persist then we can set an expiration on cookie using 2 flags ***`expires`***(date) and ***`max-age`***(seconds), then it will persist till it expires.

![[cookie-3.png]]

> **NOTE** : flags like max-age are not part of the cookie value
