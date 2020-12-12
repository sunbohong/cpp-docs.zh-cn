---
description: 了解详细信息： Android 调试器属性
title: 'Android 调试器属性 (c + +) '
ms.date: 10/23/2017
ms.assetid: 789f7a1c-38b4-41d0-809b-14f4d96c8116
f1_keywords:
- VC.Project.AndroidDebugger.DebuggerType
- VC.Project.AndroidDebugger.AndroidDeviceID
- VC.Project.AndroidDebugger.PackagePath
- VC.Project.AndroidDebugger.LaunchActivity
ms.openlocfilehash: 27068b56421860b1e77b6cacf7e2ef4fae147a24
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97136521"
---
# <a name="android-debugger-properties"></a>Android 调试器属性

| Property | 描述 | 选项 |
|--|--|--|
| 调试器类型 | 指定要调试的代码类型。 | **仅限本机**<br /><br />仅限 Java |
| 调试目标 | 指定要用于调试的仿真器或设备。 如果没有正在运行的仿真程序，请使用 "Android 虚拟设备 (AVD) 管理器" 启动设备。 |
| 要启动的包 | 指定要调试的 .apk 的位置。 在调试应用程序时，此选项将启动包 (APK) 。 |
| 启动活动 | 用于启动应用程序的 Android 活动必须与清单中所使用的活动相匹配。 按“应用”从 AndroidManifest.xml 检索列表并动态填充该列表。 |
| 其他符号搜索路径 | 调试符号的其他搜索路径。 |
| 其他 Java 源搜索路径 | Java 源文件的其他搜索路径。 （仅在调试器类型为仅限 Java 时适用。） |
