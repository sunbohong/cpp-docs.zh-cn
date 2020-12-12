---
description: 了解更多：资源编译器错误 RW1025
title: 资源编译器错误 RW1025
ms.date: 11/04/2016
f1_keywords:
- RW1025
helpviewer_keywords:
- RW1025
ms.assetid: 561a02af-e7e0-442a-8ad3-a00b2ca1b62e
ms.openlocfilehash: 40404f8d6dc16b73f93255a18ce8c632cc1e014a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97237187"
---
# <a name="resource-compiler-fatal-error-rw1025"></a>资源编译器错误 RW1025

超出最大堆内存

检查可能占用过多空间的内存驻留软件。 使用 CHKDSK 程序来找出有多少内存。

如果要创建大资源文件，请将资源脚本拆分为两个文件。 创建两个 .res 文件后，使用 MS-DOS 命令行将它们联接在一起：

```
copy first.res /b + second.res /b full.res
```
