# KURC F405 Flight Controller

A 40×40 mm, 4-layer STM32F405 flight controller for Betaflight,
designed in KiCad.
Pin mapping follows the SpeedyBee F405 V3 (`SPEEDYBEEF405V3` target).

<img width="1241" height="1170" alt="261102_02h52m52s_screenshot" src="https://github.com/user-attachments/assets/59117928-cde4-4c09-bfd6-3755afe82c5d" />

## Specs
| | |
|---|---|
| MCU | STM32F405RGT6 (168 MHz) |
| Gyro | BMI270 (SPI) |
| Input | 2S–6S LiPo |
| Regulators | TPS54360 buck → 5 V, AP2112K LDO → 3.3 V |
| USB | USB-C |
| Storage | microSD (blackbox) |
| Size | 40×40 mm, 30.5 mm mounting holes, 4-layer |
| ESC | External 4-in-1 via 8-pin JST-SH |

## Layer stack
<img width="873" height="713" alt="261102_02h53m32s_screenshot" src="https://github.com/user-attachments/assets/08fd27c8-99ae-43b6-b20c-18a0cd21f57e" />


1. **F.Cu**: components and signals
2. **In1**: GND plane
3. **In2**: +3V3 plane
4. **B.Cu**: signals, wire pads, microSD socket

## Repo layout
| Folder | Contents |
|---|---|
| `hardware/` | KiCad project (open `kurc_f405.kicad_pro`) |
| `fabrication/` | Gerber zip and BOM for ordering |
| `docs/` | Schematic PDF and images |
| `firmware/` | Betaflight setup notes |

## Firmware
Flash the Betaflight `SPEEDYBEEF405V3` target, then apply any
remaps from `firmware/betaflight_resources.txt` in the CLI.

## Status
- [x] Schematic
- [x] Placement and routing (DRC clean, 0 unconnected)
- [ ] Fabrication (rev 1)
- [ ] Bring-up and flight test

## Known issues / rev 2 ideas
- Buck converter layout is spread out (long switch node); tighten in rev 2
- VCAP caps (C19/C20) could sit closer to the MCU
- Add 100 nF decoupling right at MCU pin 48

## Tools
KiCad 10 · Arch Linux

## License
Hardware: CERN-OHL-S-2.0
