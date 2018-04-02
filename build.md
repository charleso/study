Build
=====

- [Nix](#nix)
- [Annex](#annex)


## Nix


I haven't used Nix in anger yet, which is something I want to fix, but it's
tricky given its closed-world nature, which means I would always be on my own
and going against the grain of my team/company.


### [One Build Tool](https://bitbucket.org/cofarrell/one-build-tool)

This was my own rant about the current state of build tools.
Looking back I know now that missed the mark on the "cheating" section.
This is not really related to build tools, just dependency resolution.
I now believe something like [annex](#annex) might be the ultimate solution
there.


### Dev-loop

Nix is certainly better at dealing with building at the _package_ level,
rather than the module level. I would have thought that a useful shim that
launches `ghci` with the right arguments would get you most of the way there
but I suspect it's more problematic than that given this kind of post:

- https://www.tweag.io/posts/2018-03-15-bazel-nix.html

I'll have to use Nix in anger to actually find out I suspect.


## [Annex](https://www.youtube.com/watch?v=JjYAnBhF2JU)

It feels like all the discussion around version bounds and PVP are all trying
make the best of an impossible situation. You just don't have enough
information at checkin time to make any decisions about what dependencies
make sense for a project. That happens much when it's built/tested/deployed/etc.
