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
booktitle: Proceedings of the ACM SIGOPS 28th Symposium on Operating Systems Principles
series: SOSP '21
read: true
readings:
- 2021-11-18
---

This is the third formal method material published by Amazon as I know (See technical report '14 and ICSE-SEIP '20 for the others). It is a remarkable practice to apply formal methods in large-scale system development, and wins the best paper award.

The practice is performed on Amazon's new K-V storage system ShardStore, which is the backend of S3 object storage service, and designed with some properties such as crash consistency. 

{% include links.html %}