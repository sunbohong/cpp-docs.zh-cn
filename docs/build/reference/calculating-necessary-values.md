---
description: 了解详细信息：计算延迟加载所需的值
title: 计算延迟加载所需的值
ms.date: 01/19/2021
helpviewer_keywords:
- helper functions, calculating necessary values
ms.openlocfilehash: ae5e0c15b5b13f12fd90c1378a1e449516b55f43
ms.sourcegitcommit: 3d9cfde85df33002e3b3d7f3509ff6a8dc4c0a21
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/21/2021
ms.locfileid: "98667444"
---
# <a name="calculate-necessary-values-for-delay-loading"></a>计算延迟加载所需的值

延迟加载 helper 例程需要计算两项关键信息。 为了帮助，中有两个 *`delayhlp.cpp`* 用于计算此信息的内联函数。

- 第一种是， `IndexFromPImgThunkData` 计算当前导入到三个不同表中的索引 (导入地址表 (IAT) 、绑定导入地址表 (BIAT) 和未绑定导入地址表 (UIAT) # A7。

- 第二个对 `CountOfImports` 有效 IAT 中的导入次数进行计数。

```C
// utility function for calculating the index of the current import
// for all the tables (INT, BIAT, UIAT, and IAT).
__inline unsigned
IndexFromPImgThunkData(PCImgThunkData pitdCur, PCImgThunkData pitdBase) {
    return pitdCur - pitdBase;
    }

// utility function for calculating the count of imports given the base
// of the IAT. NB: this only works on a valid IAT!
__inline unsigned
CountOfImports(PCImgThunkData pitdBase) {
    unsigned        cRet = 0;
    PCImgThunkData  pitd = pitdBase;
    while (pitd->u1.Function) {
        pitd++;
        cRet++;
        }
    return cRet;
    }
```

## <a name="see-also"></a>另请参阅

[了解 Helper 函数](understanding-the-helper-function.md)
