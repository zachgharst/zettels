# Cloud Native Patterns - Ch. 4, Event-driven microservices: It's not just request/response

## Summary

- Both request/response and event-driven protocols are used to connect
  components in cloud-native software.
- Microservices can implement both protocols.
- Under ideal circumstances, software implementing one protocol yields
  the same outcome as software implementing the other.
- In a cloud setting, however, the solution is highly distributed and
  constantly changing with wildly varying outcomes.
- CQRS plays an important role in event-driven systems.

## We're (usually) taught imperative programming

The vast majority of students are taught imperative programming: the
programmer provides a set of instructions that are executed from start
to finish. This drives programmers to think in a request/response model.

But software is no longer executing in a single process or on the same
computer. A single request to Netflix's homepage results in a fan of
downstream requests; if it were only successful when all cascading
requests are successful, Netflix wouldn't work well. Patterns like
automatic retries, multiple microservice instances, and caching help to
achieve these resiliency patterns.

## Reintroducing event-driven computing

For an event-driven system, one thing is common: the entity that
triggers code execution is fire and forget and doesn't expect
a response. Compared to request/response, the client/server aren't
dependent on each other to go smoothly. The event, and its outcome, are
disconnected and uncoupled entirely.

## My global cookbook

The author is building a site that pulls together content from favorite
sites and organizes it. One of the views is a list of latest posts: the
Connections' Posts content produced by a service. There are two parts:
a list of people or sites being followed and a list of content provided
by those sources. These are two additional services.

**Request/response**: JavaScript in the browser makes a request to the
Connections' Post service with a parameter for the individual requesting
the page and waits for a resposne. The Connections' Post service makes
a request to Connections service for a list of followed blogs and waits
for a response. The Connections' Post service then uses the list to
request the Posts service for the list of posts by those blogs and
waits. The Connections' Posts service finally composes the data and
responds to the webpage with another request to the Connections service
to find the username from the user IDs.

**Event-driven**: Code is executed when something happens. With
event-driven, the Connections and Posts services will proactively send
out change notifications rather than waiting to be asked. When
Connections' Posts is asked for data, it already knows the answer with
no downstream requests. A request is made, and the data is fetched from
the database directly by the Connections' Posts which is a result of
propagated events.

In the book, she describes this event as being emitted as an HTTP POST.
When a new blog is made, it makes a POST request to Connections' Post to
record that entry. Connections' Post is entirely autonomous. This allows
for the services to be loosely coupled. As well, aggregation happens
when events are processed *not* when they are requested.

## Introducing Command Query Responsibility Segregation

Separate write logic (commands) from read logic (queries). This is the
root of CQRS pattern. Separate models and controllers allows for this --
code is easier to understand and maintain and the surface area for bugs
is reduced. Because of this, it also allows for different protocols on
both sides (maybe Functions as a Service)

## Different styles, similar challenges

Both implementations talk about the happy path. Imagine:

- Network partitions cut off from one another
- Unexpected latency in producing lists of individuals
- The services are running on unstable IP addresses
- Certificates and credentials need to be rotated
