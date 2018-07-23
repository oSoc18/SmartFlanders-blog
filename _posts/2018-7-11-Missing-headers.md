---
layout: post
title: Problems with missing headers
---

## The problem
Even when cities do use linked open data, it's not always completely the way it should be.
For example, one of the cities that publishes open data forgot to add Cross-Origin-Resource-Sharing (CORS) headers to its website, 
making the data inaccessible from other browsers when using javascript.

### What are CORS headers
[CORS headers](https://developer.mozilla.org/en-US/docs/Web/HTTP/Server-Side_Access_Control) are HTTP headers which allow servers to specify which clients can perform which actions on which resources. 
Web browsers permit scripts on a web page to access data on another web page, 
but only if both web pages have the same origin. The origin is the domain name, for example stad.gent.
If there are no CORS headers specified and web pages don't have the same origin, 
any interaction to resources on another domain won't be allowed.

![CORS](https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS)

All the responses from a server must return an `Access-Control-Allow-Origin header` to allow client-side applications to interact with the data on this server.
This header defines which domains are allowed to interact with the data and are usually set to "*" for open data. 
This means that every domain may interact with the data.
The server then returns an `Allow-Control-Allow-Methods header` to control which actions the client can take. 
Without these headers, or for any action which is not defined in these headers, requests will be blocked for security reasons.
![CORS](https://crazygui.files.wordpress.com/2012/08/cors.png)

In case of linked data, the data can't be loaded from the server and thus can't be used by any application without these headers. 
For example the application that our befriended team OASIS is making should be able to easily use
 the linked open data provided by a city and display it on their map.
However, due to the missing CORS headers they are not allowed to access the data and can't do anything with it.

### Solution
The solution to this problem is easy: the CORS headers should be added to the linked open data and set correctly.

Request Example
```
OPTIONS /
Host: viaf.org 
Origin: http://www.librarywebchic.net/ 
The server will respond with a set of headers that tell the client which operations it is allowed to perform on that resource.
```

Response Example
```
Access-Control-Allow-Origin: *
Access-Control-Allow-Methods: GET
```
