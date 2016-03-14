Release Process
===

Branches
---

Usually each bundle should have two active branches:

 - `1.x` - current major version
 - `master` - next major version

The most important here is a `1.x` branch where current stable version is developed.
It can receive bugfixes and new features in a backwards-compatible manner.

`master` contains code for next major version. It may receive breaking changes.

Old stable version (e.g., `0.x`; not listed) receives only bugfixes and no new features.

Versions
---

We follow [semantic versioning][1] to tag new releases.

Because of quick development process and frequent releases each minor version is
maintained only until next minor version is released. For example, if current version
is `v1.2.0` and there was a bug found in version `v1.1.2` it will be fixed and released
under `v1.2.1` version.

CHANGELOG
---

We write a log of changes that might affect end user. For major versions we provide `UPGRADE x.0`
document which explains how to upgrade project's code to be compatible with given major version. 
                              
 
[1]: http://semver.org/
