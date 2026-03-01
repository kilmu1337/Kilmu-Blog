### What is `Pcileech`?

Currently, all DMA firmware is based on [pcileech-fpga](https://github.com/ufrisk/pcileech-fpga), which is not just a hardware conclusion but also requires software to be adapted to pcileech. I know there are many market gimmicks about non-pcileech solutions, so use your brain and don’t be fooled.

---

### What is `Activator`? /How is the `Activator` working?/What is the subscription model of DMA firmware?

The Activator is a necessary software component for the subscription-based firmware, enabling the firmware to function by running the activator on a second PC.

The subscription model of DMA firmware is an FPGA technology that requires developers to have a thorough understanding of firmware. It allows the firmware to receive the latest updates like software, rather than remaining static.

---

### What is `Pooled Firmware`?
Pooled Firmware is a frequently discussed topic. To explain this, it is necessary to start with a brief overview of how developers or sellers generate firmware.

Developers usually start by creating a project, such as my [GitHub project](https://github.com/kilmu1337/pcileech-rtl8188ee-wifi-emul). After that, they can continuously generate firmware simply by changing the DNA ID. Some sellers typically have only one project and keep generating firmware from it, but they claim that each firmware is unique, which is nothing more than a scam.

In fact, Pooled Firmware is a false proposition. It only applies to certain projects where a seller generates network card firmware for customers with the same MAC address and DSN. Since all emulations originate from real existing devices, it is impossible for a network card to have both the same MAC address and DSN simultaneously. This allows AC (Anti-Cheat) to determine that it is DMA.

For non-network card firmware, there is no MAC address or DSN, making it difficult to determine if it is DMA unless it is widely recognized by most AC systems worldwide.

---

### What is `1:1 Firmware`?
1:1 Firmware means that the configuration space is identical to that of a real device.

---

### What is `Interrupts`? 

Interrupts can be viewed using projects like drvscan. People often jokingly say that "firmware is breathing"  XD because interrupts make the device appear active, making it behave more like a real device.

---

### How to distinguish between `DATA Port` and `JTAG Port`?

Typically, there will be markings on the DMA card. If there are none, generally, the port closest to the gold finger is the JTAG port, while the one farthest from it is the DATA port.

---







