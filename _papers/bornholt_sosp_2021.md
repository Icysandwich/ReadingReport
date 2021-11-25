---
title: Using lightweight formal methods to validate a key-value storage node in Amazon S3
layout: paper
authors: 
- James Bornholt
- Rajeev Joshi
- Vytautas Astrauskas
- Brendan Cully
- Bernhard Kragl
- Seth Markle
- Kyle Sauri
- Drew Schleit
- Grant Slatton
- Serdar Tasiran
- Jacob VanGeffen
- Andrew Warfield
file: sosp21-bornholt.pdf
booktitle: Symposium on Operating Systems Principles
series: SOSP '21
read: true
readings:
- 2021-11-18
---

This is the third formal method material published by Amazon as I know
(See technical report '14 and ICSE-SEIP '20 for the others). It is a
remarkable practice to apply formal methods in the large-scale system
development, and wins the best paper award.

The practice is performed on Amazon's new K-V storage system
ShardStore, which is the backend of S3 object storage service, and
designed with some properties such as crash consistency. 

For me there are two things that mostly interested me: the
establishment of the reference models and the decomposition of the
correctness properties.

- **Reference models.** Unlike the former practices that manually
  writing formal specifications in formal languages such as TLA+ for
  systems, the authors directly developed an executable specification
  in Rust (ShardStore is also developed in Rust). Undoubtly, this
  decision can help reduce the efforts for developers to learn other
  formal languages, and take usage of the specifications in other
  scenarios, e.g., mocking APIs in testing. Possibly using executable
  specifications rather than the specific formal languages will be a
  trend that applying formal methods in the development (I called it
  formal engineering).

- **Property decomposition.** The core of verification is properties.
  What property to check defines what bugs can be found and the way
  to verify. This paper focuses on the durability and consistency.
  The authors decompose the property into three parts due to non-determinism:
  - For sequential crash-free executions, they directly check whether
    the specification execution results maps the implementation executions
    by property-based testing.
  - For sequential crashing executions, they use dependency analysis to
    check crash consistency like other works usually do.
  - For concurrent crash-free executions, they use a Rust model checker
    to verify the properties.
  Last, they claim that the scenario of concurrent crashing executions is too
  hard to check. It is reasonable.

The verification teams in big companies, e.g., Amazon, Google and Facebook have
made several progresses in these two years, but still far away to make formal
verification be a usual step in software development. How to make it more practical
and more lightweight is always an important topic.

{% include links.html %}