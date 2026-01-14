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

* The `gather-rpms.tar.gz` contains basic buildroots for real Fedora build
  of `at`. It was produced basically by running
  `mock -r fedora-42-x86_64 --calculate-build-dependencies at-3.2.5-17.fc42.src.rpm`
  and regular build after that. Note, that x86_64 mock config was altered to not
  use mirrors and both ``buildroot_lock.json`` were run through substition of urls
  from ``latest`` repo symlink to final ``packages``, so it remains stable for future.

# git-repos

Tared git repositories.

* `rpmbuild-pipeline-git.tar.gz` is an early shape of the main upstream repo,
  needed for `patch-git` test-case.
