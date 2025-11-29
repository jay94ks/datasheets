## ESP32-WROOM-3D (dev module)
### How to fix: Flashing issue with GPIO12.
in default configuration, `GPIO12` is used for bootstrapping pin.
And this may be used to decide voltage for flash. so, this can be solved by:
```
# install esptool.
pip install esptool

# then, burn eFuse (irreversible).
python -m espefuse --port <COM port> set_flash_voltage 3.3V
```

Note that, this solution is only for `WROOM-3D` dev module.
After this, all uploader tools are working well.

References:
1. https://docs.espressif.com/projects/esp-idf/en/latest/esp32/api-reference/peripherals/sd_pullup_requirements.html#strapping-conflicts-dat2
2. https://community.platformio.org/t/unable-to-flash-esp32-wroom-32-esp32-devkit-v1-when-plugged-in-to-custom-pcb/39614/8