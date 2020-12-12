---
description: 了解详细信息： _bstr_t：： Attach
title: _bstr_t::Attach
ms.date: 11/04/2016
f1_keywords:
- _bstr_t::Attach
helpviewer_keywords:
- Attach method [C++]
ms.assetid: 8cad867e-40fc-435b-841f-0d412c2f58d3
ms.openlocfilehash: b3f29c8eaf81a492f7e3c4282227d3d6d246988e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97229426"
---
# <a name="_bstr_tattach"></a>_bstr_t::Attach

**Microsoft 专用**

将 `_bstr_t` 包装器链接到 `BSTR`。

## <a name="syntax"></a>语法

```cpp
void Attach(
   BSTR s
);
```

#### <a name="parameters"></a>参数

*s*<br/>
要与之关联或分配到的 `BSTR`，即 `_bstr_t` 变量。

## <a name="remarks"></a>备注

如果 `_bstr_t` 以前被附加到了另一个 `BSTR`，并且没有其他 `_bstr_t` 变量使用 `BSTR`，`_bstr_t` 将清理 `BSTR` 资源。

## <a name="example"></a>示例

有关使用 **Attach** 的示例，请参阅 [_Bstr_t：： Assign](../cpp/bstr-t-assign.md) 。

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[_bstr_t 类](../cpp/bstr-t-class.md)
