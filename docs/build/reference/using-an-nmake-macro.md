---
description: 了解更多：使用 NMAKE 宏
title: 使用 NMAKE 宏
ms.date: 11/04/2016
helpviewer_keywords:
- macros, NMAKE
- NMAKE macros, using
ms.assetid: 95c87fbc-76e6-48c0-8536-9bfe179f328e
ms.openlocfilehash: 14a1856b411bf7608b94caacb1b0b078dd1f5577
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97247002"
---
# <a name="using-an-nmake-macro"></a>使用 NMAKE 宏

若要使用宏，请将其名称括在括号中，其前面带有美元符号 ($) ，如下所示。

## <a name="syntax"></a>语法

```
$(macroname)
```

## <a name="remarks"></a>备注

不允许使用空格。 如果 *macroname* 是单个字符，则括号是可选的。 定义字符串将替换 $ (*macroname*) ;未定义的宏替换为空字符串。

## <a name="what-do-you-want-to-know-more-about"></a>你想进一步了解什么？

[宏替换](macro-substitution.md)

## <a name="see-also"></a>请参阅

[宏和 NMAKE](macros-and-nmake.md)
