# DCB related files

As nVidia puts it:

"Device Control Blocks (DCBs) are static tables used to describe the board topology and connections external to the GPU chip.

Each board built has specific additions to the capabilities through external devices, as well as limitations where output lines are not linked to device connectors.  DCBs define the devices connected, specific information needed to configure those devices, and the external electrical connections such as HDMI and Display Port.

DCBs do not try to explain the capabilities of the chip itself.  That information is implicit in the VBIOS, firmware and drivers, which are built differently for each chip.  Both the firmware and the drivers know the inherent capability of each chip, and use runtime choices to determine chip dependent code paths."

On this folder you'll find:

DCB-4.0-Specification.html and Device Control Block 4.x Specification.html - These are the specifications for the DCB parts of the nVidia VBIOS, sourced from https://download.nvidia.com/open-gpu-doc/DCB/

K2100M DCB Report.txt - DCB related bits from a envytools' nvbios utility output log.

K2100M VBIOS report.txt - Full envytools' nvbios utility output log.

K2100M nvidiainfo-macos.png - Screenshot of the output of nvidiainfo macos utility.