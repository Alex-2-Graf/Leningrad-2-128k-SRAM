# Leningrad-2-128k-SRAM (Aurora)

## Leningrad-2. Russian ZX Spectrum clone with SRAM. Schematics and PCB.

> [English](README.md) | [Русский](README.ru.md)

Following the successful launch of the [Leningrad-2-48k](https://github.com/Alex-2-Graf/LENINGRAD-2-48k) project and incorporating community feedback, this version transitions from dynamic RAM (DRAM) to static RAM (SRAM). 

This architectural shift required a significant redesign of the memory management unit. As a direct benefit, the system memory has been expanded to 128K directly on the mainboard without requiring any external expansion daughterboards.

Additionally, the freed-up PCB space allowed the integration of two YM2149F sound chips, providing "out-of-the-box" Turbo Sound support (by NedoPC). An IORQ arbiter was also added to the schematic.

The final result of these upgrades is the **"Leningrad 2 NEXT 128K + TS 2025"** motherboard. Following hardware assembly, testing, and minor debugging, the project was officially given a new name by close friends: **"Aurora"**.
  
![](Foto/L2_2.01.jpg)  
  
***

### Revisions & Hardware Modules

#### Mainboard Revisions
*   **Revision 2.01** ([Schematics](Export/Leningrad%202%20128k%20SRAM%202.01%202025.pdf) / [Gerber](Gerber/Leningrad%202%20128k%20SRAM%202.01%202025%20gerber%20made%20in%20Italy.zip)) — *Initial release. Features a humorous design note: at the urgent request of the PCB manufacturer, the board text was changed from "Made in..." to "Designed in..." ;)*
*   **Revision 2.02** ([Schematics](Export/Leningrad%202%20128k%20SRAM%202.02%202025.pdf) / [Gerber](Gerber/Leningrad%202%20128k%20SRAM%202.02%202025%20Gerber.zip)) — *The latest stable revision. Adds a power LED indicator and fixes the joystick port routing.*

#### Bus Adapters & Expansion Boards
*   **Nemo-bus and ZX-bus Adapter** ([Gerber](Gerber/L2_NS_Rev_1_1_Gerber.zip)) — *Differs from the previous project version by routing the `/IORQ-GE` signal directly to its intended destination. On older Revision 1 adapters, `/IORQ-GE` went to pin A19 (+beta); it now routes to pin A17. To upgrade a Rev 1 adapter to Rev 2 specs, simply cut the trace going to A19 and solder a jumper wire to A17.*
*   **"Yolka" (3x Nemo-bus & 1x ZX-bus) Slot Expansion Board** ([Schematics](Export/Back_L2_Nemo_x3_Spec_Ver2.1.pdf) / [Gerber](Gerber/Back_L2_Nemo_x3_Spec_Ver2.1_gerber.zip)) — *An expansion backplane made possible by the new onboard hardware arbiter.*
*   **Upgraded Slot Expansion Board** ([Schematics](Export/Back_L2_Nemo_x3_L2.pdf) / [Gerber](Gerber/Back_L2_Nemo_x3_L2_gerber.zip)) — *A redesigned backplane where the ZX-bus connector is replaced with a standard Leningrad-2 edge connector. It also adds a dedicated +5V/+12V power input molex. Vintage ZX-bus cards can still be connected here using adapters ([First](Gerber/Nemo2ZX_BUS_v1.zip) / [Second](Gerber/Nemo2ZX_BUS_v2.zip)).*

#### Keyboard PCB Options
Two mechanical keyboard variants were designed for different mounting styles:
1.  **Chassis Mounted:** Designed to fit directly into a computer case ([Gerber](hGerber/ZX-Keyboard_Gerber.zip)).
2.  **Sandwich / Double-Decker Mounted:** Designed to stack directly on top of the mainboard ([Gerber](Gerber/L2-40Key_gerber.zip)).
*   **Mechanical Switch Support:** Dedicated PCB layouts have been added for **ReDragon-MX-ZT02** ([Gerber](Gerber/L2-40Key-slim-GERBER.zip)) and **ReDragon_Slim_ZT04** ([Gerber](Gerber/ZX-40Key-slim-Gerber.zip)) switches.

***

## Assembly & Jumper Settings

In general, hardware assembly and tuning are straightforward. The functions of the onboard configuration jumpers are as follows:

*   **JP1, JP2, JP3**: Short these if you are installing a standard VGA video connector. Leave them completely open for HDMI output. If using HDMI, make sure all resistors `R24-31` are replaced with 270 Ohm.
*   **J9**: Used to isolate and disconnect power from the RP2040-Zero board while flashing video firmware.
*   **J12**: Used to switch between Beta Disk Interface (BDI) firmware banks if you install a 27256 EPROM containing two separate versions of TR-DOS.

---

## ROM & Video Configuration

*   **ROM**: Detailed EPROM files and configuration info can be found [here](ROM).
*   **VGA**: Firmware and instructions for the RP2040-Zero converter are available [here](VGA).

---

## Recommended Accessories

* [BDI-TR-DOS](https://github.com/Alex-2-Graf/Leningrad2-BDI-TR-DOS)
* [DivMMC](https://github.com/Alex-2-Graf/Leningrad2-DivMMC)
* [LGT-Turbo-Sound-emulator](https://github.com/Alex-2-Graf/LGT-Turbo-Sound-emulator)
* [ZX-EQ Nemo-bus Edition](https://github.com/Alex-2-Graf/ZX-EQ)

---

## Credits & Acknowledgments

*   **Alex Ekb (Aleksey)** — for the incredible RGB2VGA converter design.
*   **HRDY (Dmitry)** — special thanks for his invaluable technical advice, consulting, and support.
*   The **Scorpion ZS & Leningrad** community, and all friends who helped bring this project to life.
