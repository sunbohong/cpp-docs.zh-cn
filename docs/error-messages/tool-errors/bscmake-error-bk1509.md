---
description: 了解详细信息： BSCMAKE 错误 BK1509
title: BSCMAKE 错误 BK1509
ms.date: 11/04/2016
f1_keywords:
- BK1509
helpviewer_keywords:
- BK1509
ms.assetid: 53df7037-1913-4b63-b425-c0bf44081792
ms.openlocfilehash: c78a9bf1243d2d11220aea2580a6a786d9ad29a6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97322916"
---
# <a name="bscmake-error-bk1509"></a>BSCMAKE 错误 BK1509

堆空间不足

BSCMAKE 用尽了内存，包括虚拟内存。

### <a name="to-fix-by-using-the-following-possible-solutions"></a>使用以下可能的解决方案进行修复

1. 释放一些磁盘空间。

1. 增加交换文件的大小。

1. 增加 Windows 交换文件的大小。

1. 减少内存 BSCMAKE 要求，方法是使用/Ei 或/Es 消除某些输入文件，或使用/Em 消除宏正文。
