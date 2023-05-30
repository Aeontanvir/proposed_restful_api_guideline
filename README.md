# Restful API Best Practices

RESTful API best practices include: meaningful resource endpoints, proper HTTP verbs, clear error handling, pagination and filtering, content negotiation, secure authentication and authorization, versioning, comprehensive documentation, performance optimization, and adherence to naming conventions and REST constraints.

### Table of Content

1. Preface
2. Overview
    1. Brief Overview
    2. Where the State comes from
3. Characteristics and Constraints of RESTful Server
4. Key Points to Remember
5. Understanding RESTful API verbs
6. Planning a RESTful API
7. Uniform Interface
8. Design Pattern of Uniform Interfaces (aka Endpoints)
    1. Overview
    2. Basic Design Patterns
9. Request and Response Format
10. Exception Handling and Error Response Format



### How to use this Document

1. HEADING NUMBERINGS: This document uses the following Google Docs Add-on (see the Add-ons menu in the menu bar) to generate the heading numberings automatically. After you have added a new heading, please use this Add-on to re-update the heading numbers. The Add-on appears as a right-side sidebar.
2. BOOKMARKS: In order to refer to specific places in this document from other tools like JIRA/Wrike/Trello, please use the bookmark feature. To create, place cursor at the place (except any heading since heading bookmarks get replaced by the TOC add-on) for which you want to create a bookmark and from Insert menu, select Bookmark. If any bookmark  link doesn't work any more, re-create the bookmark and use the new link.
3. TABLE OF CONTENT REFRESH: If you have added any heading/subheading, please remember to update the heading numbers first (follow the instructions above in item #1) and then refresh the Table of Content above, too.
4. CODE SNIPPETS FORMATTING: To format code snippets, please use the Add-on "Code Pretty" from Add-ons menu (install it if you don't have it). First, to remove source application formattings,  copy-paste your text to any plain text editor. Then from the plain text editor, copy paste to this document. Then select the text and select the Add-ons > Code Pretty > Format Selection menu option.
5. CHAT OR EMAIL SNIPPETS FORMATTING: To format chat or email snippets, just use the Consolas font. First, to remove source application formattings,  copy-paste your text to any plain text editor. Then from the plain text editor, copy paste to this document. Then select the text and then select the Consolas font from the Font drop-down menu in the toolbar. You should use font size 8 for such snippets.
6. PAGE NUMBERS: Page numbers appear at the top-right corner of each page.
7. TABLES: For tables, please use the color scheme for heading given in the sample table. You should use font size 8 for all of the table's content, except the header, which will be in regular font size 10.
8. STAND-OUT TEXT: Please use the color "cornflower blue" from the font colors menu for any stand-out text.
9. ANY COPY-PASTE: In order to not disrupt the formattings of this document, please don't do any copy-paste directly to this document. First paste the content to any plain text editor so that any source formatting is removed and then copy it again from the editor and paste to this document.
10. COMMENTING: To comment and discuss on any part of text of the document, please select the text and use the Ctrl-Alt-M commenting feature.



## Preface

In this document I am writing a very basic RESTful API and  common patterns and best practices followed by industry for designing a RESTful API. Best practices are  dictated by use cases, problem spaces, preferences and way of solving problems. I am welcoming everybody for feedback and suggestions. I am all ears.



## Overview

### Brief Overview
RESTful which stands for REpresentational State Transfer. REST gives a coordinated set of constraints to the design of components in a distributed hypermedia system that can lead to a higher-performing and more maintainable architecture. To the extent that systems conform to the constraints of REST they can be called RESTful. RESTful systems typically, but not always, communicate over HTTP with the same HTTP verbs (GET, POST, PUT, DELETE, etc.) which web browsers use to retrieve web pages and to send data to remote servers. REST interfaces with external systems using resources identified by URI,  which can be operated upon using standard verbs

### Where the State comes from
In the RESTful API we represent the state of resources. 



## RESTful vs CRUDful
A very common misconception is that RESTful also means CRUDful. CRUD is an operation that we do on resources. REST is the way in which we represent the state of a resource before or after doing CRUD operation(s).



## Characteristics and Constraints of RESTful Server

A RESTful server 

1. Must be developed following Client-Server Model
2. Must be stateless but this criteria dictated by use case and scalability
3. Should be Cacheable
4. Must have robust (as much as possible) error/exception handling.
5. Must have uniform interfaces of
    1. Identification of resources
    2. Manipulation of resources through those identification interface
    3. Self descriptive message
    4. Simple entrypoint to the application



## Key Points to Remember

While designing a RESTful API interface we must keep these 5 points in mind. Each point deserves a paragraph and further explanation. I am leaving it  to explore for others.

1. Expose enterprise data and functionality in API friendly format:  RESTful API must be able to convert complex on-premise application services / microservices into Developer friendly APIs and give developers the resources they need to create applications that deliver real value.
2. Protect Information and Assets: Ensuring that enterprise systems are protected against message-level attack, hijack and prevent misuse of exposed information.
3. Authorize Secure, Seamless Access for Valid Identities: Ensure strong Access Control, identity federation and social login functionality in a secure manner. Limiting access to resources based on identity.
4. Optimizing System Performance and API lifecycle: RESTful API must be fast and optimal to access. This means it client should not take long  to get response from the API server. API must have a life-cycle or distinguishable by proper versioning system
5. Deployment: RESTful APIs must be easy to deploy in rollback mannar.



## Understanding RESTful API verbs 

1. GET:  When a client needs to access resources it must initiate a HTTP GET request to the API server. RESTful API Server sends only that information to fulfill clients' needs according to its access level or reject requests with proper error messages. Such kind of requests must be idempotent and safe.
2. POST:  When a client needs to create a resource it must initiate HTTP POST request to the API server. A RESTful API server must send a resource identifier  on success or reject requests with proper error messages. Such kind of requests are not safe and not idempotent.
3. PUT: When a client needs to update it must initiate a HTTP PUT call to API Server. Client must send full data of that resource to update while it is initiating a PUT call. Server must send the identifier or updated resources on success.  This type of call is idempotent but not safe.
4. PATCH: When client does not need to update a whole resource but partially then client must initiate a PATCH request to API server and server must send appropriate identifier or updated resource on success. Some programming languages still do not support PATCH requests. In that case PUT request can be used but Server logic should handle this properly as this request is not idempotent and safe.
5. DELETE: Client needs to initiate a HTTP DELETE call to API Server when it wants to delete a resource. This call is idempotent but not safe. This is also a non-reversible call so proper caution must be provided.
6. HEAD and OPTIONS: The OPTIONS method allows the client to determine the options and/or requirements associated with a resource, or the capabilities of a server, without implying a resource action or initiating a resource retrieval and The HEAD method is identical to GET except that the server MUST NOT return a message-body in the response. Both methods are idempotent and safe.



## Planning a RESTful API

Somewhere I read that a better planning makes job done half. When you are planning  a RESTful API  you must have clear vision on 

1. Problem Space
2. Scope of various resources
3. Context of a resource
4. Separation of concern


## Uniform Interface

Servers must have uniform Interfaces to access resources which must be unique and based on above criterias.



## Design Pattern of Uniform Interfaces (aka Endpoints)

### Overview

While designing Endpoints we need to keep these things in mind

1. RESTful server can be accessed by FQDN or IP
2. Various API can be hosted on subdomains or its own Domain depending on SOC.
3. Endpoints can be started with api business version number or optional /api. It depends on how we are hosting and managing APIs
4. Port is optional if services run on standard HTTP port (80)
5. Listing proper Headers for an endpoint depending on which type of resources we are dealing with


