---
layout: post
title:  "Spanner"
date:   2015-11-3 21:00
permalink: PowerGraph
---

The PowerGraph paper explores the problem of big data graph computations.
Given the explosion of social networks, and the wide variety of problems which
can be mapped onto graph computations, this problem seems to be well worth
solving.

Of course, in all big data systems, we must find some way to partition the
data.  The PowerGraph paper observes that the naive method for data
partitioning, assigning each vertex to a separate node, causes large amounts of
cluster wide communication causing low performance.  The PowerGraph paper,
instead, assigns each edge to a separate node.  This moderately complicates the
implementation, but allows them to dramatically reduce inter-cluster
communication, increasing performance.

The key lesson I learned from this paper is that in big data processing
systems depend heavily on good data partitioning which in turn depends on
applications semantics.  One can't rely on a naive implementation do "do the
right thing" and achieve good performance.
