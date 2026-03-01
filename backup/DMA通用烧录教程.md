# 项目地址
 [https://github.com/kilmu1337/DMA-Flash-Tools](https://github.com/kilmu1337/DMA-Flash-Tools) 
Discord： [https://discord.gg/KilmuDMA](https://discord.gg/KilmuDMA) 

如果上面的github下载不了，点击下面的蓝奏云下载到 **副机** 

https://wwvu.lanzouq.com/i8JvA2dcatfc

# 步骤

1，DMA板子插到主机的pcie槽里，主机开机给板子供电，注意带开关的板子要打开开关。

2，用Usb-typeC线连接DMA板子的烧录口和副机。（一般靠近主板，也就是靠近金手指那个口是烧录口）

3，将上面下载的文件在副机解压出来，解压之后有三个子目录，分别是 **Flash Tools** ， **ch347 driver needed** ， **rs232 driver needed** 

4，
将固件（.bin文件）放到**Flash Tools**文件夹内！
将固件（.bin文件）放到**Flash Tools**文件夹内！
将固件（.bin文件）放到**Flash Tools**文件夹内！

5，先点击 **rs232 driver needed** 这个文件夹，双击打开 **zadig-2.5.exe** ，依次选择 **Options** -> **List All Devices** , 然后点开下方的下拉栏，查看下拉栏中的内容，这时候有几种情况：

- [1] 第一种情况：下拉栏中有 **Quad RS232-HS(Interface 0)** ，选择它并点击 **Install Driver** 或者 **Replace Driver** ，这里注意要选择 **”Interface 0“** ，别选错了。
 
![rs232-35t.png](https://github.com/user-attachments/assets/6f3094fb-437f-4cc8-b509-b30fad6c4025)

驱动安装完之后，到 **Flash Tools** 文件夹中双击 **#####flash_rs232_35t#####.bat** 这个脚本，正确的烧录过程应该是会出现很多sector xx took xxxms，ms前的数字应该是个几十到几百的范围（如果是个位数甚至0ms、1ms，请关闭并重新打开，直到sector后面ms正常为止），然后在最后一个sector会卡一下，之后出现success就是烧录完成

烧录完成后必须关机断电，然后开机(不要直接点重启)




- [2] 第二种情况：下拉栏中有 **Single RS232-HS** ，选择它并点击 **Install Driver** 或者 **Replace Driver** 
![rs232-75t.png](https://github.com/user-attachments/assets/fd1a689a-a369-4dac-86f4-c2193e2ef045)

驱动安装完之后，到 **Flash Tools** 文件夹中双击 **#####flash_rs232_75t#####.bat** 这个脚本，正确的烧录过程应该是会出现很多sector xx took xxxms，ms前的数字应该是个几十到几百的范围（如果是个位数甚至0ms、1ms，请关闭并重新打开，直到sector后面ms正常为止），然后在最后一个sector会卡一下，之后出现success就是烧录完成

烧录完成后必须关机断电，然后开机(不要直接点重启)

- [3] 第三种情况：下拉栏中出现 **USB To UART+JTAG(Interface 0)** 
![m2nnd415.png](https://github.com/user-attachments/assets/e2c1c606-fbe6-4528-b6b1-4bf02eac846d)

这种情况需要关闭zadig-2.5.exe，返回到**ch347 driver needed**目录下，再双击 **CH341PAR** 目录下的 **SETUP.EXE** ，点击安装来完成烧录口驱动的安装。

驱动安装完之后：
如果你是75T的DMA板子，到 **Flash Tools** 文件夹中双击 **#####flash_ch347_75t#####.bat** 这个脚本，正确的烧录过程应该是会出现很多sector xx took xxxms，ms前的数字应该是个几十到几百的范围（如果是个位数甚至0ms、1ms，请关闭并重新打开，直到sector后面ms正常为止），然后在最后一个sector会卡一下，之后出现success就是烧录完成

如果你是35T的DMA板子，到 **Flash Tools** 文件夹中双击 **#####flash_ch347_35t#####.bat** 这个脚本，正确的烧录过程应该是会出现很多sector xx took xxxms，ms前的数字应该是个几十到几百的范围（如果是个位数甚至0ms、1ms，请关闭并重新打开，直到sector后面ms正常为止），然后在最后一个sector会卡一下，之后出现success就是烧录完成