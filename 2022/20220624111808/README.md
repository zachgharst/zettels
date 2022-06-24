# Cloud Native Patterns: Ch. 2, Running cloud-native applications in production

[Cloud Native Patterns by Cornelia
Davis](https://www.goodreads.com/book/show/36410104-cloud-native-patterns)

## Summary

## The Obstacles

![Figure 2.1](figure_2.1.png)

- Handling production operations is a difficult and thankless job.
  Application development groups and operations teams may blame each
  other for failure to serve customers.
- Fear of the consequences of a deployment has the effect of limiting
  the frequency with which you can deploy.
  - It isn't unusual for a deployment to require downtime or cause
    unexpecterd downtime, which is expensive.
  - There are labor costs associated with keeping test environment in
    line with production, complicated by need to remove PII from test
    data.
  - When something goes unplanned in testing, complications can cause
    the environment that's designed to ensure deployments go well to
    become a bottleneck.
  - Deployments are risky enough that most businesses have time periods
    in which new deployments into production aren't permitted:
    open-enrollment for health insurance, between Thanksgiving and
    Christmas for e-commerce, etc.
- Without mechanism for providing exactly the same environment for
  development/testing/staging/production, it's easy for software to
  depend on something that's lacking in a different environment.
  Different, unique environments are snowflakes.
  - You change property files between dev, test, staging, and production.
  You risk having differences between environments creep across
  environments.
