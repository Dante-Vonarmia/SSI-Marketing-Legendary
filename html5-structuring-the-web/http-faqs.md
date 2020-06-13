---
description: Background Knowledge
---

# HTTP FAQs

### 1. What is HTTP?

* HTTP stands for Hypertext Transfer Protocol. 
* It is a set of rules for transferring of data on WWW \(World Wide Web\).

### 2. What are the basic Features of HTTP?

The basic features of HTTP are as follows:

* HTTP is a request and response protocol.
* HTTP is a media independent protocol.
* HTTP is a stateless protocol.

### 3. What are request methods in HTTP?

Following are the request methods:

```text
GET
```

It is used to send data in url.

```text
POST
```

It is used to send data to the server.

```text
PUT
```

It is used to send entire updated data to the server.

```text
DELETE  
```

Delete method sends a request to the server to perform delete operation.

```text
*HEAD*
```

It only transfers status line and header section as a request.

```text
*CONNECT* 
```

It is used to establish connection to the server.

```text
*OPTIONS* 
```

Option method describes communication options for target resource.

```text
*TRACE* 
```

It performs message loop-back test along the path to the target resource.

### 4. What are the differences between GET and POST method?

Following are the differences between GET and POST method:

| Get | Post |
| :--- | :--- |
| It is cached. | It cannot be cached. |
| It receives data using url in the browser. | It does not send data into the url. |
| It can receive limited amount of data to the server. | We can send data in bulk to the server. |

### 5. What is status code in HTTP?

It is a Standard response code given by web server on Internet.  
It helps to identify the cause of problem when web page or other resource does not load properly.

There are two major group of HTTP [status code](https://www.restapitutorial.com/httpstatuscodes.html) error exist:

* 4xx Client Error
* 5xx Server Error

### _6. What are the header fields in HTTP?_

HTTP headers fields allow the client and server to pass information with the request and response message.

Following are the header fields in HTTP:

#### General header

It applies for both request and response message.

#### Request header

It contains information for the request message.

#### Response header

It is used to contain response header information sent by the web server.

#### Entity header

It is used to contain more information about the body of the entity.

### _7. What is URI?_

URI \(Uniform Resource Identifier\) is used to define the identity of something on the web. It can represent a piece of a url.

### _8. What are_ [_Idempotent_](https://sofish.github.io/restcookbook/http%20methods/idempotency/) _methods?_

In idempotent methods, for the multiple requests, we get exact same result.  
It would no matter if the request is called one or ten times, the result should be same.

### _9. What is secure HTTP?_

* The secure HTTP is secure version of HTTP. 
* In this protocol, data transfer over the World Wide Web is secure and encrypted. 
* It is used to execute highly confidential online transaction like financial transactions.

### _10. What are the benefits of HTTPS certificate?_

The major benefits of HTTPS certificate are:

* Customer information like credit card number and ATM pin is encrypted and cannot be easily track.  
* Customers trust and prefer to purchase from the sites that use HTTPS protocol.  
* This protocol shows authenticate register domain as secure connection.  

### _11. What is cURL in HTTP?_

cURL is command line tool. It is available on all major operating systems.

### 12. What is [REST](https://sofish.github.io/restcookbook/)?

REST stands for Representational State Transfer. It is a set of constraints that ensure a scalable, fault-tolerant and easily adaptable system. It relies on a stateless, client server and cacheable communications protocol.

Good REST APIs:

* Result paginate, filtering, sorting & searching
* explicitly design in other commercially-significant API-specific features
* are well-documented and reliable
* track version
* log activity
* express URLs with nouns rather than verbs
* use HTTP verbs as Fielding originally defined
* make expressive use of HTTP Status Codes
* handle errors carefully and explicitly
* choose wisely between XML \(increasingly rare\), JSON, and HATEOAS \(rapidly growing\)
* Limiting which fields are returned by the API
* support X-HTTP-METHOD-Override to accommodate picky proxies

