---
description: 了解更多：资源编译器警告 RC4093
title: 资源编译器警告 RC4093
ms.date: 11/04/2016
f1_keywords:
- RC4093
helpviewer_keywords:
- RC4093
ms.assetid: 3c61b4a4-b418-465b-a4fd-cb1ff0adb8dd
ms.openlocfilehash: 40f4777bb62fc2a5e434a4a365cdd027a04ffafd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97237083"
---
# <a name="resource-compiler-warning-rc4093"></a>资源编译器警告 RC4093

非活动代码的字符常量中的非转义换行符

`#if`、 `#elif` 、 **#Ifdef** 或 **#ifndef** 预处理器指令的常量表达式的计算结果为零，使得代码处于非活动状态。 在该非活动代码中，换行符出现在一组单引号或双引号内。

所有文本直到下一个双引号被视为在字符常量内。
