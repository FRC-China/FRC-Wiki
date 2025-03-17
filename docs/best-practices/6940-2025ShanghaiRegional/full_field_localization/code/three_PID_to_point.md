# 3PID移动到定点算法

在拥有了相对精准的全场定位后，如何使用也是一个相对重要的问题。

这是我们代码中的所有底盘自动化的核心算法。我们使用3个 PIDController ，分别控制底盘的X轴移动，Y轴移动，旋转速度。来使得我们的机器可以直线移动到赛场上的任何一个点。这种做法虽然没有直接使用 PathPlanner 的寻路功能要智能，但是其算法高度可控而精准，在赛场上证明了它的可行性。

此外，由于全场定位还是会有相当的误差，我们在实际操作时还会将摇杆输出叠加到目标位点上，为driver保留微调目标位置的空间。

部分代码如下：

```java
    public ChassisSpeeds getHybridMoveToPoseSpeeds(Pose2d pose, ImprovedCommandXboxController driverController, double translationAdjustmentRange, double rotationAdjustmentRangeDegs){
        Pose2d currentPose = getPose();

        //Hybrid Control, read the lines carefully before you tune it
        Transform2d adjustment = new Transform2d(
            driverController.getLeftY()*translationAdjustmentRange * (DriverStation.getAlliance().get() == Alliance.Blue ? 1. : -1.),       //TODO wrong direction
            driverController.getLeftX()*translationAdjustmentRange * (DriverStation.getAlliance().get() == Alliance.Blue ? 1. : -1.),
            Rotation2d.fromDegrees(-driverController.getRightX()*rotationAdjustmentRangeDegs)
        );//获取摇杆输入，并计算微调的数据。
        pose = pose.plus(adjustment);//将微调数据叠加到目标点上
        m_targetPose2d = pose;
        //给三个Controller设置目标点，并获取对应的速度与角速度
        m_rotationController.setSetpoint(pose.getRotation().getRadians());
        m_translationXController.setSetpoint(pose.getX());
        m_translationYController.setSetpoint(pose.getY());

        double targetAngularVelocity = m_rotationController.calculate(currentPose.getRotation().getRadians());
        double targetTranslationXVelocity = m_translationXController.calculate(currentPose.getX());
        double targetTranslationYVelocity = m_translationYController.calculate(currentPose.getY());
        //这段非常重要，如果没有deadband的话机器基本上难逃疯狂的自激振荡，由于 swerve 本来就有锁死功能，到达目标点周围后直接输出0反而避免了PID常见的振荡问题，而且比调试D要简单很多
        if(isAtTranslation(pose.getTranslation())){
            targetTranslationXVelocity = 0.;
            targetTranslationYVelocity = 0.;
        }
        if(isAtRotation(pose.getRotation())) {
            targetAngularVelocity = 0.;
        }

        SmartDashboard.putNumber("targetXVeloUnoptimized", targetTranslationXVelocity);
        SmartDashboard.putNumber("targetYVeloUnoptimized", targetTranslationYVelocity);
        SmartDashboard.putNumber("targetAngularVeloUnoptimized", targetAngularVelocity);

        //这个函数限制了输出的速度和角速度，防止在远离目标点时机器输出一个非常大的数值
        return optimizeMoveToSpeeds(
            new ChassisSpeeds(targetTranslationXVelocity, targetTranslationYVelocity, targetAngularVelocity)
        );
    }
```
