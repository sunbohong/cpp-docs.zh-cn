---
description: 了解详细信息： nullopt_t 结构
title: nullopt_t 结构
ms.date: 08/04/2019
f1_keywords:
- optional/std::nullopt_t
- optional/std::nullopt
ms.openlocfilehash: 7a597dcc5f15843f125dc7572dc4c5694320f0bb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97338113"
---
# <a name="nullopt_t-struct"></a>nullopt_t 结构

`nullopt_t`类型是唯一的空类型，用于指示[可选](optional-class.md)对象不包含值。

类型的常量 `nullopt` `nullopt_t` 指示类型的 `optional` 状态为未初始化。 它可用于初始化 `optional` 对象或与一个对象进行比较。

## <a name="syntax"></a>语法

```cpp
struct nullopt_t;
inline constexpr nullopt_t nullopt{ /*implementation-defined*/ };
```

## <a name="see-also"></a>请参阅

[\<optional>](optional.md)\
[可选类](optional-class.md)
