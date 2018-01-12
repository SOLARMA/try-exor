# Trying manual rebuild of EXOR Embedded BSP

(2018-01-12 16:00 CET)

See https://github.com/ExorEmbedded/exor-bsp-platform/blob/pyro/README.adoc

Logged as gmacario@mv-linux-powerhorse

```shell
mkdir ~/tmp/exor-yocto-3.0
cd ~/tmp/exor-yocto-3.0
docker run -ti --volume=${PWD}/shared:/home/build/shared gmacario/build-yocto
```

Logged as build@container

```shell
mkdir -p ~/shared && sudo chown build.build ~/shared
cd ~/shared

git config --global user.email "easy-build@solarma.it"
git config --global user.name "easy-build"

repo init -u https://github.com/ExorEmbedded/exor-bsp-platform -b pyro
repo sync
```

(2018-01-12 16:03 CET)

To start a simple image build:

```shell
source git/yocto-poky/oe-init-build-env build
cp ../git/meta-exor/conf/bblayers.conf.sample conf/bblayers.conf
cp ../git/meta-exor/conf/local.conf.sample conf/local.conf
bitbake core-image-exor-x11
```

Build log:

```
build@c8be4c1de7b1:~/shared$ source git/yocto-poky/oe-init-build-env build
You had no conf/local.conf file. This configuration file has therefore been
created for you with some default values. You may wish to edit it to, for
example, select a different MACHINE (target hardware). See conf/local.conf
for more information as common configuration options are commented.

You had no conf/bblayers.conf file. This configuration file has therefore been
created for you with some default values. To add additional metadata layers
into your configuration please add entries to conf/bblayers.conf.

The Yocto Project has extensive documentation about OE including a reference
manual which can be found at:
    http://yoctoproject.org/documentation

For more information about OpenEmbedded see their website:
    http://www.openembedded.org/


### Shell environment set up for builds. ###

You can now run 'bitbake <target>'

Common targets are:
    core-image-minimal
    core-image-sato
    meta-toolchain
    meta-ide-support

You can also run generated qemu images with a command like 'runqemu qemux86'
build@c8be4c1de7b1:~/shared/build$ cp ../git/meta-exor/conf/bblayers.conf.sample conf/bblayers.conf
build@c8be4c1de7b1:~/shared/build$ cp ../git/meta-exor/conf/local.conf.sample conf/local.conf
build@c8be4c1de7b1:~/shared/build$ bitbake core-image-exor-x11
NOTE: /home/build/shared/build/../git/meta-exor/recipes-bsp/xloader/xloader_git.bb: base_contains is deprecated, please use bb.utils.contains instead.
NOTE: /home/build/shared/build/../git/meta-exor/recipes-bsp/bootloader/bootloader_git.bb: base_contains is deprecated, please use bb.utils.contains instead.
Parsing recipes: 100% |###############################################| Time: 0:00:59
Parsing of 2198 .bb files complete (0 cached, 2198 parsed). 2968 targets, 234 skipped, 141 masked, 0 errors.
WARNING: No bb files matched BBFILE_PATTERN_freescale-layer '^/home/build/shared/build/../git/meta-freescale/'
NOTE: Resolving any missing task queue dependencies
ERROR: Nothing RPROVIDES 'amx3-cm3' (but /home/build/shared/build/../git/meta-exor/recipes-kernel/linux-ti/linux-ti-staging_4.1.bb RDEPENDS on or otherwise requires it)
NOTE: Runtime target 'amx3-cm3' is unbuildable, removing...
Missing or unbuildable dependency chain was: ['amx3-cm3']
NOTE: Runtime target 'oprofile' is unbuildable, removing...
Missing or unbuildable dependency chain was: ['oprofile', 'virtual/kernel', 'amx3-cm3']
ERROR: Required build target 'core-image-exor-x11' has no buildable providers.
Missing or unbuildable dependency chain was: ['core-image-exor-x11', 'oprofile', 'virtual/kernel', 'amx3-cm3']

Summary: There was 1 WARNING message shown.
Summary: There were 2 ERROR messages shown, returning a non-zero exit code.
build@c8be4c1de7b1:~/shared/build$
```

<!-- EOF -->