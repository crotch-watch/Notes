# **Browser Storage**

Server has server side database and there we store data which we want to persist and restrict it's access like sensitive data would be stored in server side database not in browser storage where it could be viewed and changed.

![[browser-storage-1.png]]

When we store data in browser storage user can access it in their browser. So it makes sense to store data which is scoped to the user there.

## **Storage Engines**

![[browser-storage-2.png]]

> **NOTE** : Cookies are attached to the header of the outgoing http requests and hence can be sent to the server
