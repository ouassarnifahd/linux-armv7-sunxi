# linux-armv7 (v5.1) for Allwinner H3/H2+
Built for ArchLinuxARM and includes:
- Armbian sunxi-next patches.
- working Ethernet controler.
- xradio_wlan driver.

### Compiling:

Make sure you have an armhf toolchain (arm-linux-gnueabihf) in your PATH variable and run:

    $ CARCH=armv7h makepkg -s
