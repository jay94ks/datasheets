## Crystals
### 12MHz.
1) Yajingxin: [TAXM12M4RLBDDT2T](/PDF/Yajingxin/TAXM12M4RLBDDT2T_12MHz.pdf)
   1) Size: `3225`, `12MHz`.
   2) Load Capacitance: `20pF`.
   3) Drive Level: `100uw`.
   4) ESR: `50 ohm`. (RP2040 recommended value)
   5) Comments: When using this as the RP2040 main crystal, if the chip does not boot properly, it is because the bootROM advances to the next stage earlier than the XOSC oscillation starts. So, add the following option to the `CMakeLists.txt` file: `add_compile_definitions(PICO_XOSC_STARTUP_DELAY_MULTIPLIER=48)`