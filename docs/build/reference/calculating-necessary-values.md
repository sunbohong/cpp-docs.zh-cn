---
description: 了解详细信息：计算所需值
title: 计算所需值
ms.date: 11/04/2016
helpviewer_keywords:
- helper functions, calculating necessary values
ms.assetid: 4f037d0f-881a-4a48-a9d2-9f8872dfccb7
ms.openlocfilehash: 92d8462be2db55dbc10375629b133d9286560878
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97179338"
---
# <a name="calculating-necessary-values"></a>计算所需值

延迟 helper 例程需要计算两项关键信息。 为此，在 delayhlp 中有两个用于计算此信息的内联函数。

- 首先计算当前导入到三个不同表中的索引 (导入地址表 (IAT) 、绑定导入地址表 (BIAT) 和未绑定导入地址表 (UIAT) # A7。

- 第二个计算有效 IAT 中的导入数。

```cpp
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

## <a name="see-also"></a>请参阅

[了解 Helper 函数](understanding-the-helper-function.md)
