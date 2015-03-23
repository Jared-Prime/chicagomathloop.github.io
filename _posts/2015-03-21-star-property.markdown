---
layout: post
title:  "the star property"
date:   2015-03-21 18:16:00
categories: the * ('star') property
---

# the * property

In two separate meetings, we made judicious use of what Sidney Morris, in his textbook *Topology without Tears*, calls the `*` (pronounced 'star') property. This property focuses on subsets of `R` (the set of real numbers), and we can use it to prove many important claims about the topological structure of `R` and subsets of `R`.

> A subset `S` of `R` is said to be open in the euclidean topology on `R` if it has the following property:
> (`*`) For each `x ∈ S`, there exist `a, b ∈ R` with `a < b` such that `s ∈ (a,b) ⊆ S`.

Some practice is recommended to get the hang of this definition, so let's jump right in.

## euclidean toplogy

We have `*` and want to show that `(R, T)` satisfies the axioms for a toplogogical space. As a reminder, these axioms are (restated with direct reference to `R` without any loss of generality):

1. the complete set `R` and the empty set `∅` are members of `T`
2. any union of members of `T` is also a member of `T`
3. any finite intersection of members of `T` is also a member of `T`

Recall, also, that `T` is simply a collection of subsets of `R`.

### Proof that 1 holds true for `(R,T)`

Pick any real number `x`. Subtract `1` from `x` to get `a`. Add `1` to `x` to get `b`. Convince yourself that `x` lies somewhere 'between' `a` and `b`.

```
x ∈ R
a = x - 1
b = x + 1
x ∈ (a, b)
```

Now, `(a, b)` is an open interval and a subset of `R`. This satisfies the definition of `*` precisely, namely,

```
x ∈ (a, b) ⊆ R
```

and so, by definition, `(a, b)` is open in `(R, T)`. Do this for all `x ∈ R` and we show that `R ∈ T`.

You can say that for some `y ∉ R`, there is precisely one interval `∅` where the `*` property holds; therefore `∅ ∈ R` as well.

### Proof that 2 holds true for `(R,T)`

Recall that `T` is simply a collection of sets, so we can easily choose some subcollection, call it `A`. In fact, we can make many such choices; so, each time we choose a unique subcollection of `T`, we can 'tag' it ('index' is the correct term for this), so we have `A_i`. All this means is that we can have a collection of subcollections of `T`, and we can keep track of which subcollection we're talking about using the indices.

To prove the second axiom for `(R,T)`, we can use the `*` property again on this family of indexed subcollections `{ A_i }`.

Pick any real number `x` from a set built from the union of subsets in `A_k`, which is a specific member of the family `{ A_i }`. We then have `x` as a member of the subcollection `A_k`. Now we *chose* each `A` such that `A ∈ T`. There must then be some `a` and some `b` in `R` where the statement

```
x ∈ (a,b) ⊆ A_k
```

holds true. By induction, this must hold true *in general* for the family `{ A_i }`, meaning

```
x ∈ (a,b) ⊆ A_i
```

holds true. This again is the `*` property, and so we've shown all unions of any subcollection of `T` belongs to `T`.

### Proof that 3 holds true for `(R,T)`

At this point, we have a bit of freedom -- believe it or not, things are getting easier. Pick any pair of subsets `A` and `B` from `T`. Pick some `y` from the intersection of `A` and `B`. By definition of set intersection, `y ∈ A`. Using a similar trick as above in proving the second axiom holds on `(R,T)`, we can show

```
y ∈ (a,b) ⊆ A
```

Moreover, `y ∈ B` by definition of set intersection, and so

```
y ∈ (c,d) ⊆ B
```

Almost there! If we have some number `e` larger than both `a` and `c`, and we have some number `f` smaller than both `b` and `d`; then `e < y < f`. Hence,

```
y ∈ (e,f) ⊆ A∩B
```

The intersection -- which is, after all, *any* pair of subset from `T` -- has the `*` property.

## extreme generality

The extreme generality involved in this proof caught me off gaurd the first time. But if you think about it, we need an extremely general approach to making a claim about the topological structure of the real numbers -- `R` is uncountably large! That's why the proof is so careful to pick, with as little specificity as possible, "any" real number, or "any" set from a subcollection, or "any" pair of subsets to test whether or not it has the `*` property. If we are able to make this selection with as few restrictions as possible, then the property demonstrated on that selection "carries through" to any other selection we could have made -- which is to say any and all open sets.

Topology is like that; its extreme generality allows you to make very careful determinations on the nature of the entire space at once.

## Demostrating the 'Openness' of Subsets of `R`

This follows proposition 2.2.1 from *Topology without Tears*.

> A subset `S` of `R` is open if and only if it is a union of open intervals.

This claim goes in two directions ("if and only if"); so its strength will be very useful.

### Demonstrate `S` is an open set

Assume for the proof that `S` is a union of open intervals. We construct it with the help of indices `i`, giving us

```
S = ⋃(a_i, b_i)
```

Luckily, we've already proven this above. This immediately gives us `S` as an open set.

### Demonstrate `S` is a union of open intervals

Assume for the proof that `S` is an open set. Pick some `x` from `S`. We'll use the same trick as above to select an interval `(a,b)`, so

```
x ∈ (a,b) ⊆ S
```

Be careful! The temptation here is to say, "use the `*` property and we're done". Yes, we have shown the `*` property in this case but only in this case! There has been a subtle shift in language that ( if you're really paying incredibly close attention ) should tip us off that we've *restricted* our selection of `x`. We've chosen "some" not "any" `x`, and thus we have to justify extending the `*` property generally across the set `S`.

The two following step will justify the extension for us.

#### Demonstrate all `x` is contained in some interval

Pick any `x` from `S`. Then we get `x ∈ (a,b) ⊆ S`, making us happy. This maneuver is becoming more natural for us.

#### Demonstrate all intervals contains some `x`

Pick any `x` from a union of all open intervals. Then `x` belongs to some open interval (at least one). Then `x` belongs to `S`.

### `S` is an open set

Why these extra steps? Another subtlty in language: `S = ⋃(a_i,b_i)` is a strong claim; before we may only have claimed that the relation `⊆` rather than `=` holds for `S`. ( Recall that the precise meaning of `⊆` is that the set on the left of the symbol is either equal to or a subset of the set on the right of the symbol. This is analogous to the arithmetic relation `≤` which is true when either the two numbers are equal or the number on the left is smaller. )

We demonstrate the `*` property on some number `x` of `S`, generalize it for `S`, and then generalize it for `⋃(a_i,b_i)`, giving us justification for `=` as opposed to the weaker `⊆` ( which we could have satisfied much sooner).

## What's next?

From here, we can move pretty quickly into the definition of a topological basis, a neighborhood for an element in a topological space, and many concrete examples for bases on the euclidiean topology. But let's let the approach of these proofs soak in first!
