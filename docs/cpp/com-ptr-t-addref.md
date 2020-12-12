---
description: 了解详细信息： _com_ptr_t：： AddRef
title: _com_ptr_t::AddRef
ms.date: 11/04/2016
f1_keywords:
- _com_ptr_t::AddRef
helpviewer_keywords:
- AddRef method [C++], interface pointers
ms.assetid: c104dac3-aad3-40bb-a298-75c6cd0e63a2
ms.openlocfilehash: 0979245662a94596307b1a63af918d0ce67c7b6f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97295687"
---
# <a name="_com_ptr_taddref"></a>_com_ptr_t::AddRef

**Microsoft 专用**

`AddRef` `IUnknown` 在封装的接口指针上调用的成员函数。

## <a name="syntax"></a>语法

```cpp
void AddRef( );
```

## <a name="remarks"></a>备注

调用 `IUnknown::AddRef` 封装的接口指针， `E_POINTER` 如果指针为 NULL，则引发错误。

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[_com_ptr_t 类](../cpp/com-ptr-t-class.md)
