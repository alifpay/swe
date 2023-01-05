### Designing Events and Event Streams

What Are Events?  

First of all, events provide a record of what happened in the business. These business incidents are modeled as single events and record all the important business details about what happened and why.

Events are named based on past-tense terminology. For example, booking a flight may result in a flight_booked event, while the completion of an e-commerce order may result in an order_shipped event.

Once an event is recorded, they are written into an event stream.

Both events and event streams are completely immutable—once published, you can’t change their contents, nor can you change their order in the stream.
Many different consumers can use the events, however they choose, within their business logic.
Consumers may choose to ignore events within the consumed event stream, but they undeniably occurred.
The events are durable and replayable—they stick around as long as they’re needed.
A log of events in a stream can be used to construct a detailed picture of the system over time, rather than just as a snapshot of the present.

But what do you put into an event?

Some of the initial questions you need to ask yourself are: Who is the intended user of the data? Is this an event made for your own internal usage? Or are you looking to share it across your boundary to others?

It’s useful to start thinking about the boundaries of your systems. Any given service has its own service boundary—a division between where the internal world transitions to the external world, where encapsulation of data models and business logic give way to APIs, event streams, and remote procedure calls.

In the world of domain-driven design, the boundary between the internal and external world is known as a “bounded context.”

https://developer.confluent.io/learn-kafka/event-design/intro/
