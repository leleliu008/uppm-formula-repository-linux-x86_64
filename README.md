# uppm-formula-repository-linux-x86_64
the offical formula repository for [uppm](https://github.com/leleliu008/uppm)

## uppm formula
a uppm formula is a [YAML](https://yaml.org/spec/1.2.2/) format file which is used to config a uppm package's meta-information including one sentence description, package version, installation instructions, etc.

## uppm formula scheme
|KEY|required?|overview|
|-|-|-|
|`summary`|required|Describe this package in one sentence.|
|`webpage`|required|the home webpage url of this package.|
|`license`|optional|a space-separated list of [SPDX license short identifiers](https://spdx.github.io/spdx-spec/v2.3/SPDX-license-list/#a1-licenses-with-short-identifiers)|
|`version`|optional|the version of this package.<br>If this mapping is not present, it will be calculated from `bin-url`|
|`bin-url`|required|the prebuild binary file download url of this package.|
|`bin-sha`|required|the `sha256sum` of the prebuild binary file.|
|`dep-pkg`|optional|a space-separated list of package names. these packages will be used when installing or runtime.|
|`install`|optional|POSIX shell code to be run when installing.<br>If this mapping is not present, and if `bin-url` mapping's value ends with one of `.zip` `.tar.xz` `.tar.gz` `.tar.lz` `.tar.bz2` `.tgz` `.txz` `.tlz` `.tbz2`, `uppm` will uncompress it to `$PKG_INSTALL_DIR` for you. otherwise, just copy it to `$PKG_INSTALL_DIR`|

## Appendix: shell variables that can be used in install block
|variable|overview|
|-|-|
|`NATIVE_OS_ARCH`|current machine os arch.|
|`NATIVE_OS_KIND`|current machine os kind.|
|`NATIVE_OS_TYPE`|current machine os type.|
|`NATIVE_OS_NAME`|current machine os name.|
|`NATIVE_OS_VERS`|current machine os version.|
|`NATIVE_OS_NCPU`|current machine os has how many cpu cores.|
|||
|`UPPM_VERSION`|the version of `uppm`.|
|`UPPM_VERSION_MAJOR`|the major part of `$UPPM_VERSION`.|
|`UPPM_VERSION_MINOR`|the minor part of `$UPPM_VERSION`.|
|`UPPM_VERSION_PATCH`|the patch part of `$UPPM_VERSION`.|
|`UPPM_HOME`|the home directory of `uppm`.|
|`UPPM`|the executbale path of `uppm`.|
|||
|`PKG_SUMMARY`||
|`PKG_VERSION`||
|`PKG_LICENSE`||
|`PKG_WEBPAGE`||
|`PKG_BIN_URL`||
|`PKG_BIN_SHA`||
|`PKG_BIN_FILEPATH`||
|`PKG_BIN_FILENAME`||
|`PKG_BIN_FILETYPE`||
|`PKG_DEP_PKG`||
|`PKG_INSTALL_DIR`|the directory where the current package will be installed to.|
