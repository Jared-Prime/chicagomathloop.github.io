---
layout: post
title:  "Meeting Recap: Introduction to Topology"
date:   2015-01-15 20:30:00
categories: meeting-recap topology
---

We had a great first meeting discussing the fundamental concepts of topology. We covered:

- the composition of a topology
- rules for construction
- extended rules for determining "openness" and "closedness" properties

The primary text we are using at this stage is [*Topology without Tears*](http://topologywithouttears.net) by Sidney Morris.

## The Composition of a Topology

A topological space `(X, T)` consists of:

- a set, called `X`
- a collection of subsets of `X`, called `T`

Much of the time, we worked with a very simple finite set of letters `{a,b,c,d,e,f}` and various topologies on that set. This gave us a good sample to work with, and we added to or removed from this simple set as necessary to find relevant examples.

## Rules for Construction

We covered the three rules for qualifying `(X, T)` as a valid topological space:

1. Both the base set `X` and the empty set `0` are members of `T`
2. Any arbitrary union of the members of `T` are also members of `T`
3. Any arbitrary, finite intersection of the members of `T` are also members of `T`

For illustration, we could take a smaller space

    X := {a,b}
    T := {X, 0, {a}}

And enumerate all possible unions and intersections:

    X + 0 = 0 + X = X
    X * 0 = 0 * X = 0
    X + {a} = {a} + X = X
    0 + {a} = {a} + 0 = {a}
    X * {a} = {a} * X = {a}
    0 * {a} = {a} * 0 = 0

Verify that all the resulting sets are members of `T`. We did a number of exercises to illustrate these rules.

We discussed briefly that the use of an infinite set, such as the natural numbers `N`, makes this exhaustive enumeration impossible. We also discussed the importance that the intersection is done on finite subsets, but left the details as to why for a later session.

## Extended Rules

We can "extend" these rules with observations about open and closed sets. (I'm abusing the term "extend" here -- this is *not* a logical extension, but more a "decoration" of the core description of a topology.)

### Some Classifications: Open, Closed, and Clopen

#### Open Sets
A subset of `X` is considered "open" if it can be formed by a union of members of `T`. A similar statement is: a member of `T` is called "open".

    X := {a,b}
    T := {X, 0, {a}}

    X, 0, and {a} are all "open"

#### Closed Sets
A complement of an open set is closed; this is written `X \ U` where `U` is open.

    X := {a,b}
    T := {X, 0, {a}}

    X \ {a} = {b} is "closed"

#### Clopen Sets
A necessary feature of topology is that some open sets are also closed sets; we call these "clopen" sets.

    X := {a,b}
    T := {X, 0, {a}}

    X is "open"
    X \ 0 = X is "closed"

Therefore X is both "open" and "closed", eg. "clopen"

We can say "clopenness" is a necessity since both `X` and `0` are both "open" and "closed" according to our definitions, so we have to consider, given our rules for constructing a topology, that there may be a variety of such "clopen" sets.

### Extended Rules for Open Sets
Using the definitions above, we can state that open sets are:

1. `X` and `0`
2. the union of any open sets
3. the intersection of any finite collection of open sets

Notice the similarity to our initial rules for a topology.

### Extended Rules for Closed Sets
We can also state that the closed sets are:

1. `X` and `0`
2. the intersection of any closed sets
3. the union of any finite collection of closed sets

Notice that these definitions are complementary to the extended rules for open sets.

We did a number of examples to illustrate "openness", "closedness", and "clopenness".

## Wrap Up
We felt pretty good with this content, and the exercises brough us to the same level in familiarity as a group. We also accomplished our goal of covering the meat of *Topology without Tears*, chapter 1, which was the source text for discussion and for exercises.

Peppered throughout the meeting were some classical examples of "why topology":

- comparing a coffee cup with a donut

![morphism](/images/Mug_and_Torus_morph.gif)

- wrapping a curve around the Cartesian plane with the origin removed

![homology](/images/homology.png)

- and mention of [contemporary uses](http://research.microsoft.com/apps/video/default.aspx?id=131742) of topology within large dataset analysis.

## Thank You

Thanks for everyone for attending. If we missed each other, I hope to see you [next time](https://meetup.com/Chicago-Mathematics-Loop).

-- [Jared](https://twitter.com/haiqus)
