## v2.4.11 2016-06-02

+ mde/master merged
+ version adjusted

## mde/master v2.4.1: 2016-05-24

+ Added LICENSE file to release package (@mde)
* Various documentation improvements (@RyanZim)
* Better line-numbers in errors (@dgofman)

## v2.4.10 2016-05-16

+ added fileExtension option to change from .ejs to anything (@BananaAcid)
+ some code cleanups (@BananaAcid)
+ fixed whitespace slurping to work with custom delimiters (@BananaAcid)

## v2.4.9 2016-05-16

+ added MarcelloDiSimone/ejs/feature/multi-views (@MarcelloDiSimone)
+ Readme updated with readFile() examples (@BananaAcid)
+ all tests work in windows (@BananaAcid)

## v2.4.8 2016-04.25

+ added hash-include-directive (`#include 'path';\n #include 'path2';`) because of scope restrictions (@BananaAcid)
* Readme updated to reflect the 3 include options (@BananaAcid)
* changed some `.apply()` calls to a more appropiate `.call()` (@BananaAcid)

## v2.4.7 2016-04-22

* thoughtless naming for renderFile() return renamed from 'html' to 'content' (@BananaAcid)

## v2.4.6 2016-04-22

+ exported delimiter initially set (@BananaAcid)
+ jsHandler, a new FileLoader content handler (@BananaAcid)
* renderFile() returns an object with {err,html}, if callback is not set (which it would not call) (@BananaAcid)
+ test added for jsHandler() and renderFile() return (@BananaAcid)

## v2.4.5-1 2016-04-22

+ feat(literal): output literal %> with %%> close #153 (Roy Miloh <rmiloh@gmail.com>) PATCH 0a2623905a494aecf970114e51144234d7467135

## v2.4.5 2016-04-22

+ fileLoader management classes added. (@BananaAcid)
+ example usage added to Readme (@BananaAcid)
+ new test cases (@BananaAcid)
* cli tool's output is to stdout now (expected behaviour) (@BananaAcid)
* cli tool can take from stdin and parse to file (@BananaAcid)
* cli tool needs --out param to trigger rendering to files (e.g. `--out ./`) (@BananaAcid)
* cli tool: removed requirement for mkdirp (@BananaAcid)

## v2.4.4 2016-04-19

* fixed exception test (@BananaAcid)
+ option codeTransformer added to load JS enhancing compilers
  (they must be able to parse the EJS debug JS, e.g. Typescript, babeljs) (@BananaAcid)
+ added a lot more tests (@BananaAcid)

## v2.4.3-3 2016-04-19

+ merged the cli tool from https://github.com/mde/ejs/commit/2c58f734c63906f00a8d8fa81fae3f2002a49b9b (@mde)
* small info changes to the cli tool (@BananaAcid)
+ npm script commands extended: run is linked to the cli tool (@BananaAcid)

## v2.4.3.2 2016-04-19

* modified include hack to fit 1efc7934223ce65e1394abd44e20046f4061d1ff / IIFE (#lvl-ctx) (@BananaAcid)
* echo as function to output strings from code HACK (@BananaAcid)

## v2.4.3.1 2016-04-19

* merge with mde/ejs/master

## v2.4.3: 2016-04-18

+ api: add es6 yield support 
  (https://github.com/yawnt/ejs/commit/4dd58539184193b670f7cfc124fd0e762e9bd1ca) (@yawnt)
+ restoring IIFE, so that vars can be minimized inside the
  with; invoking IIFE not via simple () call, but rather via .apply(this) to
  ensure correct context (from <hello@dominykas.com>)

## v2.4.2.1: 2016-04-17

+ added dgofman <dgofman@gmail.com> modifications, mainly 
  Fixed issue mde#119 (@dgofman)

## v2.4.2: 2016-04-17

+ preprocessor option, a function to proccess the content
  before EJS (@BananaAcid)
+ old style filters readded (@BananaAcid)
* Mocha (for windows): fixed most line ending issues where new lines
  are not beeing tested (@BananaAcid)

## v2.4.1: 2016-01-23

+ Strict-mode support (@mde)
+ Express 4 support (@mde)
+ Configurable localsName option (@mde)

## v2.3.4: 2015-09-04

+ Whitespace slurp tag syntax -- `<%_  _%>` (@andidev)

## v2.3.3: 2015-07-11

* Fixed false positives for old `include` preprocessor directive (@mde)

## v2.3.2: 2015-06-28

* Do not require semicolons in `<%- %>` (@TimothyGu)
* Use `__append` instead of `pushToOutput` (@dominykas)
* Cache the character-encoding function (@alubbe)
* Correctly specify execution context with opts.context (@mde)

## v2.3.1: 2015-02-22

* Stop deferring execution of `renderFile` callback, revert to sync
  execution (@mde)
+ Generated template functions are now prettier (@whitneyit)
+ Add official documentation for EJS syntax (#9) (@TimothyGu)
+ Add inline JSDoc-style documentation for public functions (#9) (@TimothyGu)
+ Add a new dynamic client-side template compilation example in
  `examples/client-compile.html` (@TimothyGu)
* Fix running on Node.js v0.8. Note that we still do not support 0.8
  officially, but if you found something that can be fixed easily please
  point it out. (#57) (@TimothyGu)
* Do not trim newlines at the end of files. This might be considered
  incompatible by some, but the new behavior is the correct one, and is
  consistent with EJS v1. (#60) (@TimothyGu)
* Readd deprecation warning for `scope` option that was removed in v2.2.4. It
  never caused any problems with Express or anything else so its removal was
  a mistake. (@TimothyGu)
* Always rethrow the error from `new Function()` (@TimothyGu)

## v2.2.4: 2015-02-01

+ Ability to customize name of the locals object with `ejs.localsName` (@mde)
+ Ability to override `resolveInclude` for include-path lookup
  (@olivierkaisin)
* Only bundle rethrow() in client scripts when compileDebug is enabled
  (@TimothyGu)
* Copy `_with` from locals object to options object (@TimothyGu)
* Removed deprecation warnings (@mde)
* Significantly increased performance (@TimothyGu)
* Defer execution for `renderFile` callback, ensure async (@TimothyGu)

## v2.2.3: 2015-01-23

* Better filtering for deprecation notice when called from Express (@mde)

## v2.2.2: 2015-01-21

* Fix handling of variable output containing semicolons (@TimothyGu)
* Fix included files caching (@TimothyGu)
* Simplified caching routine (@TimothyGu)
* Filter out deprecation warning for `renderFile` when called from
  Express (@mde)

## v2.2.1: 2015-01-19

+ 4x faster HTML escaping function, especially beneficial if you use lots
  of escaped locals (@TimothyGu)
+ Up to 4x faster compiled functions in addition to above (@TimothyGu)
+ Caching mode regression test coverage (@TimothyGu)
* Fix `//` in an expanded string (@TimothyGu)
* Fix literal mode without an end tag (@TimothyGu)
* Fix setting options to renderFile() through the legacy 3-argument interface
  (as is the case for Express.js) (@TimothyGu)
+ Added version string to exported object for use in browsers (@mde)

## v2.1.4: 2015-01-12

* Fix harmony mode (@mde)

## v2.1.3: 2015-01-11

* Fix `debug` option (@TimothyGu)
* Fix two consecutive tags together (@TimothyGu)

## v2.1.2: 2015-01-11

* Fix `scope` option handling
+ Improve testing coverage (@TimothyGu)

## v2.1.1: 2015-01-11

+ Add `_with` option to control whether or not to use `with() {}` constructs
  (@TimothyGu)
+ Improve test coverage (@mde & @TimothyGu)
+ Add a few more metadata fields to `package.json` (@TimothyGu)
- Revert hack for Etherpad Lite (@TimothyGu)
* Do not claim node < 0.10.0 support (@TimothyGu)
* Pin dependencies more loosely (@TimothyGu)
* Fix client function generation without using locals (@TimothyGu)
* Fix error case where the callback be called twice (@TimothyGu)
* Add `"use strict";` to all JS files (@TimothyGu)
* Fix absolute path inclusion (@TimothyGu) (#11)

## v2.0.8: 2015-01-06

* Fix crash on missing file

## v2.0.7: 2015-01-05

* Linting and cosmetics

## v2.0.6: 2015-01-04

* Temporary hack for Etherpad Lite. It will be removed soon.

## v2.0.5: 2015-01-04

* Fix leaking global `fn`

## v2.0.4: 2015-01-04

* Fix leaking global `includeSource`
* Update client-side instructions

## v2.0.3: 2015-01-04

+ Add Travis CI support
+ Add LICENSE file
+ Better compatibility with EJS v1 for options
+ Add `debug` option
* Fix typos in examples in README

## v2.0.2: 2015-01-03

* Use lowercase package name in `package.json`

## v2.0.1: 2015-01-02

+ Completely rewritten
+ Single custom delimiter (e.g., `?`) with `delimiter` option instead of
  `open`/`close` options
+ `include` now runtime function call instead of preprocessor directive
+ Variable-based includes now possible
+ Comment tag support (`<%#`)
* Data and options now separate params (i.e., `render(str, data, options);`)
- Removed support for filters
