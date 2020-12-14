---
description: 了解详细信息：编译器警告 (等级 1) C4325
title: 编译器警告（等级 1）C4325
ms.date: 08/27/2018
f1_keywords:
- C4325
helpviewer_keywords:
- C4325
ms.assetid: 8127a08c-d626-481b-aa7b-04a3fdc9a9ec
ms.openlocfilehash: 17e14d4909e4b76d6a0a71d6e77fad1d01e3f41b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97311586"
---
# <a name="compiler-warning-level-1-c4325"></a>编译器警告（等级 1）C4325

> 已忽略标准节 "*section*" 的属性

## <a name="remarks"></a>备注

不能更改标准节的属性。 例如：

```cpp
#pragma section(".sdata", long)
```

这会覆盖使用数据类型的 `.sdata` 数据类型的标准部分 **`short`** **`long`** 。

不能更改其属性的标准部分包括、

- 。数据

- .sdata

- bss

- 。 .sbss

- .text

- . const

- .sconst

- 。 rdata

- .srdata

稍后可能会添加其他部分。

## <a name="see-also"></a>请参阅

[区](../../preprocessor/section.md)
