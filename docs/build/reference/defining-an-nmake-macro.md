---
description: 了解详细信息：定义 NMAKE 宏
title: 定义 NMAKE 宏
ms.date: 11/04/2016
helpviewer_keywords:
- macros, NMAKE
- defining NMAKE macros
- NMAKE macros, defining
ms.assetid: 45aae451-9d33-4a3d-8799-2e0cae17070d
ms.openlocfilehash: 133e05cac2a236a38f6b2d1e719f1b66fd73760d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97201633"
---
# <a name="defining-an-nmake-macro"></a>定义 NMAKE 宏

## <a name="syntax"></a>语法

```

macroname=string
```

## <a name="remarks"></a>备注

*Macroname* 是字母、数字和下划线的组合)  (_ 最多1024个字符，并且区分大小写。 *Macroname* 可以包含一个已调用的宏。 如果 *macroname* 完全由一个被调用的宏组成，则被调用的宏不能为 null 或未定义。

`string`可以是零个或多个字符的任意序列。 空字符串包含零个字符或只有空格或制表符。 `string`可以包含宏调用。

## <a name="what-do-you-want-to-know-more-about"></a>你想进一步了解什么？

[宏内的特殊字符](special-characters-in-macros.md)

[null 宏和未定义的宏](null-and-undefined-macros.md)

[定义宏的位置](where-to-define-macros.md)

[宏定义中的优先级](precedence-in-macro-definitions.md)

## <a name="see-also"></a>请参阅

[宏和 NMAKE](macros-and-nmake.md)
