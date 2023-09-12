# 常用软件概述

FRC 软件系列是为了帮助你进行设计、开发和调试机器人代码而设计的，同时也可以用于操作机器人和排错时提供反馈。本节将会一一进行一些简单的介绍。

## 兼容性

这些软件主要在 Windows 操作系统上被支持，所有的软件都确定能够支持 Windows 10 和 Windows 11，其中一些软件也支持 macOS 和 Linux 操作系统。

这意味着参赛队伍可以在任何兼容的操作系统上完成编程和开发的操作，而只需在 Windows 电脑上使用诸如 Driver Station、roboRIO Imaging Tool 一类只支持 Windows 系统的软件。

## LabVIEW FRC

LabVIEW FRC 是基于最新的 LabVIEW 版本上修改的特别版本，在三个 FRC 官方支持的编程语言之列。这是一个图形化的、以数据流为中心的编程语言。其中使用到的图块称作 VI，通过一些传输数据的线相连。

你可以通过 Kickoff Kit 中的光盘安装它，也可以直接在线下载。

官方的说明文档和安装指南请[点击此处](https://docs.wpilib.org/en/stable/docs/zero-to-robot/step-2/labview-setup.html#installing-labview-for-frc-labview-only)。

## WPILib VSCode

WPILib VSCode 是集成了 WPILib 的插件的 Visual Studio Code。它可以用于进行 Java 和 C++ 的程序编写。这两者在 FRC 中应用是都是面向对象的。

关于如何安装、配置的官方指南请[点击此处](https://docs.wpilib.org/en/stable/docs/zero-to-robot/step-2/wpilib-setup.html#wpilib-installation-guide)。

## FRC Driver Station powered by NI LabVIEW

这是唯一一个可以用于比赛时控制机器人的软件，能够将通过各种方式输入的数据发送到你的机器人上，且有许多可以用于调试机器的工具。

需要更多信息请[点击此处](https://docs.wpilib.org/en/stable/docs/software/driverstation/driver-station.html#frc-driver-station-powered-by-ni-labview)。

## Dashboard

### LabVIEW Dashboard

这是 FRC Driver Station 默认启动的一个展示板，它可以通过一系列内置的功能展示出机器人的状态。

需要更多信息请[点击此处](https://docs.wpilib.org/en/stable/docs/software/dashboards/labview-dashboard/driver-station-labview-dashboard.html#frc-labview-dashboard)。

### SmartDashboard

SmartDashboard 能够以各种自定义的方式展示出你想要的信息。

需要更多信息请[点击此处](https://docs.wpilib.org/en/stable/docs/software/dashboards/smartdashboard/index.html#smartdashboard)。

### ShuffleBoard

ShuffleBoard 的特性和 SmartDashboard 非常相似。除此以外，它用一个更加现代的方式和界面设计提升了数据处理效率，可视化界面也更加精细。

需要更多信息请[点击此处](https://docs.wpilib.org/en/stable/docs/software/dashboards/shuffleboard/index.html#shuffleboard)。

### Glass

Glass 是一个专为调试而设计的展示板。

它最突出的优势是可以在场地视图中看到车子的位置，还有一系列先进的图表工具。

Glass 的文档在 [WPILib Docs](https://docs.wpilib.org/en/stable/docs/software/dashboards/glass/index.html#glass) 上。

### LiveWindow

LiveWindow 是 SmartDashboard 和 ShuffleBoard 的一个特性，专用于和 Driver Station 中的测试模式。

用户可以通过它看到传感器等传回的原始数据。

需要更多信息请[点击此处](https://docs.wpilib.org/en/stable/docs/software/dashboards/smartdashboard/test-mode-and-live-window/index.html#smartdashboard-test-mode-and-live-window)。

### FRC roboRIO Imaging Tool

这个软件是用于格式化和配置 roboRIO 的。

具体操作请查看[安装指南](https://docs.wpilib.org/en/stable/docs/zero-to-robot/step-2/frc-game-tools.html#installing-the-frc-game-tools)和[官方文档](https://docs.wpilib.org/en/stable/docs/zero-to-robot/step-3/imaging-your-roborio.html)。

### FRC Radio Configuration Utility

FRC Radio Configuration Utility 是用于在自己调试时配置标准场控的工具。这个工具能通过合适的设置模拟 FRC 赛场上的真实体验。

你可以[点击此处](https://docs.wpilib.org/en/stable/docs/zero-to-robot/step-3/radio-programming.html#programming-your-radio)下载安装器。

### FRC Driver Station Log Viewer

该软件是用于查看 Driver Station 产生的日志的。在日志中，你可以找到一些数据来了解刚刚赛场上机器某些特定行为的原因。

需要更多信息请[点击此处](https://docs.wpilib.org/en/stable/docs/software/driverstation/driver-station-log-viewer.html#driver-station-log-file-viewer)。

### RobotBuilder

RobotBuilder 是用于辅助建立一个 Command-Based 程序项目的软件，能够以图形化（树形结构）的方式配置用到的 Subsystems 和执行器。之后它将会生成一个模板程序，你可以基于它继续完善代码。

需要更多信息请[点击此处](https://docs.wpilib.org/en/stable/docs/software/wpilib-tools/robotbuilder/index.html#robotbuilder)。

### Robot Simulation

机器模拟器给参赛队伍提供了一个在虚拟环境中验证机器代码的方式。你可以在 WPILib VSCode 中直接启动这个模拟器和一个 2D 的场地图。

需要更多信息请[点击此处](https://docs.wpilib.org/en/stable/docs/software/wpilib-tools/robot-simulation/introduction.html#introduction-to-robot-simulation)。

### FRC LabVIEW Robot Simulator

它和上一个软件类似，但是包含在 LabVIEW FRC 程序中。

需要更多信息请[点击此处](https://forums.ni.com/t5/FIRST-Robotics-Competition/LabVIEW-Tutorial-10-Robot-Simulation/ta-p/3739702?profile.language=en)。

### PathWeaver

PathWeaver 能让参赛队伍以很简单的方式生成并配置自动阶段的路线。路线由较平滑的曲线构成，让机器人能够快速地在场上的两点间移动。

需要更多信息请[点击此处](https://docs.wpilib.org/en/stable/docs/software/pathplanning/pathweaver/introduction.html#introduction-to-pathweaver)。

### System Identification

这个工具能够自动计算出机器人的程序会用到的物理数据，如运动模拟、PID 控制参数等等。

需要更多信息请[点击此处](https://docs.wpilib.org/en/stable/docs/software/pathplanning/system-identification/introduction.html#introduction-to-system-identification)。

### OutlineViewer

它是一个在调试时用于查看、修改和增加 NetworkTable 中内容的工具。使用 LabVIEW FRC 的队伍可以通过多个 LabVIEW Dashboard 中的标签页完成同样的操作。

需要更多信息请[点击此处](https://docs.wpilib.org/en/stable/docs/software/wpilib-tools/outlineviewer/index.html#outlineviewer)。