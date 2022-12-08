Interface Segregation Principle

The fourth principle is the interface segregation principle, which reads:

Clients should not be forced to depend on methods they do not use.

In Go, the application of the interface segregation principle can refer to a process of 
isolating the behaviour required for a function to do its job. As a concrete example, 
say I’ve been given a task to write a function that persists a Document structure to disk.

```Go
type Shape interface{
    drawCircle()
    drawSquare()
    drawRectangle()
}
```

This interface draws squares, circles, rectangles. Circle, 
Square or Rectangle implementing the Shape interface must define the methods drawCircle(), drawSquare(),drawRectangle().

It’s quite funny looking at the code above. Rectangle implements methods (drawCircle and drawSquare) it has no use of, 
likewise Square implementing drawCircle, and drawRectangle, and Circle (drawSquare, drawSquare).


Let's first discuss why fat interfaces might be a bad thing. Fat interfaces have more methods 
and are therefore likely to be harder to understand. They also require more work to use, 
whether this be through implementing, mocking, or stubbing them.

Fat interfaces indicate more responsibility and, as we saw with the SRP, the more 
responsibility an object has, the more likely it will want to change. If the interface changes, 
it causes a ripple effect through all its users, violating OCP and causing a massive 
amount of shotgun surgery. This is the first advantage of ISP:

ISP requires us to define thin interfaces

For many programmers, their natural tendency is to add to the existing interface rather 
than define a new one, thereby creating a fat interface. This leads to a situation where the, 
sometimes singular, implementation becomes tightly coupled with the users of the interface. 
This coupling then makes the interface, their implementations, and users all the more resistant to change.
