---
description: 了解详细信息： _bstr_t：： GetAddress
title: _bstr_t::GetAddress
ms.date: 11/04/2016
f1_keywords:
- _bstr_t::GetAddress
helpviewer_keywords:
- GetAddress method [C++]
ms.assetid: 09bc9180-867e-4ee5-b22a-8339dc663142
ms.openlocfilehash: afb877a6f1b4cfcfb6fe08b36168af745d733b85
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97229309"
---
# <a name="_bstr_tgetaddress"></a>_bstr_t::GetAddress

**Microsoft 专用**

释放所有现有字符串并返回一个新分配的字符串的地址。

## <a name="syntax"></a>语法

```
BSTR* GetAddress( );
```

## <a name="return-value"></a>返回值

指向由 `BSTR` 包装的 `_bstr_t` 的指针。

## <a name="remarks"></a>备注

**GetAddress** 影响 `_bstr_t` 共享的所有对象 `BSTR` 。 多个 `_bstr_t` 可 `BSTR` 通过使用复制构造函数和 **运算符 =** 来共享。

## <a name="example"></a>示例

有关使用 **GetAddress** 的示例，请参阅 [_Bstr_t：： Assign](../cpp/bstr-t-assign.md) 。

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[_bstr_t 类](../cpp/bstr-t-class.md)
