---
layout: post
comments: true
title:  "RESTful Notes"
---

### What does RESTful mean?

*Representational State Transfer (REST)*

  - Representation
    - representation layer of *Resources*
    - Resource is the key to RESTful
    - Resource represents an entity on internet such as music, image, text etc.
    - URI is used to locate a resource
    - URI only cares the LOCATION of a resource
    - mp3, txt, png etc. are the *representation* of a resource, which is not part of URI

  - State Transfer
    - We need to change resource's state
    - We(client side) most likely use HTTP to change resource's state by utilize HTTP's predefined methods "get", "post, "put", "delete" etc.

### Architectural constraints

  - Client-Server
    - Request starts from client to server
    - Clients are not concerned with data storage
    - Servers are not concerned with user interface and user state
  
  - Stateless
    - There are no client sessions being stored in server side. Each request from any client contains all the information necessary to service the request, and session state is held in the client.
    - A session state could be transferred by server to another service such as database to maintain a persistent state for a period of time and allow authentication.
  
  - Cacheable
    - Client may have ability to cache response.
    - Responses from server have to implicitly or explicitly, define themselves as cacheable, or not, to prevent clients from reusing stale or inappropriate data in response to further requests.

  - Layered system
    - A client cannot ordinarily tell whether it is connected directly to the end server, or to an intermediary along the way.

  - Uniform interface
    - The uniform interface is fundamental to any REST services. It simplifies and decouples the architecture, which enable each part to evolve independently.
    
    - There are four constraints for uniform interface
      1. **Identification of resources**     
         Individual resources are identified in requests, for example using URIs in web-based REST systems. The resources themselves are conceptually separate from the representations that are returned to the client. For example, the server may send data from its database as HTML, XML or JSON, none of which are the server's internal representation, and it is the same one resource regardless.
      
      2. **Manipulation of resources through these representations**    
         When a client holds a representation of a resource, including any metadata attached, it has enough information to modify or delete the resource.
      
      3. **Self-descriptive messages**      
         Each message includes enough information to describe how to process the message. For example, which parser to invoke may be specified by an Internet media type (previously known as a MIME type). Responses also explicitly indicate their cacheability
      
      4. **Hypermedia as the engine of application state**      
         Clients make state transitions only through actions that are dynamically identified within hypermedia by the server (e.g., by hyperlinks within hypertext). Except for simple fixed entry points to the application, a client does not assume that any particular action is available for any particular resources beyond those described in representations previously received from the server.



**One can characterise applications conforming to the REST constraints described in this section as "RESTful". If a service violates any of the required constraints, it cannot be considered RESTful.**
