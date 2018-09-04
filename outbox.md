Outbox
======

A stream of notes from things I have watched/read.


## Development Metrics You Should Use But Don't

- https://www.infoq.com/presentations/metrics-visualize-team-reliability

Tools to visualize a team’s reliability and variability of delivery using the data already collected..

## SBT Source Builds (sub-project)

- https://github.com/sbt/sbt/issues/2901
- https://stackoverflow.com/questions/20083564/can-multi-projects-from-git-be-used-as-sbt-dependencies
- http://blog.xebia.com/git-subproject-compile-time-dependencies-in-sbt/

Turns out you can't use `ProjectRef` for the `.` root project. Any other project is fine.
There's almost certainly a way to fix this behaviour, but I couldn't work it out.

## [Immutability Changes Everything](https://vimeo.com/52831373)

- Date: 31-05-2018
- Author: Pat Helland

## [CRDTs and the Quest for Distributed Consistency](https://www.infoq.com/presentations/crdt-distributed-consistency)

- Date: 31-05-2018
- Author: Martin Kleppmann

## [Developing Expertise](https://www.infoq.com/presentations/Developing-Expertise-Dave-Thomas)

- Date: 31-05-2018

## Distributed Code Review

Partly inspired by the Jane Street blog post:

https://blog.janestreet.com/putting-the-i-back-in-ide-towards-a-github-explorer/

I've been thinking about this (again) since I left Ambiata.
Just on a whim I did a random search and found this project from 2 years back:

https://github.com/google/git-appraise

Pros:

- Simple
- Distributed
- Supports fetching from Github
- Has (read only) local web support

The big hurdle for me is switching the team over, which is always tricky.
Having the ability to gradually migrate would be nice (if not essential).
I'm still not sure how (or _if_ it's even possible) to implement a 1:1
sync.


## Nix Stuffing Around

I couldn't mount a `/nix` volume without errors from the installer and
eventually I gave up. I ended up using this:

- http://datakurre.pandala.org/2015/11/nix-in-docker-best-of-both-worlds.html
- https://gist.github.com/datakurre/a5d95794ce73c28f6d2f

I'm trying to learn Nix a little better this time around.

- https://github.com/shajra/example-nix
- https://github.com/Gabriel439/haskell-nix

I ended up install `ghcid` with:

```sh
nix-env -f '<nixpkg>' -iA 'haskellPackages.ghcid'
```

## [Paginators are Mealy Machines in disguise](http://www.alfredodinapoli.com/posts/2016-09-10-paginators-are-mealy-machines-in-disguise.html)

Date: 13-04-2017

Getting ready for a potential talk.
I'm just trying to work out if there's a (useful) unification of a
simple backwards/forwards pager vs one with offsets for direct access.
Or would you just have different paging data types.
 
- https://github.com/ekmett/machines/blob/master/src/Data/Machine/Mealy.hs
- https://www.reddit.com/r/haskell/comments/5247w2/paginators_are_mealy_machines_in_disguise/
- http://conway.rutgers.edu/~ccshan/wiki/blog/posts/WalkZip3/


## [Incrementally Improving The DOM](http://blog.functorial.com/posts/2018-04-08-Incrementally-Improving-The-DOM.html)

Date: 12-04-2017

Very interesting idea about only computing and applying differences
to the DOM.

I'm not quite sure how it would handle interacting with an unsafe world
(ie CodeMirror). I think you could probably replace the [element text]
(https://github.com/paf31/purescript-purview/blob/7031081163f0bd6c131099b8bbcfc38af51579d5/src/Purview.purs#L50)
value with a DOM node for those cases. I'm not sure though.


## [GitPrime](https://www.gitprime.com/product/)

Date: 02-04-2017

I listened to a podcast on
[Measuring Software Engineering Productivity](http://www.se-radio.net/2018/02/se-radio-episode-317-travis-kimmel-on-measuring-software-engineering-productivity/)
which was with [Travis Kimmel](https://twitter.com/traviskimmel) about GitPrime.

It seemed like the emphasis was on using metrics to help the engineering team,
rather than a way for the HR department to harass people. Any insights gained
would then be communicated indirectly via the engineering manager to the rest
of the management team.

There was a good section on the tradeoffs when making a small feature change,
like changing a button colour, which results in a developer doing a refactor.
GitPrime can provide metrics that can highlight this to the team lead and
can help with starting a discussion about the best way to tackle the change.


## https://www.infoq.com/presentations/facebook-stream-processing

- Puma for stream
- Looking to build a unified


## https://www.infoq.com/presentations/serverless-security-2017

- Shows a few places where using unsafe JS libraries lets you access parts of a lambda container


## https://www.infoq.com/presentations/microservices-managing-data

- Good talk about why and how do deal with data with microservices
- Converting from monolith to microservices
- Don't start with microservices, there is a cost
- How do we do the following with microservices?
  - Shared Data
    - Events
    - Only _one_ canonical service still
  - Joins
    - Materialize views, listen to events in different service and aggregate what you need
  - Transactions
    - Sagas (workflows)


## https://www.infoq.com/presentations/agile-manifesto-principles-leader

- "Preserve dignity at all costs" @ 18:00


## https://www.infoq.com/presentations/http-http2-spdy-quic

- Good intro to SPDY -> HTTP/2 -> Quick
- Speed of light is a thing
- Roundtrips are the devil
- SPDY does multiplexing which is great for roundtrips
- _Everything_ has to be built on UDP and TCP, otherwise have to deal with hardware across the world
- Quic is built on UDP
- Quic is better than HTTP/2 because it doesn't have "Head of line blocking" which causes issues on unreliable networks (eg. mobile)
- Quic is being adopted by IETF which is great


## https://www.infoq.com/presentations/functional-performance

- Caching and hardware 101 (good intro)
- Universal scalability law (more accurate than Amdahl's law which didn't consider consensus)
- Pure FP DS are bad for hardware affinity - lots of pointer chasing (ie. link lists)
- Monotonic increasing integers are great for making things performance and reliable
- Borrows ideas from CRDTs
