---
description: 了解详细信息： _variant_t：： Attach
title: _variant_t::Attach
ms.date: 11/04/2016
f1_keywords:
- _variant_t::Attach
- _variant_t.Attach
helpviewer_keywords:
- Attach method [C++]
- VARIANT object [C++], attach
- VARIANT object
ms.assetid: 2f02bd08-2306-4477-aa88-d2a5dee2b859
ms.openlocfilehash: de13b1e8138eb24971e52165ee84fc92d97ca3d9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97116647"
---
# <a name="_variant_tattach"></a>_variant_t::Attach

**Microsoft 专用**

`VARIANT`将对象附加到 **_variant_t** 对象。

## <a name="syntax"></a>语法

```cpp
void Attach(VARIANT& varSrc);
```

#### <a name="parameters"></a>parameters

*varSrc*<br/>
`VARIANT`要附加到此 **_variant_t** 对象的对象。

## <a name="remarks"></a>备注

`VARIANT`通过封装来获取的所有权。 此成员函数将释放任何现有 `VARIANT` 的封装，然后复制所提供的 `VARIANT` ，并将其设置 `VARTYPE` 为 VT_EMPTY，以确保其资源只能由 **_variant_t** 析构函数释放。

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[_variant_t 类](../cpp/variant-t-class.md)
