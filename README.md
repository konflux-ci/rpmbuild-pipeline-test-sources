# rpmbuild-pipeline-test-sources

* The `broken-noarch-subpackage` directory contains an SRPM and the
  corresponding architecture-specific binary RPMs built on `x86_64` and
  `aarch64`.  These package builds are considered invalid by `check_noarch.py`
  because they provide two `noarch` subpackages (one for each architecture) with
  differing file permissions on the included script.

* The `valid-noarch-subpackage` subdirectory is similar to
  `broken-noarch-subpackage`, but the `noarch` subpackages are valid.  Even
  though the script provided on both architectures still differs (different
  content), the checker ignores the MD5 sum and file sizes and considers the
  builds valid.
