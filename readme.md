# Galaxy100

* Keyboard Maintainer: [Epomaker](https://github.com/Epomaker)
* Hardware Supported: Galaxy100
* Hardware Availability: Galaxy100

Compile example for this keyboard (after setting up your build environment):

    qmk compile -kb epomaker/galaxy100 -km default

Flashing example for this keyboard:

    qmk flash epomaker_galaxy100_default.bin

To reset the board into bootloader mode, do one of the following:

_Before before flashing QMK:_
* Hold the Escape key while connecting the USB cable (also erases persistent settings)

_After flashing QMK:_
* Fn+L+Esc will reset the board to bootloader mode if you have flashed the default QMK keymap


See the [build environment setup](https://docs.qmk.fm/#/getting_started_build_tools) and the [make instructions](https://docs.qmk.fm/#/getting_started_make_guide) for more information. Brand new to QMK? Start with our [Complete Newbs Guide](https://docs.qmk.fm/#/newbs).

---

# Instructions for QMK Toolbox (CLI) 

* Updated: 2025-04-19
* Fixes:
   -  VIA compatibility added in `keymaps/default/rules.mk`
   -  Provide correct key combination to enter bootloader mode after flashing QMK firmware

## Prerequisites

* Make sure git and python/pip are installed on your system.

Example for Fedora/Linux:

```bash
> sudo yum -y install git python3-pip
```

* Install the QMK CLI

```bash
> python3 -m pip install --user qmk
```

* Make sure [wb32-dfu-updater-cli]([)https://copr.fedorainfracloud.org/coprs/erovia/wb32-dfu-updater/) is available on your system.

```bash
> dnf copr enable erovia/wb32-dfu-updater
> dnf install wb32-dfu-updater
```

* Validate folder structure:

```
├── galaxy100
│   ├── rgb_record/
│   ├── ├── rgb_record.c
│   ├── ├── rgb_record.h
│   ├── ├── rgb_record.mk
│   ├── keymaps/
│   ├── ├── default/
│   ├── ├── ├── keymap.c
│   ├── ...
``` 

## Steps to build and flash the Galaxy100 QMK firmware

### 1. Copy source files to your qmk_firmware folder

```bash
> cp -r "<path_to_galaxy100>" <path_to_qmk_firmware>/keyboards/epomaker/
```

Example:

```bash
> cp -r ~/Downloads/galaxy100 ~/qmk_firmware/keyboards/epomaker/
```

### 2. Compile the firmware binary

* Make sure you are in the qmk_firmware folder.

```bash
> qmk compile -kb epomaker/galaxy100 -km default
> Compiling: ...
# Done:
> Copying epomaker_galaxy100_default.bin to qmk_firmware folder
```

### 3. Boot into bootloader

* Hold the escape key, then plug in the USB cable to the keyboard.

### 4. Flash the firmware binary

```bash
> qmk flash epomaker_galaxy100_default.bin
```
