---
description: 了解详细信息： _variant_t：： SetString
title: _variant_t::SetString
ms.date: 11/04/2016
f1_keywords:
- _variant_t::SetString
helpviewer_keywords:
- SetString method [C++]
ms.assetid: 816b08e5-6830-46ca-b3d7-7689308b3be3
ms.openlocfilehash: a36bab9189b6046325bb275469dc9dbdb495fc7a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97161411"
---
# <a name="_variant_tsetstring"></a>_variant_t::SetString

**Microsoft 专用**

将字符串分配给此 `_variant_t` 对象。

## <a name="syntax"></a>语法

```cpp
void SetString(const char* pSrc);
```

#### <a name="parameters"></a>parameters

*.Psrc*<br/>
指向字符串的指针。

## <a name="remarks"></a>备注

将 ANSI 字符串转换为 Unicode `BSTR` 字符串并将其分配给此 `_variant_t` 对象。

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[_variant_t 类](../cpp/variant-t-class.md)
