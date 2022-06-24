# Cloud Native Patterns - Ch. 1, You keep using that word: Defining "cloud-native"

[Cloud Native Patterns by Cornelia
Davis](https://www.goodreads.com/book/show/36410104-cloud-native-patterns)

## Summary

- You're paying AWS because you want to focus on creating value for your
  customers, not on infrastructure concerns. AWS is responsible for
  keeping its systems up, and enabling you to keep yours functioning as
  well.
- You'd be wrong to blame AWS entirely for your outage. The applications
  you're running on a particular infrastructure can be more stable than
  the infrastructure itself.
- Netflix was able to fully recover minutes after an AWS outage on
  September 20th with redundant systems and simulated regional outages
  performed.  ![figure_1.2.png]
- In the past, change or failure is treated as an exception; Netflix and
  other large-scale internet-native companies treat change or failure as
  the rule.
- Software must also be designed to allow planned events, such as
  upgrades, to be done with no downtime.
- Continuous releases reduce risk. Early feedback allows for changes and
  adjustments.
- **Cloud-native software** meets user requirements of constant
  availability, constant evolution with frequent releases, easily
  scalable, and intelligent.
- The **cloud-native app** is where you'll write your code; the business
  logic of your software.
- **Cloud-native data** is where your state lives in your cloud-native
  software, decomposed and distributed.
- **Cloud-native interactions** is the way that the apps and data
  interact.
- Scaling out/in by adding or removing instances of apps: rewards
  keeping state out of the app, allows for recovery actions more easily,
  and offers resilience.
- A distributed data fabric is required in modern software, rather than
  a monolithic, single database. It is made up of independent,
  fit-for-purpose databases (some only provide views of data when the
  source of truth lies elsewhere). Keeping information in sync across
  the multiple databases is important.
- For apps with multiple instances, some type of routing system with
  automated retries and support for the cloud-native context.
- Not all software should be cloud-native. If the software isn't
  distributed and is rarely changing (a rice cooker's embedded
  software), if characters of cloud-native software aren't appropriate
  (*eventually consistent* for financial transactions), and if there's
  no immediate value in reewriting existing software that isn't
  cloud-native.
- Cloud-native still plays well with existing solutions, since
  cloud-native is a separation of concerns into smaller components;
  a large, existing solution can just be seen as a component to
  interface with.
- Moves to cloud-native architecture doesn't need to be done all at
  once; it took Netflix seven years, by prioritizing and refactoring
  some parts of the whole.

## Today's Application Requirements

1. Zero downtime
1. Shortened feedback cycles
1. Mobile and multidevice support
1. Internet of Things
1. Data-driven
