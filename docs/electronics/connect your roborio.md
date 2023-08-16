
### **实验目标**

1. 学习基本控制电路的搭建

2. 学习电路中的基本接线方式

3. 使用有线连接方式在电脑上使用`FRC Driver Station`软件连接主板

4. 使用路由器连接方式在电脑上使用`FRC Driver Station`软件连接主板

5. 在电脑上使用`FRC Visual Studio Code`软件为主板部署程序

### 实验设备

| **名称** | **全称** | **数量** |
|:---:|:---:|:---:|
| 主板 | NI roboRIO | 1 |
| 配电板 | Power Distribution Panel | 1 |
| 10A保险丝 | 10 Amp Mini Red Fuse | 1 |
| 20A保险丝 | 20 Amp MINI Yellow Fuse | 1 |
| 开关 | 120 Amp Breaker | 1 |
| 路由器 | OM5P\-AC Radio | 1 |
| 稳压器 | Voltage Regulator Module | 1 |
| 网线 | Ethernet Cable | 1 |
| USB转USB\-B | USB A to USB B 2\.0 Cable | 1 |
| 线材 |  | 若干 |

### 实验步骤

#### 一  工具的使用方法

===1. 压线钳的使用===

2. 剥线钳的使用

#### 二  连接主板和电脑

本部分我们将按照图1所示完成接线，使用USB-B转USB线连接主板和电脑，然后按照如下步骤连接剩余电路。

![[Pasted image 20230504204056.png]]
图 1 完整接线示意

##### 1. 连接开关与线缆

如图2所示在开关接线柱处放入垫圈和线鼻子，再拧紧螺母即可。

![[Pasted image 20230504204133.png]]
图 2 安装线鼻并拧紧螺母

##### 2. 插入配电板的保险丝

如图3所示向配电板插入保险丝，不需要区分保险丝的正负极。

![[Pasted image 20230504204225.png]]
图 3 向配电板插入保险丝

##### 3. 连接主板和配电板

如图4所示按下接口，即可插入或取出线缆，注意火线与零线之间不要被多余铜丝短接。

![[Pasted image 20230504204303.png]]
图 4 按下接口插入线缆

如图5所示，用小号一字螺丝批拧松主板电源接口侧面的螺丝，即可插入或拔出线缆，同样的安装时需要注意火线与零线之间不要被多余铜丝短接。

![[Pasted image 20230504204316.png]]
图 5 主板供电接口

4. **连接电池和开关**

如图6所示对准两个安德森插头后直接插入即可，拆除时向两侧用力拔出。

![[Pasted image 20230504204332.png]]
图 6 对接安德森插头

5. **检查电路并闭合开关**

如图7所示，需要闭合开关时将RESET旋钮拨入，需要断开开关时按下凸起的按钮即可。

![[Pasted image 20230504204349.png]]
图 7 闭合开关和断开开关

#### 三  使用FRC DRIVER STATION连接主板

1. 首先从官网 [https://www.ni.com/zh-cn/support/downloads/drivers/download.frc-game-tools.html#479842](https://www.ni.com/zh-cn/support/downloads/drivers/download.frc-game-tools.html#479842) 下载`FRC Game Tools`安装包，推荐点击离线安装下载光盘映像文件。

2. 下载完成后参考 [https://docs.wpilib.org/en/stable/docs/zero-to-robot/step-2/labview-setup.html#starting-install](https://docs.wpilib.org/en/stable/docs/zero-to-robot/step-2/labview-setup.html#starting-install) 所述设置和步骤完成安装。

3. 打开安装完成的`FRC Driver Station`应用程序，如图8所示设置队号后即可连接主板。在使用`FRC Driver Station`时，注意不要随意按下空格键，否则机器将进入紧急停止状态，此时需要重启主板。

### 四  使用Visual Studio Code部署程序

1. 首先从官网 https://code.visualstudio.com/Download 下载最新版本的`Visual Studio Code`编辑器并完成安装。

2. 打开`Visual Studio Code`编辑器，按下键盘`Ctrl+Shift+X`打开拓展侧边栏，输入`WPILib`并搜索安装。 ![[Pasted image 20230504204750.png]]
 
3. WPILib插件安装完成后，点击右上方W标志或在键盘输入Ctrl+Shift+P打开命令输入框，输入`create a new project`并选择`WPILib: Create a new project`进入项目创建界面。![[Pasted image 20230504204759.png]]
 
4. 在项目创建界面依次填入项目类型（样例或模板）、编程语言、项目目录、项目名称和队号后。其中项目样例给出了许多程序示例，包括但不限于：基础底盘程序、I2C通信程序、手柄遥控程序等。本实验中，选择空的模板程序完成创建项目即可。![[Pasted image 20230504204803.png]]![[Pasted image 20230504204813.png]]
 
5. 创建项目后点击右上角的`···`;并点击`Deploy Robot Code`即可部署程序，此时可以在`FRC Driver Station`中点击`Enabled`以运行程序或点击`Disabled`以暂停程序。![[Pasted image 20230504204820.png]]

#### 五  用路由器连接主板
1. 如图所示，断开开关后在电路中连入稳压器和路由器。![[Pasted image 20230504204825.png]]
 
2. 闭合开关后，在电脑无线局域网中连接名字为8811的路由器，如路由器尚未设置名称的可参考 https://docs.wpilib.org/en/stable/docs/controls-overviews/control-system-software.html#frc-radio-configuration-utility-windows-only 完成设置。

3. 路由器连接成功后，参考步骤二的方法连接主板。

#### 六  关于主板的更多操作
1. 为主板烧录固件
2. 为主板设置队号
3. 为主板设置名称
172.22.11.2