# 结构设计

本机器的climber采用的是改造现成丝杠的设计，非常好地规避了传统的telescope的海量维护问题。
现成丝杠参考：<https://item.taobao.com/item.htm?spm=a21n57.1.0.0.69d2523cYuOP1g&id=692504254455&ns=1&abbucket=17#detail>

## 动力改造

显然，我们不能直接使用电推杆上面的电机，这并不是合法的FRC电机，所以我们需要进行一系列操作来把电机换成falcon或者其他电机。

具体地，我们使用金属打印打印了一个模数为0.8、内部为falcon花键的齿轮，我们拆开齿轮箱，把原有电机拆下，并换上falcon（很巧的是，电推杆原有的固定孔和falcon的固定孔是恰好匹配的）最后再将齿轮直接套上去，就完成了动力系统的改造。

拆开的齿轮箱：
![微信图片_20230807172703.jpg](https://img1.imgtp.com/2023/08/07/IDPZX1Y5.jpg)

金属打印齿轮：

![捕获.PNG](https://img1.imgtp.com/2023/08/07/G5ahVcRV.PNG)

## 结构固定

如果你仔细观察电推杆，你会意识到电推杆上只有两端有两个最基本的固定点，这并不能很好的满足我们爬杆的需求。这也是为什么我们使用钣金抱箍来满足我们额外的固定需求。
![捕获.PNG](https://img1.imgtp.com/2023/08/07/Vp6vkS2E.PNG)

在末端，我们将方管套在伸缩杆上来固定我们climber的钩子：

![捕获.PNG](https://img1.imgtp.com/2023/08/07/U329uOAB.PNG)

最后装上去的效果是这个样子的：

[![pPEgC8I.md.jpg](https://s1.ax1x.com/2023/08/07/pPEgC8I.md.jpg)](https://imgse.com/i/pPEgC8I)
