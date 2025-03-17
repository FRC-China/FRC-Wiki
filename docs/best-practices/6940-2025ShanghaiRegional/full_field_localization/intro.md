# 全场定位技术

6940 2025年的全场定位技术仅通过一个 Limelight 3G 便实现了5cm的误差，我们从2023年初便开始研究全场定位，并最终在今年见证这个技术达到相对成熟。6941 今年的机器也使用了相近的技术。

## 技术概述

具体而言，我们在机器上安装了一个 Limelight 3G ，使用 Pigeon2 的 yaw 数据传入给 Limelight 并获取其 Megatag2 的定位数据，随后以tag在视野中的范围占比（ta）传入我们预先测量好的线性插值表，获得对应的devision数据，并以之作为参数，和Megatag2定位以及延迟一同传入给ctre生成swerve的pose estimate系统中。以获取精确的视觉定位

## 木桶般的精密系统

全场定位是一个精密而复杂的系统，涉及到底盘，视觉，陀螺仪，代码等各个层面。也因此，经常听到有队伍抱怨系统中的某个部分不够好而导致自己的定位不精准，例如声称自己的 limelight 不够新，底盘太老。

但事实是，单纯更换其中的一部分，例如将 Limelight 3 升级成 Limelight 3G  ，并不能让定位的精度有质的飞越。

与木桶理论类似，**决定全场定位质量的往往不是系统中最卓越的那个部分，而是最糟糕的那个部分**。只有保证体系中的每个部分都达到正常运转，才能完全发挥出每个部分的实力，实现一个相对精准的全场定位。这种观点在类似的其他系统中也成立。

## 默认你知道的内容

本章节默认阅读者有一定的代码基础，只讲解相应的代码思路。若对本章所提及的名词有不了解的，可以分别阅读[wpilib文档](https://docs.wpilib.org/en/stable/docs/zero-to-robot/introduction.html)、[limelight文档](https://docs.limelightvision.io/docs/docs-limelight/getting-started/summary)以及[CTRE 文档](https://v6.docs.ctr-electronics.com/en/stable/)来获取对应信息。
