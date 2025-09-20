## 概述

参考[2910原图](https://cad.onshape.com/documents/200d496f92b5d826aad151ee/w/1313cedebc6b3a548a2453f9/e/45250e5d3ac033df739d7215)

Endeffector可以处理Algae和Coral，功能有：地吸筒，接Loading station筒，放L1-L4，拨球，吸球，放Barge，放Processor。Endeffector有两排水平轮和两排竖直轮，4个CANRange传感器，负责感知Coral的状态。Endeffector与Extension连接处有一个Wrist，提供了更大的自由度。由2个Kraken X44驱动两排竖直轮，1个Kraken X60驱动两排水平轮，另有一个Kraken X44驱动Wrist。

![](https://s21.ax1x.com/2025/09/18/pVh3xkn.png)

## 结构设计

Endeffector通过很小的体积和重量实现了Coral和Algae的抓取。底部两排竖直滚轮负责抓取Coral，下排水平兼顾了Coral和Algae，上排水平轮负责吸取和拨出Algae。

Coral

Endeffector吸取Coral时要先选择L1状态还是L2-L4状态，L1吸筒时，筒是水平的；L2-L4吸筒时，筒是垂直的。达到目标状态的吸筒依靠差速来实现。

Endeffector有4个CANRange传感器，1个在两排竖直轮中间，而剩下3个靠外的左中右，检测Coral位置，并根据传感器数据动态调整两个蓝色轮子转速，用差速实现Coral吸取达到L1状态还是L2-L4状态。

两排竖直轮用2个Kraken X60电机驱动，左右结构相同。

Algae

两排水平轮中间留足间隙，一个Kraken X60电机驱动两排水平轮，吸Algae时给满电压12V，利用Algae的形变量来夹持。特别的是，上下两排水平轮转动方向始终相反，不仅是便于单电机控制，而且在放L1和L2的同时能够拨掉Reef上的球，这对于资格赛这种冲RP局的效率带来很大提升。

两排水平轮都利用塞打螺栓设计了快拆结构，便于调试时随时更换胶轮的软硬。

Wrist

Endeffector的wrist可以做到180°的转弯，由一个Kraken X44驱动，从而实现前后面都可以放筒，这样地吸筒之后，不用转向，可以直接自瞄得分，极大缩短cycle时间。

![](https://s21.ax1x.com/2025/09/18/pVhYBnO.png)

Endeffector出现过的问题是胶轮的软硬不当。2025季后赛赛程中间疑似换过一批Algae，新的Algae更硬，原先水平滚轮的排布组合无法夹持住新的Algae，我们不断更换胶轮的硬度，但是会影响到地吸筒的效果，最终吸球功能没有调到最佳效果。