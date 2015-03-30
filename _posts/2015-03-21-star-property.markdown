---
layout: post
title:  "the star property"
date:   2015-03-21 18:16:00
categories: the * ('star') property
---

# the * property

In two separate meetings, we made judicious use of what Sidney Morris, in his textbook *Topology without Tears*, calls the `*` (pronounced 'star') property. This property focuses on subsets of `R` (the set of real numbers), and we can use it to prove many important claims about the topological structure of `R` and subsets of `R`.

> A subset `$S \subset \mathbb{R}$` is said to be open in the euclidean topology on `$\mathbb{R}$` if it has the following property:
> (`*`) For each `$x \in S$`, there exist `$a, b \in \mathbb{R}$` with `$a < b$` such that `$s \in (a,b) \subseteq S$`.

Some practice is recommended to get the hang of this definition, so let's jump right in.

## euclidean toplogy

We have `*` and want to show that `$(\mathbb{R}, \tau)$` satisfies the axioms for a toplogogical space. As a reminder, these axioms are (restated with direct reference to `$\mathbb{R}$` without any loss of generality):

1. the complete set `$\mathbb{R}$` and the empty set `$\emptyset$` are members of `$\tau$`
2. any union of members of `$\tau$` is also a member of `$\tau$`
3. any finite intersection of members of `$\tau$` is also a member of `$\tau$`

Recall, also, that `$\tau$` is simply a collection of subsets of `$\mathbb{R}$`.

### Proof that 1 holds true for `$(\mathbb{R},\tau)$`

Pick any real number `x`. Subtract `1` from `x` to get `a`. Add `1` to `x` to get `b`. Convince yourself that `x` lies somewhere 'between' `a` and `b`.

<div>$$
  x \in \mathbb{R}\\
  a = x - 1\\
  b = x + 1\\
  x \in (a, b)
$$</div>

Now, `$(a, b)$` is an open interval and a subset of `$\mathbb{R}$`. This satisfies the definition of `*` precisely, namely,

<div>$$
  x \in (a, b) \subseteq \mathbb{R}
$$</div>

and so, by definition, `$(a, b)$` is open in `$(\mathbb{R}, \tau)$`. Do this for all `$x \in \mathbb{R}$` and we show that `$\mathbb{R} \in \tau$`.

You can say that for some `$y \notin \mathbb{R}$`, there is precisely one interval `$\emptyset$` where the `*` property holds; therefore `$\emptyset \in \mathbb{R}$` as well.

### Proof that 2 holds true for `$(\mathbb{R},\tau)$`

Recall that `$\tau$` is simply a collection of sets, so we can easily choose some subcollection, call it `A`. In fact, we can make many such choices; so, each time we choose a unique subcollection of `$\tau$`, we can 'tag' it ('index' is the correct term for this), so we have `$A_i$`. All this means is that we can have a collection of subcollections of `$\tau$`, and we can keep track of which subcollection we're talking about using the indices.

To prove the second axiom for `$(\mathbb{R},T)$`, we can use the `*` property again on this family of indexed subcollections `$\{ A_i \}$`.

Pick any real number `x` from a set built from the union of subsets in `$A_k$`, which is a specific member of the family `$\{ A_i \}$`. We then have `x` as a member of the subcollection `A_k`. Now we *chose* each `A` such that `$A \in T$`. There must then be some `$a,b \in \mathbb{R}$` where the statement

<div>$$
x \in (a,b) \subseteq A_k
$$</div>

holds true. By induction, this must hold true *in general* for the family `{ A_i }`, meaning

<div>$$
x \in (a,b) \subseteq A_i
$$</div>

holds true. This again is the `*` property, and so we've shown all unions of any subcollection of `$\tau$` belongs to `$\tau$`.

### Proof that 3 holds true for `$(\mathbb{R},\tau)$`

At this point, we have a bit of freedom -- believe it or not, things are getting easier. Pick any pair of subsets `$A, B \in \tau$`. Pick some `y` from the intersection of `A` and `B`: `$y \in A \cap B$`. By definition of set intersection, `$y \in A$`. Using a similar trick as above in proving the second axiom holds on `$(\mathbb{R},\tau)$`, we can show

<div>$$
y \in (a,b) \subseteq A
</div>

Moreover, `y ∈ B` by definition of set intersection, and so

<div>$$
y \in (c,d) \subseteq B
</div>

Almost there! If we have some number `e` larger than both `a` and `c`, and we have some number `f` smaller than both `b` and `d`; then `$e < y < f$`. Hence,

<div>$$
y \in (e,f) \subseteq A \cap B
</div>

The intersection -- which is, after all, *any* pair of subset from `$\tau$` -- has the `*` property.

## extreme generality

The extreme generality involved in this proof caught me off gaurd the first time. But if you think about it, we need an extremely general approach to making a claim about the topological structure of the real numbers -- `\mathbb{R}` is uncountably large! That's why the proof is so careful to pick, with as little specificity as possible, "any" real number, or "any" set from a subcollection, or "any" pair of subsets to test whether or not it has the `*` property. If we are able to make this selection with as few restrictions as possible, then the property demonstrated on that selection "carries through" to any other selection we could have made -- which is to say any and all open sets.

Topology is like that; its extreme generality allows you to make very careful determinations on the nature of the entire space at once.

## Demostrating the 'Openness' of Subsets of `$\mathbb{R}$`

This follows proposition 2.2.1 from *Topology without Tears*.

> A subset `$S \subset \mathbb{R}$` is open if and only if it is a union of open intervals.

This claim goes in two directions ("if and only if"); so its strength will be very useful.

### Demonstrate `S` is an open set

Assume for the proof that `S` is a union of open intervals. We construct it with the help of indices `i`, giving us

<div>$$
S = \cap(a_i, b_i)
$$</div>

Luckily, we've already proven this above. This immediately gives us `S` as an open set.

### Demonstrate `S` is a union of open intervals

Assume for the proof that `S` is an open set. Pick some `x` from `S`. We'll use the same trick as above to select an interval `(a,b)`, so

<div>$$
x \in (a,b) \subseteq S
$$</div>

Be careful! The temptation here is to say, "use the `*` property and we're done". Yes, we have shown the `*` property in this case but only in this case! There has been a subtle shift in language that ( if you're really paying incredibly close attention ) should tip us off that we've *restricted* our selection of `x`. We've chosen "some" not "any" `x`, and thus we have to justify extending the `*` property generally across the set `S`.

The two following step will justify the extension for us.

#### Demonstrate all `x` is contained in some interval

Pick any `x` from `S`. Then we get `$x \in (a,b) \subseteq S$`, making us happy. This maneuver is becoming more natural for us.

#### Demonstrate all intervals contains some `x`

Pick any `x` from a union of all open intervals. Then `x` belongs to some open interval (at least one). Then `x` belongs to `S`.

### `S` is an open set

Why these extra steps? Another subtlty in language: `$S = \cup(a_i,b_i)$` is a strong claim; before we may only have claimed that the relation `⊆` rather than `=` holds for `S`. ( Recall that the precise meaning of `⊆` is that the set on the left of the symbol is either equal to or a subset of the set on the right of the symbol. This is analogous to the arithmetic relation `≤` which is true when either the two numbers are equal or the number on the left is smaller. )

We demonstrate the `*` property on some number `x` of `S`, generalize it for `S`, and then generalize it for `$\cup(a_i,b_i)$`, giving us justification for `=` as opposed to the weaker `$\subseteq$` ( which we could have satisfied much sooner).

## What's next?

From here, we can move pretty quickly into the definition of a topological basis, a neighborhood for an element in a topological space, and many concrete examples for bases on the euclidiean topology. But let's let the approach of these proofs soak in first!
