# Limelight设置

关于如何使用 limelight 在[官方的手册](https://docs.limelightvision.io/docs/docs-limelight/getting-started/summary)里以已经写得相当简洁明了了，在此只点明和全场定位相关的注意事项。

## 镜头对焦

与历届 limelight 不同，limelight 3G 拥有手动对焦的能力，在购买后请务必将其置于 tag 前，调节镜头直到视野清晰，官方手册声称需要使用胶带固定镜头，但从使用体验上来说，6940 认为不使用胶带固定也不会影响精度，不恰当地使用胶水和透明胶可能反而会导致视野模糊以及仪器损坏。

## 参数调节

与全场定位相关的参数主要有4个，其中：

1. Resolution 决定视野分辨率，越高越好。
2. Sensor gain 决定传感器的供电电压，越高视野越亮，但是噪点就越多。
3. Exposure 决定传感器的曝光时间，越高视野越亮，但是动态模糊越严重
4. Detector downscale 决定机器将多少个像素并为一个进行tag识别计算，越高帧率越高，但是识别准确度越低
反之帧率则低，但是识别准确度高。

按照6940使用 limelight 的经验，应当先在tag面前调节Sensorgain 和 Exposure ，在保证视野清晰的情况下调节 Sensor gain 和 Exposure 。随后调节 Detector downscale **使得帧率稳定在20FPS左右**，可以满足全场定位的数据需求。

## 镜头校准

在官方的手册中，Limelight 官方曾经声称 Limelight 在出场时已经经历过校准，无需额外校准，但这是无稽之谈，Limelight 现已更改他们的手册。**请务必在对焦后使用ChArUco板校准 Limelight 以修正视野边缘的畸变。**

## Limelight 位置设定

精确地输入 Limelight 镜头相对于机器中心的位置对 Limelight 的反解定位对至关重要，请务必精确地在CAD中测量 Limelight 的朝向并确保其与实际安装保持一致。
