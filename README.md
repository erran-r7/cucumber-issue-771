# Reproduction for [#771](https://github.com/cucumber/cucumber/issues/771)
An example use case that reproduces cucumber/cucumber#771. The file `nested.feature` has valid Gherkin while the file `buckets.feature` is empty.

The following usages of cucumber fail with or without the `--tags` option. These all load the empty file [features/api/buckets.feature](features/api/buckets.feature).

## Failing
* `cucumber`
* `cucumber --tags @pry`
* `cucumber features/api/`
* `cucumber features/api/buckets.feature`

## Passing
* `cucumber --exclude features/api/buckets.feature`
* `cucumber --exclude features/subdirectory/nested.feature`