# REST APIs

REST API - Representational State Transfer and Application Programming Interface

Representational State Transfer or REST refers to a group of software architecture design constraints that bring about efficient, reliable, and scalable systems. 

WEbpages contain:

- one HTML
- CSS - describes how HTML elements are to be displayed on screen, paper, or in other
  media. He saves a lot of work. It can control the layout of multiple web pages
  all at once
- JavaScript

When the visitor navigates from one view to another, the application sends a new
URI request for the web resource representing the next state of the application
which is transferred and used to **add, modify, replace, or delete** the previous data.

The key is this representational state is transferred as a **data object**, not the
entire new set of files. 

An API is a set of features and rules that exist inside a software program enabling
interaction between the software and other items, such as other software or hardware.
In the context of REST APIs, the API is the collection of tools used to access and
work with REST resources through your adverbs including **get, pull, put, and delete**.

You can think of the REST resource as a librarian and the API as the language used
to talk to them. 

## URL and URI

**URI or Universal Resource Identifier**, is described as a "compact sequence of
characters "that identifies an abstract or physical resource" that "provides a
simple and extensible means "for identifying a resource." 

The URI is the most generic method for naming and locating a web resource. 

**The URL, or Universal Resource Locator**, is a subset of the URI. The URL not only
identifies a resource, but also explains **how to access** that resource by providing
an explicit method like HTTP or FTP. 

**The URN, or Universal Resource Name**.

The classic explanation of the difference between a URN and a URL is to say the URN
is a unique name identifier, like the name of a person. There are many people named
Morten, but only one person name Morten Rand-Hendriksen. Refer to me by my full
name and anyone who knows me knows who you're talking about, even if I'm not there
and they don't know where I am at the moment. The URL provides my actual physical
location. So right now my URL is Earth, USA, California, Carpinteria, etc. 

![difference](https://i.stack.imgur.com/2iD7U.jpg)

### The six constraints of REST

- The client-server architecture
  This constraint ensures proper separation of concerns. The client manages user
  interface concerns, while the server manages data storage concerns. In return,
  we get a highly portable system where one REST service can serve many different
  clients and interfaces without knowing or caring what those interfaces look like
  or what they are doing. In short, we have a complete separation between the
  content and its presentation and interaction.

- The statelessness - безгражданство
  No client context or information, AKA state, can be stored on the server between
  requests. The client is responsible for keeping track of its own session state
  and all requests sent from a client must be self-contained and complete. 

- The cacheability
  Cacheing, as in storing responses for a set period of time, is an intricle part
  of web architecture and performance optimization. All REST responses must be
  clearly marked as cacheable or non-cacheable to ensure cacheing works as expected
  on the client end. This means cacheing responses that won't or are unlikely to
  change, cacheing rarely or periodically changed responses for reasonable periods
  of time, and blocking cacheing for constantly changing responses. 

- The layered system
  The system must be designed so the client can't know and doesn't care whether
  it's connected directly to the server or to an intermediary like a mirror or a
  CDN. This ensures scalability and also helps with security. 

- The code on demand
  Servers are allowed to transfer executable code in the form of client side JavaScript
  and compiled components to the client to extend and customize functionality. This
  is a less common use of rest.
  
- Uniform interface
  - Resource identification in request
  - Resource manipulation through representations
  - Self-descriptive messages
  - Hypermedia as the engine of application state

HTTP and REST API

Working with REST APIs, you'll most likely send your requests through HTTP. A large
percentage of REST APIs are available through the web using the HTTP protocol.
So although not all REST APIs use the HTTP protocol, the RESTful ones do. 

**HTTP, short for HyperText Transfer Protocol**, is the protocol your web browser
uses to access hypertext documents on the world wide web. That world wide web lives
on the internet alongside other services like SMTP for email, various instant
messaging services, video streaming, and so on. As you have learned, REST is a set
of six software architecture design constraints that produce a specific type of service.
There's nothing in that definition of REST that stipulates that service must run
on HTTP and therefore the web. REST and HTTP are not linked; they're just a convenient
pairing. When a REST service runs on the web over HTTP to give us access to a web
resource, we call it a **RESTful API**. In other words, if you send a request through
HTTP to a REST service that meets the six constraints, that service is a RESTful API.

Who or what interacts with REST APIs?

A client in this scenario is not the human interacting with the website or app,
but rather, that website or app itself. We are merely the operators of these REST
clients, and the clients consume the REST API by creating and sending requests,
and receiving and parsing responses. The REST API's job is to receive requests,
process data, and send responses. The key takeaway here is you, the human, do not
interact with the REST API directly. Communication with the REST API is handled by
the client, which can be anything, really.

## Request

The anatomy of a REST request:

- a method - is one of the standard HTTP operators, **get, post, put, patch, delete,**
  **options, and head**
- URI - points to the resource we want it to interact it

Whether all these listed methods work on the resource at the end of the provided
URI depends on the configuration of the REST API and the authorized capabilities
of the current user. 

So if we want a list of the most recent posts on a WordPress site, we send a GET
request to the resource URI for all posts, GET site.com/wp-json/wp/v2/posts. When
we submit a request, we can also send along metadata in the request header. This
data should include the content type to comply with the self-descriptive messages
constraints and can also contain a user agent string, accepted language string,
authentication, cache control and more.

If we want to send information to the REST API to create a new entry or update an
existing one, the request gets more complex because we have to send along the actual
data. Here, the data structure of the request needs to match the content type defined
in the request. So in this example, the content type is set to application/json,
meaning the data has to be marked up as JSON as well. To create a new post through
the WordPress REST API, we send a POST request to the post's resource through the
same URI as before. Pass along authentication information to get access to that
resource. Declare the content type as application/json and then include the actual
JSON data to be posted. The good news is we don't normally have to type out these
requests by hand and some of the metadata can be handled automatically. In a normal
application, we use scripts to handle the requests and responses, most commonly
some form of JavaScript.

Resource and representation

The key abstraction of information in REST is a resource. Any information that can
be named can be a resource: a document or image, a temporal service, like today's
weather in Los Angeles, a collection of other resources, a non-virtual object like
a person, and so on. 

A resource is a conceptual mapping to a set of entities, not the entity that corresponds
to the mapping at any particular point in time. The key here is that last part.
Conceptual mapping. Consider our librarian. When you submit a request to the librarian,
you specify a resource to retrieve. 

The interesting thing about resources is they can be collections, or singletons.
Red book in cubby number four is a singleton resource, meaning it points at a single
item. All red books is a collection resource, because it points at a collection of items, literally all red books.

This brings us to representation. REST components perform actions on a resource by
using a representation to capture the current or intended state of that resource
and transferring that representation between components. That means, rather than
accessing the actual data of the resource, we access a representation, effectively
a copy of that resource.  The data may be stored as XML, but the representation of
that data served to a client, can be JSON or HTML or any other format. 

So, the resource is whatever data sits in the location we're pointing at, the
representation is the literal representation of the data we get when we access that
resource.

Methodes \ Verbs

If you want to retrieve the data of a resource, you send a GET request. This
request will either return a 200 OK HTTP status along with the requested data or
a 404 Not Found HTTP status if there's nothing at the other end of the resource
or the resource is invalid. GET is used to get data from a resource.

GET the spesified resource, if available.

GET:

- Success 200 OK
- Failure 404 NOT FOUND

To send data from the client to the server, we have three different methods to
perform different types of actions:

- POST
- PUT 
- PATCH

POST - create a new resource and add it to a collection:

- Success 201 Created - with a link to the new resource ID in the response header
- Failure 
  - 401 Unauthorized or - if you don't have authorization to perform this action
  - 409 Conflict or - if the resource already exists
  - 404 NOT FOUND - if the request is sent to a resource that doesn't exist for some reason

PUT - update an existing singleton resource based on ID:

- Success 200 OK
- Failure
  - 401 Unauthorized or
  - 404 NOT FOUND or
  - 405 Method NOT allowed - If a Put request is sent to a collection resource,
    this status is returned since Put updates an existing singleton resource

204 No Content status when no content is present at the server

PUT is used to update data at an existing resource by replacing all of its contents
with the contents of the new request. Unlike POSTS which just contains the contents,
a PUT request contains the ID of the resource and the new content to be added to
that resource. If the resource already exists, the existing content is replaced with
the contents of the Put request. If no resource exists, the REST server may allow
a new resource to be created with the user defined ID.

PATCH - modify an existing singleton resource based on ID:

- Success 200 OK
- Failure
  - 401 Unauthorized or
  - 404 NOT FOUND or
  - 405 Method NOT allowed

Patch can carry along instructions on how to modify the existing resource without
necessarily replacing everything. 

DELETE - singleton resource based on ID:

- Success
- Failure
  - 401 Unauthorized or
  - 404 NOT FOUND

It deletes the specified resource. Delete can only be used with singleton resources.
If you try to delete a collection resource, you'll get a 405 Method Not Allowed
status because you should not be able to delete everything at once. 

There are two more methods you are likely to use from time to time. 

They are **Options** which returns a description of the communication options for
the target resource and **Head** which returns just the head section of that response.

### Response

HTTP status response

1xx - Information
2xx - Success
  200 OK - which means the request was successful
  201 Created - which means the request was successful and a new resource was created
  204 No content - meaning the server processed the request, but returned no content
3xx - Redirection
  301 Move permanently - which tells the client, use this URI for all future requests
  302/303 Found at this other URL
  307 Temporary redirect
  308 Resume incomplete
4xx - Client error
  400 Bad request - meaning the request is malformed or too large, or similar
  401 Unauthorized - meaning the client lacks proper authentication to access the
  resource
  403 Forbidden - meaning the request is outright refused by the server, typically
  because the client is not logged in, or does not have the correct permissions
  404 No found - means the resource does not exist in the first place
  405 Method not allowed - which kicks in if you try to use an HTTP verb like post
  on a resource that can only receive get requests
5xx - Server error
  501 Internal server error - meaning something went wrong of the server
  502 Bad gateway - meaning the server acts as a literal gateway or proxy, and
  received an invalid response from whatever it's trying to connect to
  503 Service unavailable - which is encountered when a server is overloaded or
  temporarily unavailable



TEST:

- A RESTful API is a service that runs on the web over HTTP to facilitate access
  to web resources.

  - [ ] FALSE
  - [x] TRUE

- Who can interact with a REST API?

  - [x] Anyone, unless the REST API includes an authentication layer or similar
        access restrictions.
  - [ ] Only users with the correct REST keys.
  - [ ] Anyone, even if the service includes an authentication layer or similar
        access restrictions.
  - [ ] Nobody unless it is explicitly made open and available.

- What is the relationship between URIs, URLs, and URNs?


  - [ ] URLs are URIs. URNs are something else.
  - [ ] A URN is the address part of the URL which is part of the URI.
  - [ ] The URI is a URL with the communication method defined. The URN is the
        address part of the URI.
  - [x] A URN can be a URL, and both are always URIs.

- REST is a stateless protocol. What does this mean?

  - [ ] It can remember client information between requests, but only if a state
        has first been established.
  - [ ] It belongs to no state - literally stateless.
  - [x] No client context or information (aka “state”) can be stored on the server
        between requests.
  - [ ] It doesn't have an internal state such as on and off, it just passes information.

- A representation of a resource is a unique copy of that resource, not the resource
  itself.

  - [ ] FALSE
  - [x] TRUE

- What is a REST API?

  - [ ] an application programming interface that literally rests until it is interacted
        with
  - [ ] an application programming interface that can follow the six constraints of REST
  - [ ] an application programming interface that allows a developer to define
        constraints for communication
  - [x] an application programming interface that follows the six constraints of REST

- What is a "resource"?

  - [ ] collections of files on a server
  - [ ] any single item on a database is a resource
  - [ ] files on a server
  - [x] any information that can be named can be a resource

- The purpose of a REST method is to tell the REST server how to retrieve resources.

  - [x] FALSE
  - [ ] TRUE

- What is the minimum requirement to send a successful REST request?

  - [ ] The request must use the GET method.
  - [ ] The request must contain a URI.
  - [x] The request must contain a method (verb) and a URI.
  - [ ] The request must contain a method (verb), a URI, and an authorization header.

- What is the correct verb to discover what methods are available for a specific
  REST resource?

  - [ ] GET
  - [ ] METHODS
  - [x] OPTIONS
  - [ ] HEAD

- Who reads the response header?

  - [ ] The server.
  - [ ] The browser.
  - [x] Primarily the client application, but anyone can read it.
  - [ ] The client application only. It's unavailable to humans.

- A status message in the 400 range means:

  - [ ] Communication error
  - [ ] 404 not found.
  - [x] Client error
  - [ ] Server error

- An authorization header is used to change the authorization level of the currently
  logged in user.

  - [ ] TRUE
  - [x] FALSE

- When you submit a DELETE request, what happens?

  - [ ] If the resource exists, it is deleted from the server.
  - [ ] If the resource exists and you have the correct authorization, the resource
        is marked as deleted on the server, but can still be retrieved.
  - [ ] The REST API is deleted.
  - [x] If the resource exists and you have the correct authorization, the resource
        is deleted or its status is changed on the server.

- What is the POST method used to do?

  - [x] Post a new resource with a unique ID on the REST server.
  - [ ] Post a request to the REST server.
  - [ ] Check for mail on the REST server.
  - [ ] Post a comment or a form submission.

- PUT/PATCH always do the same thing.

  - [ ] TRUE
  - [x] FALSE

- Some requests get no response. This is a REST feature.

  - [ ] TRUE
  - [x] FALSE

- What is the GET method used to do?

  - [x] Get the requested resource.
  - [ ] Get the requested resource header.
  - [ ] Get the requested resource URL.
  - [ ] Get the requested resource options.
