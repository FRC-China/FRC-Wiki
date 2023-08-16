本部分我们将按照下图所示完成接线，使用USB-B转USB线连接主板和电脑，然后按照如下步骤连接剩余电路。

![Pasted image 20230504204056](https://github.com/ZhangzrJerryGithub/FRC-Wiki/assets/142400625/b15ac9d4-1631-48aa-a6de-5fc1c0e7c85f)

##### 1. 连接开关与线缆

如下图所示在开关接线柱处放入垫圈和线鼻子，再拧紧螺母即可。

![Pasted image 20230504204133](https://github.com/ZhangzrJerryGithub/FRC-Wiki/assets/142400625/bb643b19-19f4-4a30-b253-7744c615e52c)



##### 2. 插入配电板的保险丝

如下图所示向配电板插入保险丝，不需要区分保险丝的正负极。

![Pasted image 20230504204133](https://github.com/ZhangzrJerryGithub/FRC-Wiki/assets/142400625/754b2922-ad98-44cb-8143-7f32fbbbc968)



##### 3. 连接主板和配电板

如下图所示按下接口，即可插入或取出线缆，注意火线与零线之间不要被多余铜丝短接。

![Pasted image 20230504204133](https://github.com/ZhangzrJerryGithub/FRC-Wiki/assets/142400625/953e2420-ba54-4129-b644-4f46fb6cab33)


如下图所示，用小号一字螺丝批拧松主板电源接口侧面的螺丝，即可插入或拔出线缆，同样的安装时需要注意火线与零线之间不要被多余铜丝短接。

![Pasted image 20230504204316](https://github.com/ZhangzrJerryGithub/FRC-Wiki/assets/142400625/85c6ca0d-37ef-4b64-8c7b-208c473bfa82)


4. **连接电池和开关**

如下图所示对准两个安德森插头后直接插入即可，拆除时向两侧用力拔出。

![Pasted image 20230504204347](https://github.com/ZhangzrJerryGithub/FRC-Wiki/assets/142400625/ed0b07ae-0ba7-43a7-9cf6-d2e118fbe190)

5. **检查电路并闭合开关**

如下图所示，需要闭合开关时将RESET旋钮拨入，需要断开开关时按下凸起的按钮即可。

![Pasted image 20230504204347](https://github.com/ZhangzrJerryGithub/FRC-Wiki/assets/142400625/672b2354-78de-49ff-9607-2318d80cc088)

#### 三  使用FRC DRIVER STATION连接主板

1. 首先从官网 [https://www.ni.com/zh-cn/support/downloads/drivers/download.frc-game-tools.html#479842](https://www.ni.com/zh-cn/support/downloads/drivers/download.frc-game-tools.html#479842) 下载`FRC Game Tools`安装包，推荐点击离线安装下载光盘映像文件。

2. 下载完成后参考 [https://docs.wpilib.org/en/stable/docs/zero-to-robot/step-2/labview-setup.html#starting-install](https://docs.wpilib.org/en/stable/docs/zero-to-robot/step-2/labview-setup.html#starting-install) 所述设置和步骤完成安装。

3. 打开安装完成的`FRC Driver Station`应用程序，如图8所示设置队号后即可连接主板。
> **Warning**
> 在使用`FRC Driver Station`时，注意不要随意按下空格键，否则机器将进入紧急停止状态，此时需要重启主板才能再次连接。

### 四  使用Visual Studio Code部署程序

1. 首先从官网 https://code.visualstudio.com/Download 下载最新版本的`Visual Studio Code`编辑器并完成安装。

2. 打开`Visual Studio Code`编辑器，按下键盘`Ctrl+Shift+X`打开拓展侧边栏，输入`WPILib`并搜索安装。 ![Pasted image 20230504204750](https://github.com/ZhangzrJerryGithub/FRC-Wiki/assets/142400625/793d886f-6093-4be2-bea2-b5561d47d982)

 
3. WPILib插件安装完成后，点击右上方W标志或在键盘输入Ctrl+Shift+P打开命令输入框，输入`create a new project`并选择`WPILib: Create a new project`进入项目创建界面。![Pasted image 20230504204750](https://github.com/ZhangzrJerryGithub/FRC-Wiki/assets/142400625/9a8038c6-11f3-4369-a347-e3301a5b2ce4)

 
4. 在项目创建界面依次填入项目类型（样例或模板）、编程语言、项目目录、项目名称和队号后。其中项目样例给出了许多程序示例，包括但不限于：基础底盘程序、I2C通信程序、手柄遥控程序等。本实验中，选择空的模板程序完成创建项目即可。![Pasted image 20230504204813](https://github.com/ZhangzrJerryGithub/FRC-Wiki/assets/142400625/7479addd-fd57-4a7d-bb6b-23b88e312f7b)
 
5. 创建项目后点击右上角的`···`;并点击`Deploy Robot Code`即可部署程序，此时可以在`FRC Driver Station`中点击`Enabled`以运行程序或点击`Disabled`以暂停程序。![Pasted image 20230504204813](https://github.com/ZhangzrJerryGithub/FRC-Wiki/assets/142400625/2d502c78-e31f-4a10-a7f9-513a058b22e9)

#### 五  用路由器连接主板
1. 如图所示，断开开关后在电路中连入稳压器和路由器。![Pasted image 20230504204813](https://github.com/ZhangzrJerryGithub/FRC-Wiki/assets/142400625/74805da4-949d-4315-a8a7-80426a66a6d3)

2. 闭合开关后，在电脑无线局域网中连接名字为8811的路由器，如路由器尚未设置名称的可参考 https://docs.wpilib.org/en/stable/docs/controls-overviews/control-system-software.html#frc-radio-configuration-utility-windows-only 完成设置。

3. 路由器连接成功后，参考步骤二的方法连接主板。

#### 六  关于主板的更多操作
1. 为主板烧录固件
2. 为主板设置队号
3. 为主板设置名称
