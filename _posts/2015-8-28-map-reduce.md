---
layout: post
title:  "Map Reduce: Simplified Data Processing on Large Clusters"
date:   2015-8-28 20:00
permalink: map-reduce
---

The MapReduce paper describes a system for doing batch computations on large 
amounts (terabytes) of data  at Google.  It borrows the map/reduce semantics of
functional languages to build a programming model which makes it easy to
express distributed computations and implement them at scale.

This is a fantastic paper.  At first glance, one might think it's about
building a large scale distributed system, but I'm not sure that's really the
contribution.  At the time of writing, using large numbers of machines to
distribute computation was common (at least at Google).  The real problem
they're solving, is how to make these distributed computations easy.  They're
moving us from a world of expertly programmed bespoke algorithms, to a world
where clean standardized interfaces dramatically simplifies development and
implementation.

The solution is pretty simple.  They noticed that many distributed computations
can be expressed as a series of map and reduce operations over a list of key
value pairs.  Map operations perform a computation on each key-value producing
an intermediate result, while reduce operations combine these intermediate
results into useful information.  Programmers express their algorithms as a
series of map reduce operations, which are handed to a system that performs
the actual computation and hands back a result.

They make no attempt to argue that map and reduce are somehow fundamental to
distributed data processing.  Instead, they rather pragmatically assert that
experience shows it useful at Google.  For this reason, I'm not sure that map
and reduce themselves are the important contribution here, so much as the
recognition that by severely restricting the computation model, they both force
programmers to write parallel code, and make it easier for their system to
distribute this code, hide complexity, and scale.  This strict simplicity is
what separates MapReduce from the systems which preceded it, and, I would
argue, is the reason for its continued success.

I'm a big believer in simplicity.  By making it easy for average programmers to
build massively scalable distributed algorithms, the MapReduce paper has been
extremely influential to date.  I see no reason for their core contribution,
simplify to scale, not to continue to be important indefinitely. 
