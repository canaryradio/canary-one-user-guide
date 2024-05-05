# Canary One User Guide

## Quick Start
1. Important: Connect Antenna.  The radio should not start tx until the LoRA region is set after the first pairing.  However, best practice is to always have the antenna connected when the device is on.  Failure to do so could damage the chip. 
2. Power your device by pressing the right button.
3. Open the Meshtastic App on your phone and pair.

## Upgrading Firmware
*Note*: Meshstastic firmware is changing at a rapid pace.  Meshtastic supports a wide array of hardware devices and sometimes breaking changes are introduced.  The CRC team will make every effort to test Firmware before it makes it to `beta`, but this is not always possible.

Two Options:

Automated: Visit [https://flasher.meshtastic.org/](https://flasher.meshtastic.org/) and follow the instructions

Manual:
1. Visit [https://flasher.meshtastic.org/](https://flasher.meshtastic.org/), select CanaryOne and download the version of firmware you want OR download firmware from [https://github.com/meshtastic/firmware/releases](https://github.com/meshtastic/firmware/releases)
1. Enter [bootloader mode](#enter-bootloader-mode-manually)
1. From your computer drag and drop `firmware-canaryone-XXXX.uf2` to `CANARYBOOT`

## Enter BootLoader Mode Manually
If the device is off:
1. plug the device in to USB
2. hold down the right button
3. the device will blink slowly and mount to your computer

If the device is on:
1. plug the device into USB
1. hold down both buttons for 10 seconds until the device is shutting down
1. release the left button and continue holding the right button
1. the device will begin flashing rapidly and then pulse slowly

Exiting Bootloader mode:
Currently, there is no mechanical exit from bootloader mode.  Drag and drop firmware onto the device and it will restart.



## Factory Reset
Typically there is no reason to factory reset the device.

1. Put the device in bootloader mode.
1. Download the firmware you want from [https://github.com/meshtastic/firmware/releases](https://github.com/meshtastic/firmware/releases) or [https://flasher.meshtastic.org/](https://flasher.meshtastic.org/)
1. Drag and drop the `Meshtastic_nRF52_factory_erase_v2.uf2` to `CANARYBOOT`
1. The device will temporarily have no feedback - no lights
1. Download and install the meshtastic python cli to your machine
1. From a terminal run `meshtastic --noproto`
1. The device will now enter bootloader mode
1. Drag and drop `firmware-canaryone-XXXX.uf2`
