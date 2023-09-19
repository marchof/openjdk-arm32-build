# Experimental OpenJDK Build on Native arm32

As there is no official arm32 CI build for OpenJDK I tried to set-up this
GitHub Actions workflow to emulate a RaspiOS using qemu.

## Status 2024/05/09

* ✅ Checkout OpenJDK source tree
* ✅ Run RaspiOS emulator with `qemu`
* ✅ Install build dependencies
* ✅ Install bootstrap JDK
* ✅ Run `configure`
* ⚙️ Run `make images`

