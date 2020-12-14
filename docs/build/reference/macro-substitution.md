---
description: 了解更多：宏替换
title: 宏替换
ms.date: 11/04/2016
helpviewer_keywords:
- NMAKE program, macro substitution
- macros, NMAKE
- substitution macros in NMAKE
ms.assetid: 47465cfe-fd92-49db-aebe-7c2d7ecceb73
ms.openlocfilehash: 5e1531afb210b4671632bca2540bfc7562653139
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97199176"
---
# <a name="macro-substitution"></a>宏替换

调用 *macroname* 时，在其定义字符串中出现的每个 *string1* 都替换为 *string2*。

## <a name="syntax"></a>语法

```
$(macroname:string1=string2)
```

## <a name="remarks"></a>备注

宏替换区分大小写，并且是文本; *string1* 和 *string2* 无法调用宏。 替换不会修改原始定义。 除了之外，你还可以在任何预定义的宏中替换文本 [$$@](filename-macros.md) 。

冒号前面没有空格或制表符;冒号后的任何解释为文本。 如果 *string2* 为 null，则将从宏的定义字符串中删除 *string1* 的所有匹配项。

## <a name="see-also"></a>请参阅

[使用 NMAKE 宏](using-an-nmake-macro.md)
