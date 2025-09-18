## 概述

参考[2910原图](https://cad.onshape.com/documents/4f8b5ebe17b3d0225c450bc4/w/f55b41e837709ccca2b57312/e/246023fb3e215358ed4aa9cb)

Pivot两侧各有3个Kraken X60，负责驱动Pivot和Extension。Pivot旋转处是一个巨大的死轴（Dead Axle），死轴两端是两个圆套，取下螺栓，拔下圆套，就可以拆下整个Arm上层。

Pivot是一个巨大的死轴，固定在三角形的基座结构（A-Frame）中。死轴两端是两个圆套，便于快拆。Pviot动力同样由底盘上3个Kraken X60提供，总减速比为120.83:1；动力通过#35链条传递至大直径链盘，提供了超大的扭矩。

![](https://s21.ax1x.com/2025/09/18/pVh3Xwj.png)

## 结构设计

Pivot两侧是两个减速箱，两侧各有3个Kraken X60电机，固定在底盘上很好地降低了机器重心。减速箱很窄，一共只有两个齿轮的厚度。对于减速箱内部的六角轴，我们用是实心1/2Hex轴，在两端用车床导圆角改成1/2ThunderHex尺寸，目的是让两端能进入REV-3197轴承，而中间部分不行，这样轴就被天然地卡在两侧轴承中间。

![](https://s21.ax1x.com/2025/09/18/pVh3jTs.png)
![](https://s21.ax1x.com/2025/09/18/pVhYrHe.png)
![](https://s21.ax1x.com/2025/09/18/pVh3zYq.png)

右侧的减速箱和#35链条负责Pivot传动，最终减速比为120.83：1；左侧的减速箱和#25链条负责Extension的传动，最终减速比为6.28：1。我们尝试了一种新的链条张紧装置，改变的是两个链轮的中心距。既能张紧，也能提供减速比。

![](https://s21.ax1x.com/2025/09/18/pVhY6Nd.png)

Pivot前端有一个最基础的物理限位，限定了Arm下压的最低位置，便于快速归位。

Pivot中间有KickStand，是一根小圆柱，可以卡在Extension0级下方的槽里，后方有弹簧，常态下KickStand靠近Pivot的框架。Kickstand让比赛开始时Extension抬起约45°，确实比赛开始时Extension不超过Frame。

Pivot框架上有灯带，在程序设定上的不同状态里闪不同颜色的灯光，方便DriveTeam判断机器状态。