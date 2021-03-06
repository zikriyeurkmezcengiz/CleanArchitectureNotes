# WHAT IS ARCHITECTURE?
The primary purpose of architecture is to support the life cycle of the system. Good architecture makes the system easy to understand, easy to develop, easy to maintain, and easy to deploy. The ultimate goal is to minimize the lifetime cost of the system and to maximize programmer productivity.

# MAINTENANCE
**Spelunking** is the cost of digging through the existing software, trying to determine the best place and the best strategy to add a new feature or to repair a defect.

# KEEPING OPTIONS OPEN
It is not necessary to choose a database system in the early days of development, because the high-level policy should not care which kind of database will be used. Indeed, if the architect is careful, the high-level policy will not care if the database is relational, distributed, hierarchical, or just plain flat files.

**A good architect maximizes the number of decisions not made.**

# DEVICE INDEPENDENCE

By the late 1960s, we had learned our lesson—and we invented device independence. The operating systems of the day abstracted the IO devices into software functions that handled unit records that looked like cards. The programs would invoke operating system services that dealt with abstract unit-record devices. Operators could tell the operating system whether those abstract services should be connected to card readers, magnetic tape, or any other unit-record device.
Now the same program could read and write cards, or read and write tape, without any change. The Open–Closed Principle was born (but not yet named).

The value of device independence was enormous!

# INDEPENDENCE
A good architecture must support : 
* The use cases and operating of system
* The maintenance of teh system 
* The development of the system 
* The deployment of the system

# Use Cases

The arhitecture must support the use cases. 

# Decoupling Layers and User Cases

At the same time, use cases are narrow vertical slices that cut through the horizontal layers of the system. Each use case uses some UI, some application-specific business rules, some application-independent business rules, and some database functionality. Thus, as we are dividing the system in to horizontal layers, we are also dividing the system into thin vertical use cases that cut through those layers.

**A good architecture leaves options open.**

# DRAWING BOUNDRY LINES
Early in the development of FitNesse, we drew a boundary line between business rules and databases. That line prevented the business rules from knowing anything at all about the database, other than the simple data access methods. That decision allowed us to defer the choice and implementation of the database for well over a year. It allowed us to try the file system option, and it allowed us to change direction when we saw a better solution. Yet it did not prevent, or even impede, moving in the original direction (MySQL) when someone wanted it.

The fact that we did not have a database running for 18 months of development meant that, for 18 months, we did not have schema issues, query issues, database server issues, password issues, connection time issues, and all the other nasty issues that raise their ugly heads when you fire up a database.

# Plugin Architecture 
Indeed, the history of software development technology is the story of how to conveniently create plugins to establish a scalable and maintainable system architecture. The core business rules are kept separate from, and independent of, those components that are either optional or that can be implemented in many different forms. 

![The PluggingIntoTheBusinrssRules](https://github.com/zikriyeurkmezcengiz/CleanArchitectureNotes/blob/0ea3109b0715dced20fd2ccc3a2bc6c3aa41cf98/src/assets/images/PluggingIntoTheBusinessRules.png)

# POLICY AND LEVEL

Note the dashed border surrounding the Encrypt class, and the CharWriter and CharReader interfaces. All dependencies crossing that border point inward. This unit is the highest- level element in the system.

![PolicyAndLevels](https://github.com/zikriyeurkmezcengiz/CleanArchitectureNotes/blob/cf37dabbcba0f8e46555551c3ba3562d101c494f/src/assets/images/PolicyAndLevels.png)

ConsoleReader and ConsoleWriter are shown here as classes. They are low level because they are close to the inputs and outputs.


Recall that policies are grouped into components based on the way that they change. Policies that change for the same reasons and at the same times are grouped together by the SRP and CCP. Higher-level policies—those that are farthest from the inputs and outputs—tend to change less frequently, and for more important reasons, than lower- level policies. Lower-level policies—those that are closest to the inputs and outputs— tend to change frequently, and with more urgency, but for less important reasons.

# CLEAN ARCHITECTURE

Characteristics of clean architecture : 

* Testable. The business rules can be tested without the UI, database, web server, or any other external element.
* Independent of the UI. The UI can change easily, without changing the rest of the system. A web UI could be replaced with a console UI, for example, without changing the business rules.
* Independent of the database. You can swap out Oracle or SQL Server for Mongo, BigTable, CouchDB, or something else.Your business rules are not bound to the database.
* Independent of any external agency. In fact, your business rules don’t know anything at all about the interfaces to the outside world.

![CleanArchitecture](https://github.com/zikriyeurkmezcengiz/CleanArchitectureNotes/blob/9182c0b8c7943a0644d417baee6b9b3656017da7/src/assets/images/CleanArchitecture.png)

**Conclusion** : 
Aome very smart people have told us, over the years, that we should not anticipate the need for abstraction. This is the philosophy of ***YAGNI***: “You aren’t going to need it.” There is wisdom in this message, since over-engineering is often much worse than under- engineering. On the other hand, when you discover that you truly do need an architectural boundary where none exists, the costs and risks can be very high to add such a boundary.

# HUMBLE OBJECT PATTERN
TODO: Need more research. 

# MAIN COMPONENT 

Think of Main as a plugin to the application—a plugin that sets up the initial conditions and configurations, gathers all the outside resources, and then hands control over to the high-level policy of the application. Since it is a plugini it is possible to have many Main components, one for each configuration of your application. 

# SERVICES: GREAT AND SMALL

**THE DECOUPLING FALLACY** : 
Services are decoupled at the level of individual variables. However, they can still be coupled by shared resources within a processor, or on the network. What’s more, they are strongly coupled by the data they share.
For example, if a new field is added to a data record that is passed between services, then every service that operates on the new field must be changed. The services must also strongly agree about the interpretation of the data in that field. Thus those services are strongly coupled to the data record and, therefore, indirectly coupled to each other.

The decoupling fallacy means that services cannot always be independently developed, deployed, and operated. To the extent that they are coupled by data or behavior, the development, deployment, and operation must be coordinated.

# THE TEST BOUNDARY

When developers realize that simple changes to the system can cause massive test failures, they may resist making those changes. The first rule of software design-whether for testability or for any reason-is always the same. Don't depend on volatile things. GUIs are volatile. Test suites that operate the system through the GUI must be fragile. Therefore design the system, and the tests, so that business rules can be tested without using the GUI.