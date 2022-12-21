# uppm-formula-repository-linux-x86_64
the offical formula repository for [uppm](https://github.com/leleliu008/uppm)

## what's formula
formula is a YAML format file which is used to config a [uppm](https://github.com/leleliu008/uppm) package infomation and describe how to install it.

|KEY|required?|overview|
|-|-|-|
|`summary`|required|the summary of this package.|
|`webpage`|required|the home webpage of this package.|
|`license`|optional|the license of this package.|
|`version`|optional|the version of this package.<br>If this key is not present, it will be calculated from `bin-url`|
|`bin-url`|required|the prebuild binary archive file download url of this package.<br>must end with one of `.zip` `.tar.xz` `.tar.gz` `.tar.lz` `.tar.bz2` `.tgz` `.txz` `.tlz` `.tbz2`|
|`bin-sha`|required|the `sha256sum` of the prebuild binary archive file.|
|`dep-pkg`|optional|space-separated packages that will be used when installing or runtime.|
|`install`|optional|bash shell code to be run when installing.|

## the variable can be used in install block
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
|`UPPM_HOME`|the home directory of `uppm`.|
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
