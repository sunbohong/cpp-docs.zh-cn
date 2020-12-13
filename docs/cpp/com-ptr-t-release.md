---
description: 了解详细信息： _com_ptr_t：： Release
title: _com_ptr_t::Release
ms.date: 11/04/2016
f1_keywords:
- _com_ptr_t.Release
- _com_ptr_t::Release
helpviewer_keywords:
- Release method [C++]
ms.assetid: db448b34-0efa-4f02-b701-ad1ca3ae6ca5
ms.openlocfilehash: a1b81295ab249b1826ea6d373f782d91765df3b7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97344713"
---
# <a name="_com_ptr_trelease"></a>_com_ptr_t::Release

**Microsoft 专用**

在封装的接口指针上调用的 **Release** 成员函数 `IUnknown` 。

## <a name="syntax"></a>语法

```cpp
void Release( );
```

## <a name="remarks"></a>备注

调用 `IUnknown::Release` 封装的接口指针， `E_POINTER` 如果此接口指针为 NULL，则引发错误。

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[_com_ptr_t 类](../cpp/com-ptr-t-class.md)
