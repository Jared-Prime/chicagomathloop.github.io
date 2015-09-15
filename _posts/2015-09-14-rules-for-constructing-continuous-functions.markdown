---
layout: post
title: "rules for constructing continuous functions"
date: 2015-09-12 00:00:00
preview: "following Munkres' Topology, Theorem 18.2"
---

There are six rules for building continuous functions in topology; these are generalizable from the typical constructions found in analysis. Together, they comprise a handy theorem for using whenever given the task of mapping one topological space into (an) other(s).

## Constant Function

> If `f :: X -> Y` maps all of `X` into the single point `y0 :: Y`, then `f` is continuous.

For example, a straight horizontal line takes every point on the bottom edge of your notebook (call this the "x coordinate") to a single point on the left/right edge of your notebook (call this the "y coordinate"). Since we define this for *every* x coordinate, at no point are there "breaks" in the line -- eg. the line is continuous.

## Inclusion

> If `A :: X`, the inclusion function `j :: A -> X` is continuous.

I'm using bastardized notation in the conditional clause above, treating `A :: X` to mean that `A` is a subspace of `X`. Imagine a collection of coins. Some are silver, some are gold, some are aluminum. The aluminum coins, for example, are a subset `A` of the larger collection `X`; endow the larger collection with a topology -- the discrete topology will do well for this example. Then we can construct a subspace with `A` using the standard method.

Now, the inclusion function simply says, given an open set of `X`, we can take an inverse map back into an open set of `A`; colloquially, we can get back to where we started by taking the same steps. Try this out a few times (and perhaps try an refine my ad-hoc example here!)

## Composite

> If `f :: X -> Y` and `g :: Y -> Z` are both continuous, then the map `f . g :: X -> Z` is continuous.

This ought to be a bit more familiar; in essence, we can chain continuous maps together and retain our continuity property from end-to-end: each open set of `Z` can be traced all the way back through the chain to an open set of `X`.


## Domain Restriction

> If `f :: X -> Y` is continuous, and if `A :: X`, then `f :: A -> Y` is continuous.

Let't take a space described in an earlier example: a map (`f`) from a straight horizontal line on the bottom edge of your notebook (`X`) to some point(s) (`Y`) on the left edge of your notebook. If we take a subspace `A :: X`, we're "restricting" our straight horizaontal line on the bottom edge to a portion of that bottom edge. The mapping from that restricted portion is continuous as before.

## Range Restriction or Expansion

> Let `f :: X -> Y` be continuous. If `Z :: Y` and `Z` contains the image set `map f X`, then the function `g :: X -> Z` obtained by restricting the range of `f` is continuous. If `Y :: Z`, then the function `h :: X -> Z` obtained by expanding the range of `f` is continuous.

Here, we have a bit of a trickier task. Let's make sure we have some terminology clear:

- an image set is the (sub)set of `Y` obtained by taking the map `f` from `X`

Place your fingertips together. Let your left fingertips represent the space `X`; let your right fingertips represent the space `Y`. The mapping then is just the proposition "left finger `x :: X` touches right finger `y :: Y`". (Formally, we would need to build some kind of index set to keep track of which finger is which in order to make this fully generalizable.)

To restrict the image set, take away two or more right hand fingers. These fingers you take away are now closed from the remaining subspace. The fingers which remain are open; now notice that the inverse map from each open set ("finger") in the image ("right hand") is open in the domain ("right hand").

To expand the image set, put one right hand finger back. These fingers you add back are open in the image set, and they have an inverse map back to an open set in the domain.

Again, try it out for yourself, and see if you can find cleaner example.

## Local Formulation

> The map `f :: X -> Y` is continuous if `X` can be written as the union of open sets `U` such that `map f U` is continuous for each `U`.

This is actually easier than it seems. All we need is a map `f` known to be continuous. If we remake its domain `X` using any of its open sets, then we can show that the inverse map from the image gets back to some open set of `X`.