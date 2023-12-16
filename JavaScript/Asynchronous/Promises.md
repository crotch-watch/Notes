## **Asynchronous Introduction**

JS is single threaded meaning it can't simultaneously execute multiple instructions, until one line has executed superseding instructions await it's completion, it is blocking the second instruction.
Synchronous code means code will execute line by line or sequentially.

![[async_1.png]]

Certain operations take longer to finished execution like timers and HTTP requests, these take an eternity and can block script execution for an unknown period of time. So in order to counter this JS offloads these tasks to the browser meanwhile synchronous tasks are executed in the thread and browser handles these tasks in background and when synchronous tasks are done potentially blocking code executes.

![[async_2.png]]

> **NOTE** : Asynchronous code is executed after all synchronous code has finished execution. It is non-blocking as it is offloaded and following synchronous code starts executing.

![[async_3.png]]

Example shows ***addEventListener*** itself does not turn the code asynchronous,  ***img.src = "dog.jpg"***  is loading the image in the background and this task is asynchronous hence it is deferred into the future by JS. 

![[async_4.png]]

## **API**

![[async_5.png]]
## **How Web Works**

When browser(client) needs data from another server it sends a request to the server and server responds, this is known as request response model or client server architecture.

Every URL has 3 constituents ***http/https*** which is the protocol. Then we have the domain name finally the resource we want to access

IP address is identifier of website not domain name, firstly URL is sent to the DNS server to retrieve its IP address this process is called DNS Lookup. DNS server contains the all names and it returns IP address which is sent back to the browser.

Then TCP/IP socket connection is established which is a communication protocol subsequently client sends an HTTP request to the server, format of HTTP request :-

1. Start line
2. HTTP request headers are fields which describe the request.
3. Request body which is the data we send to the server.
