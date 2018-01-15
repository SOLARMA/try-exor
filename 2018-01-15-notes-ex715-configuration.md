# Notes on the EX715 software configuration

## SW config as inspected on the sample EX715 panel

Checked on 2018-01-15, 18:00 CET

* Kernel: `Linux version 3.14.28-rt25-1.0.0_ga-gfab7ac7 (autosvn@build-station-linux) (gcc version 4.9.3 (GCC) ) #1 SMP PREEMPT RT Tue Mar 28 15:17:24 CEST 2017`
* libc: TODO
* Qt libraries: libQt version 4.8.5 for: Core, DBus, Gui, Network, OpenGL, Test, Xml; libQtWebKit version 4.9.4
* NodeJS v0.10.45

## SW config of binaries on download.exorint.com

Checked on 2018-01-15, 18:00 CET

#### From `jmobile2.01-233-2_portable_us03kit_cds3.tar.gz`

* Xorg Server 6.3.0
* Qt libraries 4.8
* JMobile 2.01 runtime
* CODESYSControl (Runtime System)

## SW config built with SOLARMA/exor-bsp-platform core-image-exor-x11

* Kernel: Bitbake recipe `linux-imx-rt-3.14.28-r0`
* libc: TODO
* TODO: x11vnc

<!-- EOF -->
