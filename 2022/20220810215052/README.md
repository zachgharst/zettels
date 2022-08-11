# Cloud Native Patterns - Ch. 5, App redundancy: Scale-out and statelessness

## Summary

- Stateful applications don't work well in a cloud-native context.
- A sequence of interactions with a user is a common way for state to
  creep into your application.
- Stateful services are a special type of service that must address the
  significant challenges of data resilience in a distributed,
  cloud-based setting.
- Most apps should be stateless and should offload the handling of state
  to these stateful services.
- Making apps stateless is simple and realizes significant advantages in
  a cloud setting.

## Cloud-native apps have many instances deployed

The prevailing model in the cloud is to scale horizontally to increase
or decrease application capacity.