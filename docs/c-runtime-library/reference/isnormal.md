---
description: 了解详细信息： isnormal
title: isnormal
ms.date: 01/31/2019
f1_keywords:
- isnormal
- math/isnormal
helpviewer_keywords:
- isnormal function
ms.openlocfilehash: 3afae5196a7a6b2b149028ad347f95baa27b1544
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97337768"
---
# <a name="isnormal"></a>isnormal

确定浮点值是否为正常值。

## <a name="syntax"></a>语法

```C
int isnormal(
   /* floating-point */ x
); /* C-only macro */

template <class FloatingType>
inline bool isnormal(
   FloatingType x
) throw(); /* C++-only function template */
```

### <a name="parameters"></a>parameters

*x*<br/>
要测试的浮点值。

## <a name="return-value"></a>返回值

 **`true`** 如果参数 *x* 既不是零、次正常、无限大，也不是 NaN，则 Isnormal 将返回 c + + 代码中的非零值 () 。 否则， **isnormal** 将 **`false`** 在 c + + 代码) 中 (返回0。

## <a name="remarks"></a>备注

在编译为 C 时， **isnormal** 是宏，而在编译为 c + + 时则是内联函数模板。

## <a name="requirements"></a>要求

|函数|必需的标头 (C)|必需的标头 (C++)|
|--------------|---------------------------|-------------------------------|
|**isnormal**|\<math.h>|\<math.h> 或 \<cmath>|

有关兼容性的详细信息，请参阅[兼容性](../../c-runtime-library/compatibility.md)。

## <a name="see-also"></a>请参阅

[浮点支持](../../c-runtime-library/floating-point-support.md)<br/>
[isfinite、_finite、_finitef](finite-finitef.md)<br/>
[isinf](isinf.md)<br/>
[isnan、_isnan、_isnanf](isnan-isnan-isnanf.md)<br/>
[_fpclass、_fpclassf](fpclass-fpclassf.md)<br/>
