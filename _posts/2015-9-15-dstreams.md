---
layout: post
title:  "Discretized Streams"
date:   2015-9-15 21:00
permalink: dstream
---

The NSDI deadline is fast approaching so this one is going to be rough.

Discretized streams are an enhancement of spark that enables support for stream  
processing.  Streams are infinite sets of key value pairs, which need a series
of operations applied to them at vary low latency.

Most of the stream processing systems up to this point had relied on per-key
computation abstraction.  This, combined with the fact that various processing
elements had internal state, made fault tolerance and scale somewhat difficult.
Dstreams relied on the insight that if you grouped key values into small
batches at a regular time interval, you could process them on top of spark
resulting in a significant performance boost and giving you fault tolerance for
free.

It seems to me that in any system which does batching, there's a trade off
between latency and throughput.  I suppose this paper relies on the fact that
most of these stream use cases are eventually being consumed by humans, and
thus human time-scale latencies are sufficient.

It's a nice paper, though I suspect it's influence over the long term as a
piece of academic work will be somewhat limited.  It's a nice step on the way
to the ideal solution, but it's not clear to me that the result is fundamental.
That said, spark has so much traction behind it, even if something better comes
up, this solution still had a good chance of winning.
