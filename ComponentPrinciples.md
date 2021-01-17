# TOP-DOWN DESIGN

The component structure cannot be designed from the top down. It is not one of the first things about the system that is designed, but rather evolves as the system grows and changes.
If we tried to design the component dependency structure before we designed any classes, 
we would likely fail rather badly. We would not know much about common closure, we would be unaware of any reusable elements, and we would almost certainly create components that produced dependency cycles. 
Thus the component dependency structure grows and evolves with the logical design of the system.

# THE STABLE DEPENDENCIES PRINCIPLE

Any component that we expect to be volatile should not be depended on by a component that is difficult to change. 
Otherwise, the volatile component will also be difficult to change.
It is the perversity of software that a module that you have designed to be easy to change can be made difficult to change by someone else who simply hangs a dependency on it.

# STABILITY
Webster’s Dictionary says that something is stable if it is “not easily moved.” Stability is related to the amount of work required to make a change. On the one hand, the standing penny is not stable because it requires very little work to topple it. 
On the other hand, a table is very stable because it takes a considerable amount of effort to turn it over.

# STABLE ABSTRACTIONS PRINCIPLES
A component should be as abstract as it is stable.
Thus, if a component is to be stable, it should consist of interfaces and abstract classes so that it can be extended. Stable components that are extensible are flexible and do not overly constrain the architecture.