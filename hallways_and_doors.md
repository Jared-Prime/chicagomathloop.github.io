# Hallways and Doors

## Imagine

Say each set of a collection of subsets is a hallway; the elements of the set are doors. (We have an immediate difficulty which we amend by saying that, in our universe, there are no hallways without doors. The ur-element is `$\emtyset$`.)

Conveniently, the doors are distinct and each has a unique color.

- `$\{red, blue, green\}$` is a subset representing a hallway with a red door, a blue door, and a green door
- `$\{red, blue\}$` is another subset representing hallway with *the same* red door and *the same* blue door as in the first hallway
- `$\{green\}$` is a third subset representing hallway with *the same* green door as in the first hallway

You'll probably have little trouble imagining hallways with the same door leading into one another. Keep hold of this instinct for just a bit (but not too firm a hold...)

When we apply the `$\cup$` or "set union" operation to these subsets, we say we posit a hallway consisting only of doors present in the each of the "unioned" hallways. For instance `$\{red, blue\} \cup \{green\}$` posits a hallway `$\{red, blue, green\}$`. Do this as many times as you like with as many hallways as you like contained in our collection.

When we apply the `$\cap$` or "set intersection" operation to these subsets, we say we posit a hallway consisting only of doors present in all of the "intersected" hallways. For instance `$\{red, blue\} \cap \{red, blue, green\}$` posits a hallway `$\{red, blue\}`. Interestingly, and conveniently, `$\{red, blue\} \cap \{green\}$` posits no hallway or `$\emptyset$`.

## Enter

Let us enter this space we have just imagined. We may enter either the first hallway `$\{red, blue, green\}$` or we may stay noplace `$\emptyset$`. You can always choose to stay out or to go nowhere, and this fact should indicate that some of our natural, physical instincts will be pushed into higher abstractions. But don't worry. So long as we've imagined this collection of hallways appropriately, we can get around just fine.

Say we start in the first hallway: `$\{red, blue, green\}$`

### Explore

Enter the red door. You are in a hallway with a red door and a blue door: `$\{red, blue\}`.

Enter the blue door. You are back in the hallway where you started: `$\{red, blue, green\}$`.

Enter the blue door again. You are back in the previous hallway with a red and a blue door: `$\{red, blue\}`. So far, so good.

Enter the red door. You are back in the hallway where you started: `$\{red, blue, green\}$`.

Enter the green door. You are in a closet, ie. a smallish "hallway" with only a green door leading back `$\{green\}$`.

Enter the green door again. You are back in the hallway where you started: `$\{red, blue, green\}$`.

Everything seems quite natural; keep exploring if you wish else you may "exit" by going nowhere: `$\emptyset$`.

## Where were we?

We have not visited the Matrix. We have visited a topology; this collection of hallways we've explored satisfies three axioms:

- our "starting points" `$\{red, blue, green\}$` and `$\emptyset$` are available to explore
- any arbitary union of hallways in our collection is available to explore
- each intersetcion of hallways in our collection is available to explore

All the "movements" we've taken to explore have been rather natural. But we can explore more fantastic spaces.