# THE DATABASE IS A DETAIL 

I am not talking about the data model. The structure you give to the data within your application is highly significant to the architecture of your system. But the database is not the data model. The database is piece of software. The database is a utility that provides access to the data. From the architecture’s point of view, that utility is irrelevant because it’s a low-level detail—a mechanism. 
**And a good architect does not allow low-level mechanisms to pollute the system architecture.**

The organizational structure of data, the data model, is architecturally significant. The technologies and systems that move data on and off a rotating magnetic surface are not. Relational database systems that force the data to be organized into tables and accessed with SQL have much more to do with the latter than with the former. The data is significant. The database is a detail.

# THE WEB IS A DETAIL

Now imagine you were a software architect at Q. Imagine that some marketing genius convinces upper management that the whole UI has to change to look more like the web. What do you do? Or, rather, what should you have done before this point to protect your application from that marketing genius?
You should have decoupled your business rules from your UI. I don’t know whether the Q architects had done that. One day I’d love to hear their story. Had I been there at the time, I certainly would have lobbied very hard to isolate the business rules from the GUI, because you never know what the marketing geniuses will do next.

You should have decoupled your business rules from your UI. I don’t know whether the Q architects had done that. One day I’d love to hear their story. Had I been there at the time, I certainly would have lobbied very hard to isolate the business rules from the GUI, because you never know what the marketing geniuses will do next.

