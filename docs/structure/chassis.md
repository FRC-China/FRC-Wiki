# 底盘

### 基础概念

FRC 机器人中的底盘主要由金属构件支撑，分为两种：**直轮底盘**和**全向底盘**。

### 直轮底盘（官底）

直轮底盘（Train Drive）是指底盘上的轮胎方向不会改变，通过左右两侧轮胎速度差，或麦克纳姆轮的几何转动来完成转向。这样的底盘可以通过履带坦克的例子来类比。

![AndyMark officially provided Train Drive](https://s2.loli.net/2023/05/31/3btdeaojIfGXVpS.jpg)

> Source: AndyMark[^ref1]. 上图是 AndyMark 公司提供的直轮底盘，由于该公司是 FIRST 官方所声明的赞助商，直轮底盘亦被称之为「官底」，即“官方底盘”。

直轮底盘在2020年及以前应用甚广，如 118、971 等外国强队都在官底的设计理念之上更新了齿轮箱、轮组，从而达到更佳的效果。以下列出部分轮组升级产品。

![Omni Wheels](https://s2.loli.net/2023/05/31/Hpcyz3rkDVTdeMJ.png)
![Pneumatic Rubber Wheels](https://s2.loli.net/2023/05/31/LYxj9baTeOvnmAD.jpg)

> Source: REV Robotics[^ref2]. 上图分别是 Omni 万向轮、充气高摩擦力橡胶轮，他们相较于官底配置有了极大性能提升。

此外，部分队伍还采用了麦克纳姆轮（Mecanum wheels）来实现类似效果。麦轮的优势在于节省传动空间，且机动性更高。而劣势在于麦轮抓地力不可观，在 2023 赛季中难以爬上斜坡，因此其应用并不广泛。

![typical Mecanum Drive](https://s2.loli.net/2023/05/31/anUYFieEkjSgVh4.png)

![Principals of Mecanum Operations](https://s2.loli.net/2023/05/31/Knp5YzS2Oq1hEfd.png)

> Source: Wikipedia[^ref3]. 上图分别是典型的麦轮底盘设计与麦轮驱动原理图。极高的转向灵活性必然带来抓地力的牺牲。

### 万向底盘

万向底盘（Swerve Drive Train）是通过改变底盘轮胎的方向来改变方向的底盘。我们通过实例图片来理解其原理。

![SDS MK4i Swerve Module](https://s2.loli.net/2023/05/31/r5QDKoOIWlMtyfk.webp)

> Source: Swerve Drive Specialties[^ref4]. 上图是较新版本的 Swerve 全向底盘部件。一个底盘共有 4 个完全相同的 Swerve 模块，本图仅展示了其一作展示之用。

一个 Swerve 模块通常包含两个电机（motors），上图展示的是 Falcon 电机，现实中亦可使用 775 电机。其中一个电机带动轮胎滚动，另一个负责转向。由此，Swerve 实现了万向功能。

![Orbit 1690 Swerve](https://s2.loli.net/2023/05/31/uvn4XAlQfwOoEWZ.jpg)

> Source: Chief Delphi / Team 1690 Orbit[^ref5]. 上图是 Swerve 模块完全安装在底盘铝方管上时的样子。
## 参考资料与注释

[^ref1]: [6 Wheel Drop Center Robot Drive Base](https://www.andymark.com/products/am14u4-kit-of-parts-chassis)

[^ref2]: [ION Omni Wheels](https://www.revrobotics.com/ION-Omni-Wheels/)

[^ref3]: [Mecanum wheel](https://en.wikipedia.org/wiki/Mecanum_wheel)

[^ref4]: [MK4i Swerve Module](https://www.swervedrivespecialties.com/products/mk4i-swerve-module)

[^ref5]: [1690 Swerve Drive 2019 off season project](https://www.chiefdelphi.com/t/1690-swerve-drive-2019-off-season-project/369008)