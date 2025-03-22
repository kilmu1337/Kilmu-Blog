# General Inspection Process
1. Ensure the flashing process is correct. When flashing, the "ms" following the sector should be in hundreds, `not single digits`.no
2. After flashing, make sure the main pc is completely powered off. Do not directly click reboot.
3. After power-off and reboot, the dma card should have a red light continuously on and a green light continuously on.
4. `Virtualization` and `VT-d/IOMMU` in the main pc BIOS better be disabled.
5. If has issue when using chair, pls close chair and run speed test. and check step 4 .
6. Try to uninstall and rescan in main pc device manager for the emul device.
7. If still has some issues, please send screenshots of the main pc Device Manager and the secondary pc speed test logs.

# Solutions for Some Special Cases

### How to solve `FPGA: TINY PCIe TLP algrithm auto-selected!` when run speed test

![Image](https://github.com/user-attachments/assets/f61cc94e-fa2b-45cf-8aae-5131cf9ff4d8)

- [x] Check if the driver for the emul device in the device manager of the main PC is loaded properly. If the driver is not present, you need to install the corresponding driver. If a yellow exclamation mark is displayed, first try right-clicking on the device in the Device Manager and uninstalling it. Then, right-click and select "Rescan." If it still doesn't work, please check `Virtualization` and `VT-d/IOMMU` in the main pc BIOS
- [x] If using the activator, check if run activator when dma on data port.
- [x] Double click the emul device in device manager, check ->Power Management(if has) ->Untick "Allow this computer to turn off this device to save power") to avoid the BME OFF by main pc os.

### How to solve `FPGA: ERROR: Unable to connect to USB/FT601 device` when run speed test

![Image](https://github.com/user-attachments/assets/57aa54aa-eabe-4169-854a-3512227c55ea)

This issue means there is a problem between your USB cable and the data port.
- [x] Check if it’s in the data port.
- [x] Check this part: `DMA card data port` ⇄ `usb cable` ⇄ `radar pc's usb port`, try to unplug and plug the cable and port.
