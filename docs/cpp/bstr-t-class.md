---
title: _bstr_t 类
ms.date: 11/04/2016
f1_keywords:
- _bstr_t
helpviewer_keywords:
- BSTR object
- _bstr_t class
- BSTR object [C++], COM encapsulation
ms.assetid: 58841fef-fe21-4a84-aab9-780262b5201f
ms.openlocfilehash: f521681da10eeda3b8024b0865d5164021296353
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/25/2020
ms.locfileid: "88838706"
---
# <a name="_bstr_t-class"></a>_bstr_t 类

**Microsoft 专用**

`_bstr_t`对象封装[BSTR 数据类型](/previous-versions/windows/desktop/automat/bstr)。 类 `SysAllocString` `SysFreeString` 在适当时通过对和和其他 api 的函数调用来管理资源分配和释放 `BSTR` 。 **_Bstr_t**类使用引用计数来避免开销过大。

### <a name="construction"></a>建筑

| 构造函数 | 说明 |
|--|--|
| [_bstr_t](../cpp/bstr-t-bstr-t.md) | 构造 `_bstr_t` 对象。 |

### <a name="operations"></a>Operations

| 函数 | 说明 |
|--|--|
| [Assign](../cpp/bstr-t-assign.md) | 将 `BSTR` 复制到 `BSTR` 包装的 `_bstr_t` 中。 |
| [附加](../cpp/bstr-t-attach.md) | 将 `_bstr_t` 包装器链接到 `BSTR`。 |
| [copy](../cpp/bstr-t-copy.md) | 构造封装的 `BSTR` 的副本。 |
| [分离](../cpp/bstr-t-detach.md) | 返回 `BSTR` 包装的 `_bstr_t` 并从 `BSTR` 中分离 `_bstr_t`。 |
| [获取地址](../cpp/bstr-t-getaddress.md) | 指向 `BSTR` 包装的 `_bstr_t`。 |
| [GetBSTR](../cpp/bstr-t-getbstr.md) | 指向 `BSTR` 包装的 `_bstr_t` 的开头。 |
| [length](../cpp/bstr-t-length.md) | 返回 `_bstr_t` 中的字符数。 |

### <a name="operators"></a>运算符

| 操作员 | 说明 |
|--|--|
| [operator =](../cpp/bstr-t-operator-equal.md) | 将新值赋给现有 `_bstr_t` 对象。 |
| [运算符 + =](../cpp/bstr-t-operator-add-equal-plus.md) | 将字符附加到 `_bstr_t` 对象的结尾。 |
| [operator +](../cpp/bstr-t-operator-add-equal-plus.md) | 串联两个字符串。 |
| [操作员!](../cpp/bstr-t-operator-logical-not.md) | 检查封装的 `BSTR` 是否为 NULL 字符串。 |
| [operator = =、！ =、 \<, > 、 \<=, >=](../cpp/bstr-t-relational-operators.md) | 比较两个 `_bstr_t` 对象。 |
| [运算符 wchar_t * &#124; char\*](../cpp/bstr-t-wchar-t-star-bstr-t-char-star.md) | 提取指向封装的 Unicode 或多字节 `BSTR` 对象的指针。 |

**结束 Microsoft 专用**

## <a name="requirements"></a>要求

**标头：**\<comutil.h>

**Lib：** comsuppw.lib 或 comsuppwd.lib (参阅 [/zc： Wchar_t (Wchar_t 是本机类型) ](../build/reference/zc-wchar-t-wchar-t-is-native-type.md) 有关详细信息) 

## <a name="see-also"></a>另请参阅

[编译器 COM 支持类](../cpp/compiler-com-support-classes.md)
