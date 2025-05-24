# Galaxy100

* Keyboard Maintainer: [Epomaker](https://github.com/Epomaker)
* Hardware Supported: Galaxy100
* Hardware Availability: Galaxy100

Make example for this keyboard (after setting up your build environment):

    make epomaker/galaxy100:default
        
Flashing example for this keyboard:

    make epomaker/galaxy100:default:flash

To reset the board into bootloader mode, do one of the following:

* Hold the Reset switch mounted on the bottom side of the PCB while connecting the USB cable
* Hold the Escape key while connecting the USB cable (also erases persistent settings)
* Fn+L+Esc will reset the board to bootloader mode if you have flashed the default QMK keymap
* Exit bootloader mode (if bootloader does not exit automatically in CLI): `wb32-dfu-updater_cli --reset`


See the [build environment setup](https://docs.qmk.fm/#/getting_started_build_tools) and the [make instructions](https://docs.qmk.fm/#/getting_started_make_guide) for more information. Brand new to QMK? Start with our [Complete Newbs Guide](https://docs.qmk.fm/#/newbs).

---

* Updated: 2025-04-27
* Fixes:
  -  VIA compatibility added in `keymaps/default/rules.mk`
  -  Rotary encoder programming enabled in `keymaps/default/rules.mk`
  -  Provide correct key combination to enter bootloader mode after flashing QMK firmware

* Updated: 2025-05-25
* Fixes:
  -  Added missing RGB Matrix mapping to the `keyboard.json`
  -  Added missing CAPS and NUM status indicator logic in `galaxy100.c`
