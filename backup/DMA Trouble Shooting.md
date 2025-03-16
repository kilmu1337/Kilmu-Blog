1. Ensure the flashing process is correct. When flashing, the "ms" following the sector should be in hundreds, `not single digits`.
2. After flashing, make sure the main pc is completely powered off. Do not directly click reboot.
3. After power-off and reboot, the dma card should have a red light continuously on and a green light continuously on.
4. Virtualization and VT-d/IOMMU in the main pc BIOS better be disabled.
5. If has issue when using chair, pls close chair and run speed test. and check step 4 .
6. Try to uninstall and rescan in main oc device manager for the emul device.
7. If still has some issues, please send screenshots of the main pc Device Manager and the secondary pc speed test logs.