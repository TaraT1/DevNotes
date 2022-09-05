---
id: cavkmujnsr6fx6bynolnjws
title: Mvc
desc: ''
updated: 1662346117237
created: 1661694652649
---
The Model-View-Controller (MVC) is a software architectural pattern that separates an application into three main logical components: the model, the view, and the controller. Each of these components are built to handle specific development aspects of an application. MVC is one of the most frequently used industry-standard web development framework to create scalable and extensible projects.

Software Architecture defines fundamental organization of a system.
- defines how components of a software system are assembled
- serves as blueprint for software app and dev basis for dev team

Software Architecture Design are used to represent how a system will act on the basis of software elements, relationships and properties. Helps to connect technical and operational aspects of defining and structuring a solution
- software architecture defines the blueprints of a system. Serves as communication and coordination mechanism of the elements. Designs structured solution while keeping performance, security, etc. in check. Impacts quality, maintainability and overall performance of system
- software design - method of developing plan that takes user requirements and available resources to find optimal design. Lays the path for devs and managers to develop project to meet customer demands.


2 main approaches to large-scale software are monolithic and services based
- monolithic architecture is a design style that is holistic and self-contained. Can get complex. If something breaks the system, the whole thing breaks
- services-based architecture 
    - service-oriented architecture often shares and reuses elements between differenct components of the software system
    - microservices often break components down farther than in service-oriented arch and create smaller components as self-contained units
    
## Software Architecture Patterns 
Software arch organizes code and defines development. Software architecture encompasses the patterns and practices necessary to manage volume and complexity involved in producing software.

1. Client-server architecture is network architecture that follows the request-response model. The interwebs, banking, email, file sharing are examples.
2. Model-View-Controller separates application logic into three components
- models (contains application's data and main functionality - data and logic)
- views (user interface - displays data and interacts with user)
- controller (handles user input, mediates between model and view - request handler)

Each pattern has advantages and drawbacks. Other software architecture patterns are:
- circuit breaker
- command query responsibility segregation (CQRS)
- controller-responder
- pub-sub
- saga
- static content hosting

### References: 
    - https://www.geeksforgeeks.org/how-to-design-a-web-application-a-guideline-on-software-architecture/?ref=rp
    - https://builtin.com/software-engineering-perspectives/software-architecture
    - https://en.wikipedia.org/wiki/Model%E2%80%93view%E2%80%93controller
    - https://www.redhat.com/architect/14-software-architecture-patterns
    - https://get.oreilly.com/rs/107-FMS-070/images/Software-Architecture-Patterns.pdf

    MVC Watch: DevMarketer's MVC video: https://youtu.be/1IsL6g2ixak 
    - used by many frameworks

    Frameworks like Rails, django, ios, objective c, implement MVC
    M - model
    V - view
    C - controller

    - DRY
    - structured programming so everything has its place

    Flow
    - client (browser) -->> server (Linux, server-side languages)
    - servers don't store info. Info stored in db (MySQL, Postgres, MongoDB)
        - modular
    
    - Server (controller) 
        - processes GET/POST/PUT/DESTROY requests
        - server-side logic
        - middle-person
            - info from user
            - processes info and talks to db if needed
            - receives info from db
            - speaks to view to explain how present
    - M DB (model); 
        - adding and retrieving items from db
        - processing data from or to db
        - speaks only to controller
    - V Client (view)
        - only thing user ever sees
        - html/css
        - only listens to controller

   Route processing occurs through controllers

   Every framework handles differently

tutorials: http://jacurtis.com
Follow me on Twitter: http://twitter.com/_jacurtis
