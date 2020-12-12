---
description: 了解详细信息： _com_ptr_t：:D etach
title: _com_ptr_t::Detach
ms.date: 11/04/2016
f1_keywords:
- _com_ptr_t::Detach
helpviewer_keywords:
- Detach method [C++]
ms.assetid: 0652053e-af37-44e9-a278-2522212ebfed
ms.openlocfilehash: ec2a18a04b8c32e373225235fd0d6f520e768af0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97295505"
---
# <a name="_com_ptr_tdetach"></a>_com_ptr_t::Detach

**Microsoft 专用**

提取并返回封装的接口指针。

## <a name="syntax"></a>语法

```
Interface* Detach( ) throw( );
```

## <a name="remarks"></a>备注

提取并返回封装的接口指针，然后将封装的指针存储清除为 NULL。 这将从封装中移除接口指针。 你需要 `Release` 在返回的接口指针上调用。

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[_com_ptr_t 类](../cpp/com-ptr-t-class.md)
