# 控制程序

球路的自动供球由2个输入，2个输出组成，blocker由shooter系统单独控制，不算在自动供球系统中。

尽管直接设计球路的供球逻辑可能没有那么简单，但是考虑到只有两个 DigitalInput ，我们可以采取直接枚举的方式来撰写控制逻辑。

![标注了轮子传动的6940机器](https://r2.img.cdn.loliloli.net/19d48d1c0382158a62dfb072681f2190/2025/02/08/LIh9C.md.png)

![简单的自动供球](https://r2.img.cdn.loliloli.net/19d48d1c0382158a62dfb072681f2190/2025/02/08/LI0Dy.md.png)

以下是控制代码节选（UpFront 和 UpBack 都是蓝色部分的控制，只不过这个部分有两个不同的电机）：

AutofeedCommand:

```java
    if(!RobotContainer.m_Hopper.NoBallOnBottom()&&!RobotContainer.m_Hopper.NoBallOnTop())
    {
      RobotContainer.m_Hopper.SetBottomOutput(0);
      RobotContainer.m_Hopper.SetUpFrontOutput(0);
      RobotContainer.m_Hopper.SetUpBackOutput(0);
    }
    else if(RobotContainer.m_Hopper.NoBallOnBottom()&&!RobotContainer.m_Hopper.NoBallOnTop())
      {
        RobotContainer.m_Hopper.SetBottomOutput(HopperConstants.HopperOutput);
        RobotContainer.m_Hopper.SetUpBackOutput(0);
        RobotContainer.m_Hopper.SetUpFrontOutput(0);
      
      
      }
    else if(!RobotContainer.m_Hopper.NoBallOnBottom()&&RobotContainer.m_Hopper.NoBallOnTop())
    {
      RobotContainer.m_Hopper.SetBottomOutput(HopperConstants.HopperOutput);
      RobotContainer.m_Hopper.SetUpFrontOutput(HopperConstants.HopperOutput);
      RobotContainer.m_Hopper.SetUpBackOutput(HopperConstants.HopperOutput);
    }
    else
    {
      RobotContainer.m_Hopper.SetBottomOutput(HopperConstants.HopperOutput);
      RobotContainer.m_Hopper.SetUpFrontOutput(0);
      RobotContainer.m_Hopper.SetUpBackOutput(0);

    }
```

值得一提的是，这种控制逻辑下，在没有球的情况下，底部的同步带会一直维持高速旋转，会浪费大量电池电量并导致电压下降，可以通过在球路前部新增传感器来优化球路的控制逻辑。

还有一个比较坑的地方， roborio 的 digitalinput 逻辑非常的诡异，当有电压输入的时候返回 false ，没有电压输入的时候会返回 true ，与 arduino 的逻辑恰恰相反，各位编写程序的时候要额外注意。
