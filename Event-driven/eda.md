Event-Driven Architecture

Event-driven architecture involves events. You have a number of services or applications within a whole system, and each of those applications is emitting events that have some meaning to the overall system, or at least some services or other applications within the system. And when you emit those events, that is the driven part. That’s where we are driving those events toward some other services or applications in the system, and they’re going to react to those. And so really, reacting to events is what the other systems do.

So when you receive that event, you react to it, and that is event-driven. And it’s an architecture, because it’s not just events within a single service or application. It is events that are happening in several of those, if not all of them, and everybody is reacting to those in different ways. And you may even react to your own events. But that is where the events are driving what happens next.

Everything related to the event-driven is passive. They aren’t doing anything until they see an event that has a meaning to them.

One good design technique when you receive an event in an event-driven architecture is you don’t consume that event deeply internally into your model. Because that creates a very strong coupling between whoever emitted that event and published that event to you.

Benefits of EDA

Creating commands from the events, that helps with decoupling.

Because you’re using messaging to deliver these events, there is a time decoupling.

You do have latency at various times in the network. You will occasionally have network partitions that occur.

You are actually embracing latency. You’re embracing the network. You don’t even care, really, if there is latency. Unless it’s too much latency, like really, really too much latency. But that’s not a programmer’s decision. That’s not a software developer’s decision. Too much latency is the decision of the business. And you simply have, that’s why, again, conversations. So you ask the business, how long is too long?

Eventual Consistency

If two, let’s say, entities are dependent on some change, like one entity in one context has a change made to it, and another entity in another context needs a compensating change for that, or a reactive change based on the other change that happened, the only really practical way that you can do that is through eventual consistency.

A lot of developers can’t deal with some of the ways that DDD wants to deal with the eventual consistency.

When something goes wrong with choreography, it’s more difficult potentially to figure out where something went wrong. But if you only have one or two places where something could go wrong, it’s not much of a challenge.

Event Storming

Event storming is an activity in lightweight modeling. You start with big picture modeling. So this is where you’re trying to understand the process, the overall process through an entire system, as it relates to your current core domain. And so you’re using sticky notes of certain colors. And each of the colors represents a certain thing within the model. And the primary one is orange. And orange represents events.

Purple sticky represents policies. And a policy is basically a set of business rules.

Event Sourcing

Event sourcing uses events and a stream of events to represent some state.

A stream is just a collection. It’s an ordered collection of events. You have your zeroth event, and you have your N event on the high-end side. And so what you can do is take that collection, and starting with the first or the zeroth event, interpret that, and apply what that event means to your entity that owns that event, that emitted that event in the first place.

I’m going to mutate or modify my entity state based on those. As those events initially happened right there, they’re very much connected to command. So the entity receives a command, says, “Do this.” The entity does that, and it emits an event. And that event must somehow represent the change that needs to happen to that state. And you actually immediately mutate your state based on the event that you’ve just emitted. But then later, you can also reconstitute the state of that entity from the stream, or just that ordered collection, that sequence of events, zero through N, and reapply them to your state, and your state will be recovered.

What it’s really meant to do is to make a record of every individual thing, every unique thing that happens to that entity in the model. And then if you use event sourcing across every entity type, and every entity instance, then you have this global stream of everything that’s happened in your model ever over time.

You can actually create not only a total ordering of everything that belongs to that entity, but a total ordering of everything that has happened in that entire model or bounded context.

Don’t use it just because you think it sounds cool. But if you have these specific problems to solve are probably good compliances to me, like constraints to me within a certain industry, then use it.

