---
description: 了解详细信息：链接器工具警告 LNK4092
title: 链接器工具警告 LNK4092
ms.date: 11/04/2016
f1_keywords:
- LNK4092
helpviewer_keywords:
- LNK4092
ms.assetid: d569ec47-a338-40e1-940b-8a8061459acb
ms.openlocfilehash: 6ef835981a8ed7921147697d6ed9fc79ceeb7033
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97210005"
---
# <a name="linker-tools-warning-lnk4092"></a>链接器工具警告 LNK4092

共享的可写节 "section" 包含重定位;图像可能无法正确运行

当你有共享部分时，链接器将发出此警告，以便警告你潜在的严重问题。

在多个进程之间共享数据的一种方法是将节标记为 "shared"。 但是，将节标记为共享可能会导致问题。 例如，你有一个 DLL，它在共享数据部分中包含如下所示的声明：

```
int var = 1;
int *pvar = &var;
```

链接器无法解析 `pvar` ，因为它的值取决于 dll 加载到内存中的哪个位置，因此它将重定位记录置于 dll 中。 当 DLL 加载到内存中时， `var` 可以解析和分配的地址 `pvar` 。 如果其他进程加载同一 DLL 但无法在同一地址加载它，则 `var` 将为第二个进程更新地址的重定位，第一个进程的地址空间将指向错误的地址。
