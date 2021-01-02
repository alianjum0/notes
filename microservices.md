# Microservices
Provides distribution, scalability and agility.

### Core concepts of Microservices
1. Services
2. Communications
3. Distribution
4. Database and transactions
5. API layer
### Advanced Concepts
1. Asynchronous communications
2. tracing and logging
3. Continuous delivery
4. Hybrid Architecture
### Architecture Choices
1. Design considerations
2. Managing trade-off
3. Edge services
4. DevOps culture

### For Managers
1. Focus on key benefits
2. Explain the risks
3. Bottom-line impacts

### For Architects
* Foundational knowledge
* Prepare you to ask the right questions
* exposes you to the rewards and risks

### For Developers
* Foundational knowledge
* Answer the why questions
* Not a coding courses

## History of service-based architecture
> monolithic architecture -> service based architecture -> Microservices
### Monolithic Application
* Highly coupled
* Agility and maintainabilty is highly impacted and also scalability
### Services-oriented Architecture
Values
* string contract
* WSDL- best part of SOAP
Issues
* envelope is wasted space
* Ok and Fault only, nothing in between
### Microservices
* Decomposition- break into smaller units
All communications over ReST
Polyglot development support

* Microservices are cheap
* can be done open-source
Agility and ability to distribute are the main pros

Cost of moving to Microservices
* complexity - many components
* distribution tax 
* reduction of reliability- more part -> more reliability issues

Maximise benefits while reducing risks

### Microservices and cloud native
They are different but often go together
### Cloud Infrastructure
types
1. Public cloud
2. Private
3. Hybrid
Microservices set very well in cloud infrastructure

### Cloud-Native Microservices-Based
* Single code base
* Completely self-contained
* Zero file system usage

* It's not about the size, it's about the operation
* all inter-service call is ReST based
* unify service documentation to be able to inter communicate

Domain Driven design helps in this
As class in object oriented programming, service is in microservices.
Services are divided by domains.

Problems in service design Anti-pattern
1. Too fine grained
2. Not fine grained enough

### The communication dance
All communication is over HTTP using ReST based services
This strategy is called Protocol-Aware Heterogeneous Interoperability

* This allows the flexibility to create service in different languages. e,g
back-end in Java, Front-end in Nodejs, Data science in Python

* This provides agility to the project.

* Problem can arise from all the network calls,as each service can call any other
service.

### Distribution and scale
* the communication pattern is benefit for distributive and highly scalable
pattern.
* Enterprise and Internet needs
- Customer-facing application
- Business-facing applications
- All for day 2 growth from day 1

Traditional Strategy of Monoliths
* Scale for the busiest day every day
All this comes with a price

### The dangers if latency and gridlock
As traffic increases and have many calls then latency can become a big problem.
This can cause gridlock. In a circular call stack latency can become a problem
early.
Circuit breaker pattern can be use to solve this problem.
When latency start occur, you then trip the circuit and perform default
behaviour. Extra functionality is not provided but functionality is completed.
And system is saved from crippling.
### Bounded Context
design pattern to decompose large multi-domain system into microservices.
Core Concepts
* Investigate working system
* Determine the domains
* Break services up accordingly
Spend time in actually evaluating traffic in the real world use cases.
- reduce cross domain calls
knowledge is the key while dividing into service.

String contracts and well-defined boundaries allow for self-discovery.

### Data domain as a service boundary
Transactional boundaries
* Cannot eliminate transactions completely
* No distributed transactions
* New ways of thinking are needed

 Building low level domains for low-level services is one of the hardest parts
of a microservices for various reasons.

Different ways to solve this problem

Minimise the cross domains calls.
### No ACID, only BASE
atomic, consistent, Isolated, Durable

In microservices models they don't exist.

We strive for eventual consistency. BASE

Aim for eventual consistency as may places as possible and it will eventually
improve system health as a whole.

### The API layer
API layer is of critical importance

API layer is nothing more than an aggregated proxy of all of services offering.

### Asynchronous communications 
Async communication is not easy.
1. An example is event driven model
2. An other example is stream data platform. Producer-Consumer

### Logging and tracing in a microservices architecture
Plan for unified logging strategies across your entire platform.
Is very critical in troubleshooting
* Day to Day operations
* Troubleshooting
* Maintenance
* Investigation
* General tasks

It can be more challenging in microservices
* Larger volume of artifacts
* Agile nature
* Different teams- different logging strategies
A unified logging is very important as the system gets distributed
trace-ID for logging across the services
### continuous delivery as a requirement
* Has many moving parts
* Improves success 

Build step -> Automated deployment (Non Production) -> Production
It is required to achieve agility in this architecture
start small and then expand from there.

### Hybrid architecture: Hierarchy and service-based
1. Hierarchical Service Architecture
* Many thought leaders are opposed to this model
* Prevents circular dependencies
* Models an n-tier architecture via services instead of modules
2. Service based architecture
* Single underlying database
* Leverages services to handle decomposition
* Gains some agility without modifications to datastore
consider all the benefits and risks of each model before diving into it and
make sure to maximise the benefits.

## Making Architecture Choices
### Design Considerations
1. CI and CD should be first aspect to your design.
2. Logging and tracing should be the second aspect of your design.
Leveraging domain driven design.

Service design to control latency
* Consider non-blocking code
* Standardize your stack when possible

Design everything async until you prove it is required synchronous.
### The trade-offs
1. Benefits of paying the distribution tax
* Distributability
* Well-defined service boundaries
* Scalability

2. Issues of complexity
* Scalability and deployment
* Large number of moving parts

3. Polyglot deployment practices
* Many pros and cons
* Use it as a tool
* Consider standardization

Spend serious time in evaluating these trade-offs

### An argument for edge services
API layer should be used only as a proxy layer

Two distinct types of edge services
1. Outbound edge service
Expose your clients specific need to the outside world
2. Inbound/Translation edge services
Abstract you from third party dependencies

An edge service to use between clients API. To change at one place when needs
to change client.

Key benefits of edge services
* Manage code informations similar to other code in your system
* Provide a consistent interface even if underlying services change.

### Embracing DevOps
Never underestimate culture
Monitor a microservices system to ensure lag doesn't have major impacts.

