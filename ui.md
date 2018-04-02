UI
==

- [History](#history)
- [Elm Based)(#elm-based)
- [Reflex)(#reflex)


## History

This is mostly based around my previous experience at Ambiata having to build
back _and_ front ends to a system, which was something that doesn't seem

It would probably make an interesting talk to discuss how most people when
faced with this siutation decide that having the same language on the server
is the _only_ fix (ie. javascript), which is not something we found acceptable.
However, it _did_ mean building a non-trivial, type-safe templating language.

- https://github.com/ambiata/loom
- https://github.com/ambiata/projector


## Elm Based

At Ambiata we used [Pux](https://github.com/alexmingoia/purescript-pux),
which was chosen on a very brief comparison to the far more complex looking
[halogen](https://github.com/slamdata/purescript-halogen).

I wouldn't recommend Pux again. Parly because the maintainer wasn't very active
and dropped a major rewrite on the repository without warning and no review.
Partly because Pux is a _very_ thin shim over react.js, and is fragile to
hold because of that. An example of this was trying to drop in codemirror.js
and having to thread the needle with the Pux hacks to get everythign to play
nice.

Instead it seems like [spork](https://github.com/natefaubion/purescript-spork)
might be a slightly more mature and less hacky implementation of the same ideas.
It has a way to add native DOM elements which would improve on the problems
with codemirror.js.

In general though, Elm architecture doesn't lend itself to composition.
Instead you have separate `view` and `update` functions which correspond very
tightly. It's all very simple to use, but doesn't compose.

Phil Freeman, of Purescript fame, seems to have a
[similar view](https://twitter.com/paf31/status/949851698507300864), and
released [purescript-sdom](https://github.com/paf31/purescript-sdom) as
a prototype, but I haven't looked in to it yet.


## [Reflex](https://github.com/reflex-frp/reflex-dom)

Ignore the powerful FRP behaviours, at it's core this seems like a way to
deal with updating the DOM in a slightly more controlled way.

- https://hackage.haskell.org/package/reflex-dom-0.3/docs/Reflex-Dom-Internal.html#v:GuiEnv

There are some purescript implementations which might be interesting to look
at:

- https://github.com/restaumatic/purescript-specular
  - [motivation](https://github.com/restaumatic/purescript-specular/blob/master/doc/Motivation.md)
- https://github.com/juspay/purescript-reflex-dom
