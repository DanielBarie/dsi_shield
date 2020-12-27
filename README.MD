DSI Core Readme
------------------------
# Disclaimer

This project implements a MIPI DSI (MIPI Display Serial Interface) Verilog core.
Since the DSI specification is non-public and requires an NDA, the core was built
using bits and pieces available throughout the Web: presentations, display controller/SOC
datasheets, various application notes and Android kernel drivers. The author is not 
associated in any way with the MIPI Alliance. The core is provided as-is, it has never been
verified for compliance with the DSI standard and it probably lacks many of its features.
You use it at your own risk, there's no warranty.

# Get it up and running

- This is an XC6 Spartan project. It cannot be synthesized using Xilinx' new toolchain (Vivado). You'll have to use the original ISE toolchain.
- Version 2 of the HDL part depends on the original author's implementation of a RISC-V core. Don't get it from his github. It won't work. Go to the Open Hardware Repository instead: https://ohwr.org/project/urv-core. Download the entire repository and unzip it to the subdirectory ip_cores/urv-core. Else, ISE will complain about missing files. Why not the version from the author's github? It won't implement. 
- Adding the Xilinx HDMI IP needs a little care: The unpack script will write read-only files. So patching fails. This repo contains a modified version of the unpack script.

# License

- All HDL (unless otherwise noted) is released under LGPL v3.0
- All software (unless otherwise noted), is GPL v 3.0 or later.
- PCB design and schematics are licensed under CERN Open Hardware License v 1.2.

# Acknowledgements

- Special thanks go to Sebastien Bourdeauducq, the creator of the Milkymist project, for his 
  excellent IP cores (HPDMC, FML and LM32 Xilinx port) used by in the DSI shield firmware.

- Andrew "Bunnie" Huang, for his EDID generation tools (Chumby WebTV project).

- The original author of this project (https://github.com/twlostow/dsi-shield, https://hackaday.io/project/364-mipi-dsi-display-shieldhdmi-adap).
