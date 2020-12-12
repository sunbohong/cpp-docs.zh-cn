---
description: 了解详细信息： _variant_t 类
title: _variant_t 类
ms.date: 11/04/2016
f1_keywords:
- _variant_t
helpviewer_keywords:
- _variant_t class [C++], operators
- _variant_t class
- _variant_t class [C++], member functions
- VARIANT object
- VARIANT object [C++], COM encapsulation
ms.assetid: 6a3cbd4e-0ae8-425e-b4cf-ca0df894c93f
ms.openlocfilehash: e720d78e6f7fd22fc369d4b39804260892e235c1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97116608"
---
# <a name="_variant_t-class"></a>_variant_t 类

**Microsoft 专用**

**_Variant_t** 对象封装 `VARIANT` 数据类型。 类可管理资源分配和释放，并根据需要对和进行函数调用 `VariantInit` `VariantClear` 。

### <a name="construction"></a>建筑

| 名称 | 描述 |
|--|--|
| [_variant_t](../cpp/variant-t-variant-t.md) | 构造一个 **_variant_t** 对象。 |

### <a name="operations"></a>操作

| 名称 | 描述 |
|--|--|
| [附加](../cpp/variant-t-attach.md) | `VARIANT`将对象附加到 **_variant_t** 对象。 |
| [清除](../cpp/variant-t-clear.md) | 清除封装的 `VARIANT` 对象。 |
| [ChangeType](../cpp/variant-t-changetype.md) | 将 **_variant_t** 对象的类型更改为指定的 `VARTYPE` 。 |
| [分离](../cpp/variant-t-detach.md) | `VARIANT`从此 **_variant_t** 对象分离封装的对象。 |
| [SetString](../cpp/variant-t-setstring.md) | 为此 **_variant_t** 对象分配一个字符串。 |

### <a name="operators"></a>运算符

| 名称 | 描述 |
|--|--|
| [Operator =](../cpp/variant-t-operator-equal.md) | 将新值分配给现有的 **_variant_t** 对象。 |
| [operator = =，！ =](../cpp/variant-t-relational-operators.md) | 比较两个 **_variant_t** 对象是否相等或不相等。 |
| [Extractors](../cpp/variant-t-extractors.md) | 从封装的对象中提取数据 `VARIANT` 。 |

**结束 Microsoft 专用**

## <a name="requirements"></a>要求

**标头：**\<comutil.h>

**Lib：** comsuppw.lib 或 comsuppwd.lib (参阅 [/zc： Wchar_t (Wchar_t 是本机类型)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md) 有关详细信息) 

## <a name="see-also"></a>请参阅

[编译器 COM 支持类](../cpp/compiler-com-support-classes.md)
