# 程序概述

## 什么是 WPILib？

WPILib 是一个提供给参赛队伍来为机器编写程序的标准库。WPILib 含有一系列实用的类和现成的程序，可以用于驱动 FRC 控制系统中的许多部件（如传感器、电调等），也有其他的实用功能。

## 支持的语言

WPILib 有两个版本，各对应了一个 FRC 官方支持的语言：WPILibJ 是 Java 版本，而 WPILibC 是 C++ 版本。

同时维护这两个库并不轻松，因为只有当一个特性在 Java 库和 C++ 库中都被很好地支持时，它才会被添加到正式版的库中。同时，两个特性的命名也会尽可能地靠近。

### 我应该如何选择语言？

事实上，两者的学习难度都不高，C++ 能够提供更好的性能而 Java 需要手写的部分则较少。

Java 一直是 FRC 中较为主流的编程语言。

## 源代码和说明文档

WPILib 是一个开源项目，源代码在其 [GitHub](https://github.com/wpilibsuite/allwpilib) 页面可见。

- [WPILibJ](https://github.com/wpilibsuite/allwpilib/tree/main/wpilibj/src/main/java/edu/wpi/first/wpilibj)
- [WPILibC](https://github.com/wpilibsuite/allwpilib/tree/main/wpilibc/src/main/native/cpp)

官方也分别为它们编写了两个说明文档：

- [Java](https://github.wpilib.org/allwpilib/docs/release/java/)
- [C++](https://github.wpilib.org/allwpilib/docs/release/cpp/)
