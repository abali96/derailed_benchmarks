# A Log of Changes!

## 1.4.0

- Allow configuration of `perf:ips` benchmark.
- Fix bug with `require_relative` [#142](https://github.com/schneems/derailed_benchmarks/pull/142)
- Introduce `perf:library` to profile patches to libraries (like Rails) [#135](https://github.com/schneems/derailed_benchmarks/pull/135), [#139](https://github.com/schneems/derailed_benchmarks/pull/139), [#140](https://github.com/schneems/derailed_benchmarks/pull/140), [#141](https://github.com/schneems/derailed_benchmarks/pull/141)

## 1.3.6

- `require_relative` is now measured [commit](https://github.com/schneems/derailed_benchmarks/commit/af11bcc46a4fa24f79e4897a51034927a56e077e)
- Fix bug preventing a specific Rails 6 file from being loaded (https://github.com/schneems/derailed_benchmarks/pull/134)
- `exit(1)` is called instead of raise (https://github.com/schneems/derailed_benchmarks/pull/127)

## [1.3.5]

- Output of `test` now emits the word "derailed" for easier grepping.
- Fix "already initialized constant" warning

## [1.3.4]

- Allow for "warming up tasks" via WARM_COUNT env var #119

## [1.3.3]

- Make all paths added to $LOAD_PATH absolute instead of relative to allow for use with apps that use bootsnap.

## [1.3.2]

- Allow for use with Rack 11.


## [1.3.1]

- Allow for use with Rack 11.


## [1.3.0] - 2015-01-07

- Allow environment variable to skip Active Record setup.
- Allow Rack 2 to work with Derailed.

## [1.1.3] - 2015-10-15

- Update docs

## [1.1.2] - 2015-10-05

- Added ability to use TEST_COUNT environment variable with `perf:heap`.

## [1.1.1] - 2015-10-01

- Added ability to create a heap dump `perf:heap`.

## [1.1.0] - 2015-09-09

- Set custom auth user using a lambda in perf.rake
- Changed `perf:ram_over_time` changed to `perf:mem_over_time`
- Fixed gem warnings

## [1.0.1] - 2015-06-20

- `bundle:mem` and similar tasks now keep track of duplicate requires and display them along side of memory requirements. This makes it easier to identify where components are used by multiple libraries
- Add rake to gemspec which gets rid of `Unresolved specs during Gem::Specification.reset:` warning
- Outputs of memory are now done in [mebibytes](https://en.wikipedia.org/wiki/Mebibyte), a more accurate unit for the value we're measuring (hint: it's what you think MB is).

## [1.0.0] - 2015-05-14

- Added `derailed` command line utility. Can be used with just a Gemfile using command `$ derailed bundle:mem` and `$ derailed bundle:objects`. All existing Rake tasks can now be called with `$ derailed exec` such as `$ derailed exec perf:mem`.
- Changed memory_profiler task to be `perf:objects` instead of `perf:mem`.
- Changed boot time memory measurement to `perf:mem` instead of `perf:require_bench`
- Released seperate [derailed](https://github.com/schneems/derailed) gem that is a wrapper for this gem. I.e. installing that gem installs this one. Easier to remember, less words to type. Also means there's no colision using the `derailed` namespace for executables inside of the `derailed_benchmarks`.

## [0.0.0] - 2014-08-15

- Initial release
