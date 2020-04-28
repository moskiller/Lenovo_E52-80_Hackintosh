# Lenovo_E52-80_Hackintosh


### 电脑配置

|规格|	|详细信息|
|:----:| |:----:|
|电脑型号|	|联想 昭阳 E52-80 笔记本电脑|
|操作系统|	|macOS Catalina 10.15.4(19E287)|
|处理器|	|英特尔 酷睿 i5 - 7200U|
|内存|	|8GB DDR4 2133MHz|
|硬盘| |SSD 128G STATIII接口|
|显卡|	|Intel HD Graphics 620|
|显示器|	|15.5 英寸 FHD 1366x768|
|声卡|	|Realtek ALC236|
|网卡| |原Intel3165NGW无解，更换为 Dell DW1820A(08KF4)|



### 引导方案
Clover


### 安装教程 : 略，请自行上网搜索

### 镜像下载 : [黑果小兵的部落阁] :【黑果小兵】原版镜像



### 更新日志

哪些可以工作得更好

因目前休眠无法正常唤醒 , 为避免影响到睡眠 , 终端使用以下命令关闭休眠
sudo pmset -a hibernatemode 0
开启 HIDPI 来提升系统 UI 质量 , 终端使用以下命开启或关闭 HIDPI
bash -c "$(curl -fsSL https://raw.githubusercontent.com/daliansky/Lenovo-Air13-IWL-Hackintosh/master/Advanced/hidpi-zh.sh)"
安装 ALCPlugFix 来修复 3.5 mm 耳麦切换异常问题
Windows 和 MacOS 蓝牙设备双系统共用
OpenCore 菜单部分 常见问题
OpenCore 使用原生苹果 启动磁盘 ( BootCamp ) 切换双系统
鸣谢

Acidanthera 提供 OpenCore 和 相关驱动
Sniki 提供 EAPD-Codec-Commander
al3xtjames 提供 NoTouchID
alexandred 提供 VoodooI2C
宪武 提供 OC-little
