---
description: 了解详细信息： _bstr_t：： GetBSTR
title: _bstr_t::GetBSTR
ms.date: 11/04/2016
f1_keywords:
- _bstr_t::GetBSTR
helpviewer_keywords:
- GetBSTR method [C++]
ms.assetid: 0c62ff16-4433-4183-a03c-d5a0a9b731ef
ms.openlocfilehash: ced985bb5123d86ff119279fc49a2b4d181ba8b3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97229296"
---
# <a name="_bstr_tgetbstr"></a>_bstr_t::GetBSTR

**Microsoft 专用**

指向 `BSTR` 包装的 `_bstr_t` 的开头。

## <a name="syntax"></a>语法

```
BSTR& GetBSTR( );
```

## <a name="return-value"></a>返回值

`BSTR` 包装的 `_bstr_t` 的开头。

## <a name="remarks"></a>备注

**GetBSTR** 影响 `_bstr_t` 共享的所有对象 `BSTR` 。 多个 `_bstr_t` 可 `BSTR` 通过使用复制构造函数和 **运算符 =** 来共享。

## <a name="example"></a>示例

有关使用 **GetBSTR** 的示例，请参阅 [_Bstr_t：： Assign](../cpp/bstr-t-assign.md) 。

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[_bstr_t 类](../cpp/bstr-t-class.md)
