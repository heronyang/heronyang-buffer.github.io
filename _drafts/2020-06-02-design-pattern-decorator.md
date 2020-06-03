# Design Pattern - Decorator

Reading [the explanation of decorator design
pattern](https://refactoring.guru/design-patterns/decorator), I found this
design pattern weaken the contract between components, which is a big reason for
you to stay away from it.

Adopting decorator pattern means you don't have to change how the callers use
the interface. Using the example of sending notification as described in [the
guru's page](https://refactoring.guru/design-patterns/decorator), we can make
the same interface, Notifier, to send to multiple destinations without changing it.

That is, we don't update the interface but we make the code do something not
being promised before. Originally, each notifier is coded in the way that it
sends notification to one destination. It is the contract either implicitly or
explicitly described somewhere. However, after the change, one Notifier can send
to multiple destinations which will start to confuse people over time.

Instead, to solve the same problem, I prefer to define a new interface which
promise to resolve the new use case, sending to multiple destinations. This new
interface contains a set of Notifiers and provide a clear contract saying it
sends noficiations to one or many destinations. This makes each interface does
exact one clear thing (Single Responsibility Principle).

The downside of my proposed alternative is that requires code change of the
callers. However, I think it is expected as the caller is now doing something
different and this change should be awared by the caller.
