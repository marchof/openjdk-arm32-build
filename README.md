# Native ARM 32-Bit OpenJDK Builds

I'm running OpenJDK builds on 32-bit Raspberry Pis for fun since
many years and discovered [several issues](https://bugs.openjdk.org/browse/JDK-8312366?jql=reporter%20%3D%20%27marchof%27%20AND%20summary%20~%20%27arm32%27).
This repository uses [GitHub Actions](https://github.com/features/actions) with
the [qemu](https://www.qemu.org/) emulator to create native 32-bit builds on RaspiOS.
The build time on the emulator is about 2 hours, in comparison to 40 minutes on an actual Raspberry Pi 4.

**⚠️ Published artifacts are completely untested. Use as your own risk!**

Better sources for ARM 32-bit OpenJDK builds are:

* [Bellsoft's Liberica JDK](https://bell-sw.com/pages/downloads/)
* [Mister Shipilëv's Home for Peculiar (JVM) Builds](https://builds.shipilev.net/)


## Build Steps

* Checkout OpenJDK source tree
* Run RaspiOS emulator with `qemu`
* Install build dependencies
* Install bootstrap JDK
* Run `configure`
* Run `make images`
* Zip JDK and upload to action

