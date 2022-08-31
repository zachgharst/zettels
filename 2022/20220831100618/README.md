# Cloud Native Patterns - Ch. 7, The application lifecycle: Accounting for constant change

## Summary

## Having empathy for operations

Having empathy for operations is self-serving, since we are likely to be
doing ops as well as development.

Main operational concerns:

- *Manageability*: Management functions should be automateable,
  efficient, and reliable.
- *Resilience*: Platform should have a fail-safe way of detecting when
  an app has failed to recover.
- *Responsiveness*: Outputs should be received in a timely manner.
- *Cost management*: Being able to scale out/in and optimize away idle.

## Single-app lifecycle, multiple-instance lifecycles

It might seem wasteful to restart an app to pick up a configuration
change, especially with the use of an endpoint like `/refresh` which
would refresh application context (problem: load balancer would only
update 1 instance).

