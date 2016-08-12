[![Latest release](http://img.shields.io/bower/v/purescript-equatable-functions.svg)](https://github.com/rgrempel/purescript-equatable-functions/releases)
[![Dependency Status](https://www.versioneye.com/user/projects/57007272fcd19a0051853c1d/badge.svg?style=flat)](https://www.versioneye.com/user/projects/57007272fcd19a0051853c1d)
[![Build Status](https://travis-ci.org/rgrempel/purescript-equatable-functions.svg?branch=master)](https://travis-ci.org/rgrempel/purescript-equatable-functions)

# purescript-equatable-functions

It would sometimes be useful to be able to compare two functions in order to
determine whether they are equal. This is famously impossible, in the general
case, in the sense that there is no general algorithm to determine whether one
function is equivalent to another function.

Now, when faced with the desire to test whether two functions are equal, the
right answer is often: don't do that! Instead, refactor your code so that
you the things you are comparing are just data.

However, there are some patterns in which you treat a function as part of a
larger data type, and in those cases you may want to be able to determine
whether two values of that type are equal. Hence, you want to determine whether
two functions are equal.

So, how can we accommodate that, to some degree? This module provides a kind
of "wrapper" type -- `EqFunc` -- which can be tested for equality. The typical
life-cycle is:

* Construct an `EqFunc` from a regular function.
* Possibly manipulate the `EqFunc` or combine it with other `EqFunc`s.
* Test the `EqFunc` for equality with another `EqFunc`.
* Use `runEF` (and friends) to turn it back into a function.

The manipulation of an `EqFunc` includes things such as composition, partial
application, currying, uncurrying, and flipping -- all preserving equality
with another `EqFunc` which has been built in an eqivalent manner.

## Installation

Try `bower install purescript-equatable-functions`

## Development

Try something like:

    git clone https://github.com/rgrempel/purescript-equatable-functions
    bower install
    pulp test

## API

Documentation for the API can be found on
[Pursuit](https://pursuit.purescript.org/packages/purescript-equatable-functions).
Or, if you are already looking at Pursuit, then below ...

