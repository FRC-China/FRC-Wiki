# 控制程序

由于丝杠的自锁特性，我们不需要进行繁琐的 PID 校准，或者担心线轴收线的偏移。我们只需要简单的 percentoutput 就能满足基本的爬升需求。

控制代码节选：

teleoperated period:

```java
if(RobotContainer.m_Controller.getXButton())
{
    RobotContainer.m_Climber.SetClimberOutput(1)
}
else if(RobotContianer.m_Controller.getYButton())
{
    RobotContainer.m_Climber.SetClimberOutput(-1)
}
else
{
    RobotContainer.m_Climber.SetClimberOutput(0)
}
```

ClimberSubSystem:

```java
public void SetClimberOutput(_PCT)
{
    m_ClimberMotor.set(ControlMode.PercentOutput,_PCT);
}
```
