# TVI3315A on Linux 6.18

The rebuild step applies `device-tree-fixes.dts` to the selected board DTB.
It renames the first RK808 clock output and enables I2S2 for HDMI audio.
The host needs the `device-tree-compiler` package. The helper checks the
board compatible and the HDMI sound card's CPU DAI before replacing the DTB.

The TVI3315A test workflow builds the pinned Bookworm base image with the
6.18.63 kernel, checks the merged DTB inside the compressed image, and uploads
the result as an Actions artifact. The board-level DTS fixes are tracked in
[unifreq/linux-6.18.y#109](https://github.com/unifreq/linux-6.18.y/pull/109).
