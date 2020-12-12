---
description: 了解详细信息： _variant_t：： ChangeType
title: _variant_t::ChangeType
ms.date: 11/04/2016
f1_keywords:
- _variant_t::ChangeType
- _variant_t.ChangeType
helpviewer_keywords:
- ChangeType method [C++]
- VARIANT object [C++], ChangeType
- VARIANT object
ms.assetid: 829d2eeb-3338-4a88-9dce-0ca145f47aac
ms.openlocfilehash: 32ce43f1d9afb388c97e5271927113c71d31bb92
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97116621"
---
# <a name="_variant_tchangetype"></a>_variant_t::ChangeType

**Microsoft 专用**

将对象的类型更改 `_variant_t` 为指定的 `VARTYPE` 。

## <a name="syntax"></a>语法

```cpp
void ChangeType(
   VARTYPE vartype,
   const _variant_t* pSrc = NULL
);
```

#### <a name="parameters"></a>parameters

*vartype*<br/>
`VARTYPE`此对象的 `_variant_t` 。

*.Psrc*<br/>
指向要转换的 `_variant_t` 对象的指针。 如果此值为 NULL，则转换就地执行。

## <a name="remarks"></a>备注

此成员函数将 `_variant_t` 对象转换为指定的 `VARTYPE` 。 如果 *.psrc* 为 NULL，则会就地执行转换，否则，此 `_variant_t` 对象将从 *.psrc* 复制，然后转换。

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[_variant_t 类](../cpp/variant-t-class.md)
