# **How Web Works**

When **browser(client)** needs data from **server** it sends a **request** to the server and server responds, this is known as **request response model** or **client server architecture**.

Every URL has **3 constituents**  :-

1. **http/https** :- Which is the protocol. Then we have the domain name finally the resource we want to access
2. **IP address** :- It is the **real identifier** of website **not domain name**, first **URL** is sent to the **DNS server** to **retrieve** its **IP address** this process is called **DNS Lookup**. DNS server has the all **IPs indexed**. It **returns IP address** for the site we wish to access, then it is sent back to the browser.
3. Then **TCP/IP socket connection** is established which is a **communication protocol** subsequently client sends an **HTTP request** to the server.

Format of an **HTTP request** :-
    1. **Start line** :-  HTTP method + request target(resource) + HTTP protocol version
    2. . **HTTP request headers** :- These are fields which describe the request.
    3. **Request body** :- Which is the data we send to the server.

![[BTS_web.png]]

Server processes the request and sends a **response** which is an **HTTP response** which also has a format :-

Format of an **HTTP response** :-
    1. **Start line** :- HTTP version + status code + status message
    2. **HTTP response headers** :- containing information about the response.
    3. **Response body** :- contains data we requested from the server.

## **TCP - Transmission Control Protocol**

It divides the **request/response** into smaller **chunks** which are called **packets** because sending it as a single chunk is **impractical** as there is a severe traffic and once the data is received on the other end **it puts the request together**.

## **IP - Internet Protocol**

It controls the **routing of packets** and makes sure they reach their desired address. Request/response packets are sent via **different routes**.
