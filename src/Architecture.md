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

TODO: The PluggingIntoTheBusinrssRules.png will be used in here. 

# POLICY AND LEVEL

Note the dashed border surrounding the Encrypt class, and the CharWriter and CharReader interfaces. All dependencies crossing that border point inward. This unit is the highest- level element in the system.
TODO: The PolicyAndLevels.png will be used in here. 

ConsoleReader and ConsoleWriter are shown here as classes. They are low level because they are close to the inputs and outputs.


Recall that policies are grouped into components based on the way that they change. Policies that change for the same reasons and at the same times are grouped together by the SRP and CCP. Higher-level policies—those that are farthest from the inputs and outputs—tend to change less frequently, and for more important reasons, than lower- level policies. Lower-level policies—those that are closest to the inputs and outputs— tend to change frequently, and with more urgency, but for less important reasons.

# BUSINESS RULES
