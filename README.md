# i2c-piix4-aura-dkmsi2c-piix4-aura-dkms
## Intro
This repository contains a patched i2c-piix4 module which supports the secondary i2c controller on several >= X370 AM4 mainboards as DKMS-package for Debian GNU/Linux Unstable. This package might work with earlier versions of Debian but mileage may vary. It is designed as a soft dependency for future packaged versions of [OpenRGB](https://gitlab.com/CalcProgrammer1/OpenRGB) to enable access to RGB LED settings of these mainboards. 
The original idea of patching and packaging this module was *lend* from the package i2c-piix4-aura-dkms found at [Arch Linux AUR](https://aur.archlinux.org/packages/i2c-piix4-aura-dkms). I have only changed some Debian-specific pathes and added some packaging information with debhelper.
## Usage
Clone this repository and run `dpkg-buildpackage -us -uc -b`. Install the resulting package with `sudo dpkg -i path/to.deb`.
To have OpenRGB controlling your LEDs you either need to add your user to the group `adm` or simply run OpenRGB as root. I'd rather not recommend to run any GUI application with root privileges.
THX
## Thanks to 
- [CalcProgrammer1](https://gitlab.com/CalcProgrammer1) for his awesome work on OpenAuraSDK/OpenRGB and his fix for i2c-piix4,
- Térence Clastres for the awesome idea of squeezing this patch into a DKMS package and
- my gf for sharing and supporting my obsession with RGB LED stuff and Linux.
