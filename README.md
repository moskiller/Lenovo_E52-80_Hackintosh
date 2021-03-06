# Lenovo E52-80 Hackintosh


### 电脑配置

规格|详细信息
:----:|:----:
电脑型号 |	联想 昭阳 E52-80 笔记本电脑
操作系统 |	macOS Catalina 10.15.4(19E287)
处理器 |	第七代智能英特尔®酷睿™双核处理器 i5-7200U 
内存 |	8GB DDR4 2133MHz (4G*2)
硬盘 | ~~500GB 7200转 2.5" 7mm SATAIII硬盘~~ 升级为 SSD 128G STATIII硬盘
集成显卡 | Intel HD Graphics 620
独立显卡 | AMD Radeon R5 M430 DDR3L 2G
显示器	| 15.6英寸 16:9 HD 1366x768
光驱	| DVD Super-Multi 刻录光驱 
声卡 | Realtek ALC236
摄像头 | 720P HD摄像头
有线网卡 | Realtek8111 100/1000M自适应网卡
无线网卡 | ~~原Intel3165NGW无解，更换为 Dell DW1820A(08KF4)~~ BCM94360CS2+转接卡
读卡器 | 4合1读卡器 (SD, SDHC, SDXC, MMC)
引导方案 | Clover


### 更新日志
* 2020/08/20
  修改了电池补丁文件中的两处错误调用。
* 2020/05/14
放弃DW1820A，更换BCM94360CS2网卡，同时精简少许无用的驱动。 现在是 MacOS + Win10 双系统啦!  EFI在这里[2020-05-14-V2-EFI.zip](https://github.com/moskiller/Lenovo_E52-80_Hackintosh/blob/master/2020-05-14-V2-EFI.zip)
  
* 2020/04/28
第一次上传.    EFI在这里 [2020-4-28-V1-EFI.zip](https://github.com/moskiller/Lenovo_E52-80_Hackintosh/blob/master/2020-4-28-V1-EFI.zip)

  
  

### 正常工作

1. 显卡: 集显　Intel(R) UD Graphics 620正常，Platform-id为：0x59160000，添加DVMT补丁,采用Devices-Properties方法注入； 　独显暂无解，加上性能不佳，已从BIOS中关闭。
2. 电源: 睡眠正常，合盖正常。
3. 亮度调节: 正常，F11减少 F12增加。
4. 蓝牙: ~~采用[headkaze](https://www.insanelymac.com/forum/profile/1364628-headkaze/)提供的kext，固件为V7 4689， 可工作，但不稳定, AirDrop、handoff、Apple Watch解锁等功能都可用。~~ 更换为BCM94360CS2，免驱，所有功能正常，包括AirDrop、handoff、Apple Watch解锁等。
5. Wifi: ~~DW1820A(08KF4) NGFF M.2接口，不用屏蔽引脚，直接免驱，采用Devices-Properties方法注入: pci-aspm-default	 0 就可以了~~ 同上，更换后免驱、免注入任何属性。
6. USB: 采用 Hackintool 定制，正常使用。
7. 声卡: 型号为ALC236，注入ID：3，使用AppleALC仿冒，顺利加载；
8. 有线网卡: 使用 Realtek8111.kext
9. 摄像头: 正常
10. 触摸板: 采用自己修改过的 ApplePS2SmartTouchPad.kext 驱动，支指2、3、4指，较完美。
11. 电池: 已打DSDT补丁，可正常显示电量。
12. 睡眠：其它 ACPI 补丁修复采用 hotpatch 方式，文件位于 /CLOVER/ACPI/patched。

### 已知问题
1. SD 读卡器 不能用
2. 指纹功能 不能用
3. ~~睡眠唤醒后，偶有键盘失灵，需要重启电脑~~ 定制USB后，基本正常，测试中。
4. ~~Apple Watch解锁功能，只在第一次解锁时是正常的，之后就不能再解锁了，原因不明。~~ 更换为BCM94360CS2后，真香！




### 安装教程 : 略，请自行上网搜索

### 镜像下载 :  [【黑果小兵】macOS Catalina 10.15.4 19E287 正式版 with Clover 5112原版镜像[双EFI版][UEFI and MBR]](https://blog.daliansky.net/macOS-Catalina-10.15.4-19E266-Release-version-with-Clover-5107-original-image-Double-EFI-Version-UEFI-and-MBR.html) 

### 注意事项
安装系统之前，请于BIOS中禁用 WLAN/WIFI 和 Bluetooth，待安装系统成功后再行开启
  
因目前休眠无法正常唤醒 , 为避免影响到睡眠 , 终端使用以下命令关闭休眠
`sudo pmset -a hibernatemode 0`



### 鸣谢(排名不分先后)
[Apple](https://www.apple.com/)的 MacOS  

[RehabMan](https://github.com/rehabman)维护的项目：[OS-X-Clover-Laptop-Config](https://github.com/RehabMan/OS-X-Clover-Laptop-Config)  [Laptop-DSDT-Patch](https://github.com/RehabMan/Laptop-DSDT-Patch) 等  

[headkaze](https://www.insanelymac.com/forum/profile/1364628-headkaze/) 提供的工具：[hackintool](https://github.com/headkaze/Hackintool)  [BrcmPatchRAM](https://www.insanelymac.com/forum/topic/339175-brcmpatchram2-for-1015-catalina-broadcom-bluetooth-firmware-upload/)  

[CloverHackyColor](https://github.com/CloverHackyColor)维护的项目：[CloverBootloader](https://github.com/CloverHackyColor/CloverBootloader)  [CloverThemes](https://github.com/CloverHackyColor/CloverThemes)  

[Acidanthera](https://github.com/acidanthera) 提供的驱动  

[al3xtjames](https://github.com/al3xtjames) 提供 [NoTouchID](https://github.com/al3xtjames/NoTouchID)  

[github.com](https://www.github.com)  

......


