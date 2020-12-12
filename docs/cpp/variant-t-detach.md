---
description: 了解详细信息： _variant_t：:D etach
title: _variant_t::Detach
ms.date: 11/04/2016
f1_keywords:
- _variant_t::Detach
- _variant_t.Detach
helpviewer_keywords:
- VARIANT object [C++], detatch
- Detach method [C++]
- VARIANT object
ms.assetid: c348ac08-62cf-4657-a16f-974a79c12158
ms.openlocfilehash: 502903f73f9b149a5f85a6eb1be44687aab20664
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97204688"
---
# <a name="_variant_tdetach"></a>_variant_t::Detach

**Microsoft 专用**

从此对象分离封装的 `VARIANT` 对象 `_variant_t` 。

## <a name="syntax"></a>语法

```
VARIANT Detach( );
```

## <a name="return-value"></a>返回值

封装的 `VARIANT` 。

## <a name="remarks"></a>备注

提取并返回封装的 `VARIANT` ，然后清除此 `_variant_t` 对象而不销毁它。 此成员函数 `VARIANT` 从封装中移除，并将 `VARTYPE` 此对象的设置 `_variant_t` 为 VT_EMPTY。 `VARIANT`通过调用[VariantClear](/windows/win32/api/oleauto/nf-oleauto-variantclear)函数，可以释放返回的。

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[_variant_t 类](../cpp/variant-t-class.md)
