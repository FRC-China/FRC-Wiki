# poseEstimator 更新

我们今年采用的是 CTRE 的生成底盘代码，其定位似乎相对 wpilib 更为准确，且不需要手动将底盘的 position 传入 poseestimator 。建议各位队伍采纳。但类似的算法在 wpilib 自带的 poseestimaor 中也适用，我们在24年季后赛用的就是 wpilib 的 swerve 框架

## 上传底盘朝向数据

Limelight 的 MegaTag2 需要使用底盘的朝向来进一步过滤定位代码。请不要忘记在代码里上传朝向，否则获取的 Megatag2 定位会变得很奇怪。具体代码如下：

```java
LimelightHelpers.SetRobotOrientation(RobotContainer.m_Limelight, getPose().getRotation().getDegrees(), 0, 0, 0, 0, 0);//一般只用传yaw即可
```

## megaTag2 数据获取

请特别注意，Limelight 的获取 Megatag2 定位的代码和获取 Megatag1的代码是不同的:

```java
LimelightHelpers.PoseEstimate mt2 = LimelightHelpers.getBotPoseEstimate_wpiBlue_MegaTag2(RobotContainer.m_Limelight);//注意这个_MegaTag2的后缀，不要漏了
```

## 动态权重

poseEstimator大多要求传入视觉的权重来决定如何用视觉数据修正底盘位置。为了实现最好的修正效果，我们使用了线性插值表建立了 ta 和devision的映射关系，从而实现了视觉的动态权重。这保证机器在靠近tag的时候视觉可以快速修正底盘的位置。而在远离tag的时候又不至于过分相信tag的跳动的数据。

Wpilib有自带的线性插值表类，直接调用即可，具体代码如下：

```java
        //初始化插值表与插值表上的点
        public static final InterpolatingDoubleTreeMap tAtoDev = new InterpolatingDoubleTreeMap();

        public static final Point2D[] tAtoDevPoints = {
            new Point2D.Double(0.17, 0.08),
            new Point2D.Double(0.12, 0.20),
            new Point2D.Double(0.071, 0.35),
            new Point2D.Double(0.046, 0.4),
        };
```

```java
//把点插入插值表
public static void initializeConstants()
{
    for(var p : PoseEstimatorConstants.tAtoDevPoints)
       PoseEstimatorConstants.tAtoDev.put(p.getX(), p.getY());
}
```

## 视觉更新

在最后进行视觉更新时，需要格外注意：

1. Limelight megatag2 使用了底盘的 yaw 作为其的返回朝向的 yaw 并以此过滤底盘的坐标，如果这时候再用 Limelight 传回的 yaw 反过去修正底盘的 yaw 可能会出现朝向偏移等奇异现象，因此请务必在视觉更新时将 yaw 的devision设为接近无限大。
2. 不要使用 Limelight 获取的 tl 来计算 timestamps ，而是直接使用 limelighthelper 返回的 pose estimate 中的 timestampSeconds 数据。
3. 记得特判 limelight helper 返回的 estimate 为 null 的情况，否则可能会出现 NullPointer 等问题
4. 在tag距离机器过远或机器高速旋转时放弃更新，否则可能会导致数据不准。

我们视觉更新的完整代码如下：

```java
    public void updateOdometry(){
        LimelightHelpers.SetRobotOrientation(RobotContainer.m_Limelight, getPose().getRotation().getDegrees(), 0, 0, 0, 0, 0);
        LimelightHelpers.PoseEstimate mt2 = LimelightHelpers.getBotPoseEstimate_wpiBlue_MegaTag2(RobotContainer.m_Limelight);
        // ImprovedLL.MT2stddevs devs = ImprovedLL.getmt2Devs();
        // ImprovedLL.mt2stdDev stdDev = ImprovedLL.getmt2Dev(RobotContainer.m_Limelight); 
        if(mt2 == null) {
            DriverStation.reportWarning(RobotContainer.m_Limelight + " Diconnected!", false);
            return;
        }

        if (Math.abs(getSpeeds().omegaRadiansPerSecond) <= 4*Math.PI 
            && mt2.tagCount > 0 
            && mt2.avgTagDist < 4 
            && Math.hypot(getSpeeds().vxMetersPerSecond, getSpeeds().vyMetersPerSecond) < 2
        ) {
            addVisionMeasurement(mt2.pose,
                Utils.fpgaToCurrentTime(mt2.timestampSeconds),
                VecBuilder.fill(PoseEstimatorConstants.tAtoDev.get(mt2.avgTagArea), PoseEstimatorConstants.tAtoDev.get(mt2.avgTagArea), 100000000)
                // VecBuilder.fill(0.00001,0.00001, 100000000.)
                // VecBuilder.fill(devs.xdev, devs.ydev, 100000000.)
            );
            SmartDashboard.putNumber("tA", mt2.avgTagArea );
            SmartDashboard.putNumber("Dev",
            PoseEstimatorConstants.tAtoDev.get(mt2.avgTagArea));
        }
        
    }
```
