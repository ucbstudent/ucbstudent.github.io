---
layout: post
title:  "The Dataflow Model"
date:   2015-9-15 20:30
permalink: dataflow
---

This is a somewhat rough pre-NSDI-deadline post.  Please excuse the
brevity.

I have very little to say about this paper.  It seems nice enough, but isn't
particularly interesting.  The basic idea here is that they propose a model for
data-processing which is a generalization of both batch and stream processing
systems.  Given this model, they show how you can easily window the data based
on ones needs, and perform computations on these windows, independent of the
underlying implementation.

Again, this seems like a nice enough model, but it's just that -- a model.  The
paper would me much more interesting/impactful if they actually built and
evaluated the thing.  Perhaps they have an implementation internally that
they're not telling us about, but I'm not going to adore a paper just cause
Google promises it's cool.


