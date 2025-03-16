# Flash Tool Link
 [https://github.com/kilmu1337/DMA-Flash-Tools](https://github.com/kilmu1337/DMA-Flash-Tools) 

# Step
1, **Download** "DMA-Flash-Tools" on second pc(radar pc) then **Extract** the downloaded file. After extraction, there will be three subdirectories: `Flash Tools`,` ch347 driver needed`, `rs232 driver needed`.

2, **Insert** the DMA card into the PCIe slot of the main pc(game pc). Power on the main pc to supply power to the card. Note that for cards with a switch, the switch must be turned on.

3, Use a USB-type C cable to connect the **jtag** port of the DMA card to the second pc. (Generally, the port close to the motherboard, near the gold fingers, is the jtag port.)

**4, Place the firmware (.bin file) into the `Flash Tools` folder!**

5, First, click on the `rs232 driver needed` folder and double-click to **open zadig-2.5.exe**. Then, select **Options -> List All Devices**, and open the dropdown menu below to view its contents. At this point, there are a few possible situations:

![Image](https://github.com/user-attachments/assets/4a64d90e-7ced-4255-ad4e-0dab8616e0ea)

- [1] **First situation:** If **Quad RS232-HS(Interface 0)** appears in the dropdown menu, select it and click Install Driver or Replace Driver. Note that you must select "Interface 0" and avoid selecting the wrong one.

![Image](https://github.com/user-attachments/assets/6f3094fb-437f-4cc8-b509-b30fad6c4025)

After the driver installation is complete, go to the Flash Tools folder and double-click the `#####flash_rs232_35t#####.bat` script. The correct flashing process should display many lines like "sector xx took xxxms," where the number before "ms" should range from tens to hundreds (if it shows single digits or 0ms, close it and reopen until the ms value is normal). Then, at the last sector, it will pause for a moment, and after that, "success" will appear, indicating that the flashing is complete.

Once the flashing is complete, **main pc** must **shut down and cut off the power**, then power it on again (do not directly click restart).

---


- [2] **Second situation:** If **Single RS232-HS** appears in the dropdown menu, select it and click Install Driver or Replace Driver. 

![Image](https://github.com/user-attachments/assets/fd1a689a-a369-4dac-86f4-c2193e2ef045)

After the driver installation is complete, go to the Flash Tools folder and double-click the `#####flash_rs232_75t#####.bat` script. The correct flashing process should display many lines like "sector xx took xxxms," where the number before "ms" should range from tens to hundreds (if it shows single digits or 0ms, close it and reopen until the ms value is normal). Then, at the last sector, it will pause for a moment, and after that, "success" will appear, indicating that the flashing is complete.

Once the flashing is complete, **main pc** must **shut down and cut off the power**, then power it on again (do not directly click restart).

- [3] **Third situation:** If **USB To UART+JTAG(Interface 0)** appears in the dropdown menu. 

![Image](https://github.com/user-attachments/assets/e2c1c606-fbe6-4528-b6b1-4bf02eac846d)

In this situation, you need to close zadig-2.5.exe, go back to the `ch347 driver needed` directory, then double-click **SETUP.EXE** in the `CH341PAR` folder and click install to complete the installation of the programming port driver.

After the driver installation is complete:

If you are using the **75T** DMA card, go to the `Flash Tools` folder and double-click the `#####flash_ch347_75t#####.bat` script. The correct flashing process should display many lines like "sector xx took xxxms," where the number before "ms" should range from tens to hundreds (if it shows single digits or 0ms, close it and reopen until the ms value is normal). Then, at the last sector, it will pause for a moment, and after that, "success" will appear, indicating that the flashing is complete.

If you are using the **35T** DMA board, go to the Flash Tools folder and double-click the `#####flash_ch347_35t#####.bat` script. The correct flashing process should display many lines like "sector xx took xxxms," where the number before "ms" should range from tens to hundreds (if it shows single digits or 0ms, close it and reopen until the ms value is normal). Then, at the last sector, it will pause for a moment, and after that, "success" will appear, indicating that the flashing is complete.

