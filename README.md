# rpmbuild-pipeline-test-sources

- `broken-noarch-subpackage` contains source RPM and corresponding arch-specific
  binary RPMs built on `x86_64` and `aarch64`.  The package build is buggy
  because it provides a `norpm` sub-packages with different payload on every
  architecture.

- `valid-noarch-subpackage` is similar to `broken-noarch-subpackage`, but the
  `noarch` packages are valid.
