# Possibly the most best Verilog-Based DPI and MIPI-DSI FPGA Examples

## If this project is constructive, welcome to donate a drink to PayPal.

<img src="images/qrcode.png" style="height:20%; width:20%">

or 

paypal.me/briansune

### This project aimed to support MIPI or DPI I/F off-the-shelf LCD/TFT display.

#### Expected FPGA Support

1) ✅ Xilinx - 7 series (Currently tested on Kintex 7 & Artix 7)

2) ✅ Xilinx - 6 series (Currently tested on Spartan 6)

3) ✅ Xilinx - Ultrascale+ / Ultrascale  (Currently tested on ZYNQMP)

4) ✅ Altera - Cyclone IV (Currently tested on Cyclone IV EP4CE6F17C8)

5) 🔜 Altera - Cyclone V

6) ✅ Anlogic - EG4 series (Currently tested on EAGLE 4 EG4X20BG256)

7) ✅ Anlogic - DR1 series (Currently tested on Dragon 1 DR1V90MEG484)


#### FPGA Support Details

a) In the follow examples, Xilinx 6 series, 7 series, ultrascale+ series should able to support as much MIPI display as possible.

b) Xilinx 6 or 7 would require resistor network to convert LVDS to SLVS.

c) Successful cases are demonstrated on three Xilinx FPGA families "Spartan", "Kintex", "Artix", and "ZYNQ Ultrascale+".

d) It is confident to say this pure Verilog-based MIPI DSI design is stabled and matured enough to merge onto any FPGA with serialization feature.

### Read First !

Please study the example 5.5" LCD with LCD driver HX8399C.

This example provided detail resistor-network vs MC20902 design, which is aligned with Xilinx doc. "XAPP894".

The resistor-network is not re-simulated via IBIS simulator, so if you really concern on SI then do it as your will.

### Commonly Asked Questions

1) Q: Do this design only work on Xilinx 7-series? A: There are example in Ultrascale, and other non-MIPI DSI supported FPGA brand tested internally.

2) Q: Why there are no brand xxx FPGA given? A: Because either the brand xxx either I don't have it or it is tested internally but not worth to recreate new repositories.

3) Q: Can brand xxx FPGA support 1080p, 2k, 4k etc A: If you understand how MIPI-DSI video mode works, this question won't even exist from first place!!!

4) Q: Can this Verilog-based HDL design work on brand xxxx. A: Very high chances, because the inherent design don't rely on IPs nor any DPHY, it is pure MACROs and HDL.

Remarks: there are many people asked Spartan 6 should support MIPI-DSI as well.

From experiment, it do work as expected, but why I got to buy Spartan 6 when Artix 7 is even cheaper and performs better in all aspects ❓❓❓

>>> If there are any technical questions, please contact via Email: briansune@gmail.com

### Video Test Pattern Top Block-Diagram

<img src="./images/MIPI_IP_TOP.jpg" width="600">

### A Full Resources Report under Kintex-7 XC7K325T (Vivado 2024.2)

[Full-Report](./Kintex7_MIPI_DSI.html)

### Tested FPGA IDE Tools

1) Vivado 2020.2 - Original Develop Environment

2) Vivado 2024.2 - Updated Environment (No Modification is Found on HDL files)

3) ISE 14.7

4) Quartus Prime 18.1

5) Tang Dynasty 4.6

6) Tang Dynasty 5.9

### Display Examples

Remarks: "V" Video Mode, "C" Command Mode

|Idx|Display|Status|I/F|Driver IC|Lane #|Mode|Project Link|Tested FPGA|IDE|FPS|W,H,BPP|
|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
|  1 | <img src="./images/1p32inch_lcd.png" width="100">     | 🟢 DONE    | MIPI | GC9C01       | 1   | C   | [ZJY132R-IG03](https://github.com/briansune/Kintex-7-MIPI-DSI-1.32-inch-LCD)        | K7,ZU  | Vivado | 60 |    360,360,[24]     |
|  2 | <img src="./images/1p6inch_lcd.png" width="100">      | 🟢 DONE    | MIPI | ST7797       | 1   | V   | [DT160BQ-C12-01](https://github.com/briansune/Kintex-7-MIPI-DSI-1.6-inch-LCD)       | A7,K7  | Vivado | 60 |    400,400,[16,24]  |
|  3 | <img src="./images/2p95inch_lcd.png" width="100">     | 🟢 DONE    | MIPI | ST7701S      | 2   | V   | [CY300H4003](https://github.com/briansune/Kintex-7-MIPI-DSI-2.95-inch-LCD)          | K7     | Vivado | 60 |    360,640,[16,24]  |
|  4 | <img src="./images/3p97inch_lcd.png" width="100">     | 🟢 DONE    | MIPI | ST7701S      | 2   | V   | [T397B5-C24-02](https://github.com/briansune/Artix-Kintex-7-MIPI-DSI-3.97-inch-LCD) | C4,A7,K7  | Quartus<br>Vivado | 60 |    480,800,[16,24]  |
|  5 | <img src="./images/4p5inch_lcd.png" width="100">      | 🟢 DONE    | MIPI | NT35516      | 2   | V/C | [INX4.5](https://github.com/briansune/Artix-Kintex-7-MIPI-DSI-4.5-inch-LCD)         | C4,A7,K7  | Quartus<br>Vivado | 60 |    540,960,[16,24]  |
|  6 | <img src="./images/5p5inch_lcd.png" width="100">      | 🟢 DONE    | MIPI | HX8399C      | 4   | V   | [AML055T012A K7](https://github.com/briansune/Kintex-7-MIPI-DSI-5.5-inch-LCD)<br>[AML055T012A S6](https://github.com/briansune/Spartan-6-MIPI-DSI-5.5-inch-LCD)<br>[AML055T012A C4](https://github.com/briansune/Cyclone-IV-MIPI-DSI-5.5-inch-LCD)<br>[AML055T012A EG4](https://github.com/briansune/Eagle-4-MIPI-DSI-5.5-inch-LCD)<br>[AML055T012A DR1]https://github.com/briansune/Dragon-1-MIPI-DSI-5.5-inch-LCD | EG4,C4,S6,A7,K7     | TD<br>Quartus<br>Vivado | 40,50,60 |  1080,1920,[16,24]  |
|  7 | <img src="./images/3p97inch_lcd_2nd.png" width="100"> | 🟢 DONE    | MIPI | ST7701S      | 2   | V   | [HXR397HS25PIN](https://github.com/briansune/Kintex-7-MIPI-DSI-3.97-inch-LCD-B)     | A7,K7  | Vivado | 60 |    480,800,[16,24]  |
|  8 | <img src="./images/5inch_lcd.JPG" width="100">        | 🟢 DONE    | MIPI | R61322       | 4   | V   | [DXQ5D0039](https://github.com/briansune/Kintex-7-MIPI-DSI-5-inch-LCD)              | A7,K7  | Vivado | 60 |  1080,1920,[24]     |
|  9 | <img src="./images/5p5inch_lcd_c.png" width="100">    | 🟢 DONE    | MIPI | JD9522Z      | 4   | V   | [HD55017C31](https://github.com/briansune/Kintex-7-MIPI-DSI-5.5-inch-LCD-C)         | C4,S6,A7,K7  | Quartus<br>ISE<br>Vivado | 60 |  1080,1920,[16,24]  |
| 10 | <img src="./images/10p1inch_lcd.jpg" width="100">     | 🟢 DONE    | MIPI | JD9365DA-H3  | 4   | V   | [MX101BA13](https://github.com/briansune/Kintex-7-MIPI-DSI-10.1-inch-LCD)           | S6,A7,K7  | ISE<br>Vivado | 60 |   800,1280,[16,24]  |
| 11 | <img src="./images/3p4inch_lcd.png" width="100">      | 🟢 DONE    | MIPI | JD9365DA-H3  | 3   | V   | [HD34003C39](https://github.com/briansune/Kintex-7-MIPI-DSI-3.4-inch-LCD)           | K7     | Vivado | 60 |    800,800,[16,24]  |
| 12 | <img src="./images/2p95inch_lcd_B.png" width="100">   | 🟢 DONE    | MIPI | ST7701S      | 2   | V   | [HXR030HSD40PIN](https://github.com/briansune/Kintex-7-MIPI-DSI-2.95-inch-LCD-B)    | K7     | Vivado | 60 |    360,640,[16,24]  |
| 13 | <img src="./images/5p5inch_2k_lcd.png" width="100">   | 🟢 DONE    | MIPI | R63419       | 4,4 | V   | [LS055R1SX04](https://github.com/briansune/Kintex-7-MIPI-DSI-5.5-inch-2K-LCD)       | K7     | Vivado | 60 | 720x2,2560,[24]     |
| 14 | <img src="./images/5p5inch_4k_lcd.png" width="100">   | 🟡 1080p   | MIPI | NT35950      | 4,4 | V   | [AML055D105G](https://github.com/briansune/Kintex-7-MIPI-DSI-5.5-inch-4K-LCD)       | K7     | Vivado | 60 |  1080,1920,[24]     |
| 15 | <img src="./images/6p9inch_lcd.png" width="100">      | 🟢 DONE    | MIPI | GC9702P      | 4   | V   | [HD69002C31](https://github.com/briansune/Kintex-7-MIPI-DSI-6.9-inch-LCD)           | C4,A7,K7  | Quartus<br>Vivado | 60 |   720,1440,[24]     |
| 16 | <img src="./images/3p5inch_lcd.png" width="100">      | 🟢 DONE    | MIPI | FL7703NP     | 4   | V   | [HD35052C31](https://github.com/briansune/Kintex-7-MIPI-DSI-3.5-inch-LCD)           | C4,S6,A7,K7  | Quartus<br>ISE<br>Vivado | 60 |   720,1280,[16,24]  |
| 17 | <img src="./images/4p1inch_lcd.png" width="100">      | 🟢 DONE    | MIPI | NV3051F1     | 4   | V   | [HD41004C31](https://github.com/briansune/Kintex-7-MIPI-DSI-4.1-inch-LCD)           | A7,K7  | Vivado | 60 |   720,1280,[24]     |
| 18 | <img src="./images/5inch_lcd_720.png" width="100">    | 🟢 DONE    | MIPI | ILI9881C     | 4   | V   | [HD50004C30](https://github.com/briansune/Artix-7-MIPI-DSI-5-inch-LCD)              | A7     | Vivado | 60 |   720,1280,[16,24]     |
| 19 | <img src="./images/7inch_lcd.png" width="100">        | 🟢 DONE    | DPI  | AT070N92/94  | x   | V   | [AT070N92/94](https://github.com/briansune/max-II-cpld-sdram-tft-driver)            | MAX II | Quartus       | 60 |    800,480,[24]     |
| 20 | <img src="./images/5inch_lcd_s3.png" width="100">     | 🟢 DONE    | DPI  | AT070N92/94  | x   | V   | [AT070N92/94](https://github.com/briansune/Spartan_3_sdram_ftf_driver)              | S3     | ISE      | 60 |    800,480,[24]     |

### Tested LCD Driver IC(s)

✅ No Issue / Supported

❎ Vendor confirm it is not supported or silicon issue

✖ Datasheet clearly mentioned not support

❔ No Datasheet is found

❌ Datasheet clearly mentioned support, but abnormal display

🚨 Not recommended

🚫 Command Mode supported, color depth work differently

|Idx|IC Company|Driver IC|16bpp|24bpp|Stable|
|:-:|:-:|:-:|:-:|:-:|:-:|
|  1 | RENESAS SP | R61322      | ✖️ | ✅ | ✅ |
|  2 | RENESAS SP | R63419      | ✖️ | ✅ | ✅ |
|  3 | Sitronix   | ST7797      | ✅ | ✅ | ✅ |
|  4 | Sitronix   | ST7701S     | ✅ | ✅ | ✅ |
|  5 | JADARD     | JD9365DA-H3 | ✅ | ✅ | ✅ |
|  6 | Forcelead  | FL7703NP    | ✅ | ✅ | ✅ |
|  7 | Novatek    | NT35516     | ✅ | ✅ | ✅ |
|  8 | Novatek    | NT35950     | ❔ | ✅ | ✅ |
|  8 | Fitipower  | JD9522Z     | ✅ | ✅ | ✅ |
|  9 | Himax      | HX8399-C    | ✅ | ✅ | ✅ |
| 10 | GALAXYCORE | GC9C01      | 🚫 | 🚫 | ✅ |
| 11 | GALAXYCORE | GC9702P     | ❌ | ✅ | 🚨 |
| 12 | New Vision | NV3051F1    | ❎ | ✅ | ✅ |
| 13 | ILITEK     | ILI9881C    | ✅ | ✅ | ✅ |
