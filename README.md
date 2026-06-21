# Leningrad-2-128k-SRAM (Aurora)

## Leningrad-2. Russian ZX Spectrum clone with SRAM. Schematics and PCB.

> [English](README.md) | [Русский](README.ru.md)

Following the successful launch of the Leningrad-2-48k project and incorporating community feedback, this version transitions from dynamic RAM (DRAM) to static RAM (SRAM). 

This architectural shift required a significant redesign of the memory management unit. As a direct benefit, the system memory has been expanded to 128K directly on the mainboard without requiring any external expansion daughterboards.

Additionally, the freed-up PCB space allowed the integration of two YM2149F sound chips, providing "out-of-the-box" Turbo Sound support (by NedoPC). An IORQ arbiter was also added to the schematic.

The final result of these upgrades is the **"Leningrad 2 NEXT 128K + TS 2025"** motherboard. Following hardware assembly, testing, and minor debugging, the project was officially given a new name by close friends: **"Aurora"**.

***

### Revisions & Hardware Modules

#### Mainboard Revisions
*   **Revision 2.01** ([Schematics](https://github.com/Alex-2-Graf/Leningrad-2-128k-SRAM) / [Gerber](https://github.com/Alex-2-Graf/Leningrad-2-128k-SRAM)) — *Initial release. Features a humorous design note: at the urgent request of the PCB manufacturer, the board text was changed from "Made in..." to "Designed in..." ;)*
*   **Revision 2.02** ([Schematics](https://github.com/Alex-2-Graf/Leningrad-2-128k-SRAM) / [Gerber](https://github.com/Alex-2-Graf/Leningrad-2-128k-SRAM)) — *The latest stable revision. Adds a power LED indicator and fixes the joystick port routing.*

#### Bus Adapters & Expansion Boards
*   **Nemo-bus and ZX-bus Adapter** ([Gerber](https://github.com/Alex-2-Graf/Leningrad-2-128k-SRAM)) — *Differs from the previous project version by routing the `/IORQ-GE` signal directly to its intended destination. On older Revision 1 adapters, `/IORQ-GE` went to pin A19 (+beta); it now routes to pin A17. To upgrade a Rev 1 adapter to Rev 2 specs, simply cut the trace going to A19 and solder a jumper wire to A17.*
*   **"Yolka" (3x Nemo-bus & 1x ZX-bus) Slot Expansion Board** ([Schematics](https://github.com/Alex-2-Graf/Leningrad-2-128k-SRAM) / [Gerber](https://github.com/Alex-2-Graf/Leningrad-2-128k-SRAM)) — *An expansion backplane made possible by the new onboard hardware arbiter.*
*   **Upgraded Slot Expansion Board** ([Schematics](https://github.com/Alex-2-Graf/Leningrad-2-128k-SRAM) / [Gerber](https://github.com/Alex-2-Graf/Leningrad-2-128k-SRAM)) — *A redesigned backplane where the ZX-bus connector is replaced with a standard Leningrad-2 edge connector. It also adds a dedicated +5V/+12V power input molex. Vintage ZX-bus cards can still be connected here using adapters ([First](https://github.com/Alex-2-Graf/Leningrad-2-128k-SRAM) / [Second](https://github.com/Alex-2-Graf/Leningrad-2-128k-SRAM)).*

#### Keyboard PCB Options
Two mechanical keyboard variants were designed for different mounting styles:
1.  **Chassis Mounted:** Designed to fit directly into a computer case ([Gerber](https://github.com/Alex-2-Graf/Leningrad-2-128k-SRAM)).
2.  **Sandwich / Double-Decker Mounted:** Designed to stack directly on top of the mainboard ([Gerber](https://github.com/Alex-2-Graf/Leningrad-2-128k-SRAM)).
*   **Mechanical Switch Support:** Dedicated PCB layouts have been added for **ReDragon-MX-ZT02** ([Gerber](https://github.com/Alex-2-Graf/Leningrad-2-128k-SRAM)) and **ReDragon_Slim_ZT04** ([Gerber](https://github.com/Alex-2-Graf/Leningrad-2-128k-SRAM)) switches.

***

## Assembly & Jumper Settings

In general, hardware assembly and tuning are straightforward. The functions of the onboard configuration jumpers are as follows:

*   **JP1, JP2, JP3**: Short these if you are installing a standard VGA video connector. Leave them completely open for HDMI output. If using HDMI, make sure all resistors `R24-31` are replaced with 270 Ohm.
*   **J9**: Used to isolate and disconnect power from the RP2040-Zero board while flashing video firmware.
*   **J12**: Used to switch between Beta Disk Interface (BDI) firmware banks if you install a 27256 EPROM containing two separate versions of TR-DOS.

---

## ROM & Video Configuration

*   **ROM**: Detailed EPROM files and configuration info can be found [here](https://github.com/Alex-2-Graf/Leningrad-2-128k-SRAM).
*   **VGA**: Firmware and instructions for the RP2040-Zero converter are available [here](https://github.com/Alex-2-Graf/Leningrad-2-128k-SRAM).

---

## Recommended Accessories

*   BDI-TR-DOS
*   DivMMC
*   LGT-Turbo-Sound-emulator
*   ZX-EQ Nemo-bus Edition

---

## Credits & Acknowledgments

*   **Alex Ekb (Aleksey)** — for the incredible RGB2VGA converter design.
*   **HRDY (Dmitry)** — special thanks for his invaluable technical advice, consulting, and support.
*   The **Scorpion ZS & Leningrad** community, and all friends who helped bring this project to life.
