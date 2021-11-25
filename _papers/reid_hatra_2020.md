---
title: 'Towards making formal methods normal: meeting developers where they are'
layout: paper
authors: 
- Alastair Reid
- Luke Church
- Shaked Flur
- Sarah de Haas
- Maritza Johnson
- Maritza Johnson
- Ben Laurie
booktitle: Human Aspect of Types and Reasoning Assistants
series: HATRA '20
read: true
readings:
- 2021-11-20
---

Here we come to the work of Google's verification team. This paper
mainly discusses two topics, i.e., the necessity and obstacles of
integrating formal methods with developers' existing practices.
Further, it mentions Google's practice: a prototype for verifying Rust
programs, but lacks essential details of analyzing and solving the
problem.

Reid begins by introducing what can formal methods do for developers,
and what profits can it bring compared to testing. This topic is mentioned
much in other materials, but Reid discusses it from the perspective
of developers. Their goal is to realize a weekly cost-benefit ratio.
That means, developers can get the positive feedback within one week.
Considering the huge learning effort of the most formal methods, it is 
really an ambitious goal.

Then, Reid introduces their prototype on Rust. Surprisingly, this
paper directly gives me the answer why so many groups focus on
verifying Rust programs. I am a Rust freshman and have been pondering
over the problem for a long time. Shortly, there are three reasons. 
- **Technical** Rust's ownership type system is fit for realize formal methods
  such as reasoning.
- **Cultural** Rust is known by its safety, and Rust programmers are also
  concerned with it. Thus, they are more likely to use formal methods
  to ensure their programs be safer.
- **Community** Rust verification tools are far behind the state of C
  verification tools, so there is much to do.

Reid's prototype has three verification ways. First is to use a fuzz-tester.
Second relies on KLEE symbolic execution engine. Third is to use Galois' "Crux"
verification tool to perform model checking.

Finally, Reid talks about the obstacles in aspects of usability,
ecology and technical. They are too trivial to be all summarized.
Interestingly, Reid has mentioned the difference between Amazon's
verification workflows and Google/Facebook's. Amazon forms a
specialized team to fill the gap between verification team and
development team, while Google and Facebook plan to take formal
verification tools only in code review stage, limited by the
organization structure.

{% include links.html %}
