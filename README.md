# Experimental OpenJDK Build on Native arm32

As there is no official native arm32 CI build for OpenJDK I tried to set-up this
GitHub Actions workflow to emulate a RaspiOS using [qemu](https://www.qemu.org/).

The build runtime is about 2 hours -- in comparison to 40 minutes on an actual
Raspberry pi 4.

## Steps

* ✅ Checkout OpenJDK source tree
* ✅ Run RaspiOS emulator with `qemu`
* ✅ Install build dependencies
* ✅ Install bootstrap JDK
* ✅ Run `configure`
* ✅️ Run `make images`
* ✅ Zip JDK and upload to action

