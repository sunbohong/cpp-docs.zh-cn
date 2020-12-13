---
description: 了解详细信息： isinf
title: isinf
ms.date: 01/31/2019
f1_keywords:
- isinf
- math/isinf
helpviewer_keywords:
- isinf function
ms.openlocfilehash: f174855ddbb8cc43fd7338d4254c0f03bf53967d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97332639"
---
# <a name="isinf"></a>isinf

确定浮点值是否为无穷值。

## <a name="syntax"></a>语法

```C
int isinf(
   /* floating-point */ x
); /* C-only macro */

template <class FloatingType>
inline bool isinf(
   FloatingType x
) throw(); /* C++-only template function */
```

### <a name="parameters"></a>parameters

*x*<br/>
要测试的浮点值。

## <a name="return-value"></a>返回值

 **`true`** 如果参数 *x* 为正无穷或负无穷，则 Isinf 将返回 c + + 代码中的非零值 () 。  **`false`** 如果参数是有限的或 NAN，则 Isinf 将在 c + + 代码中返回 0 () 。 正常和次正常浮点值都被视为有限值。

## <a name="remarks"></a>备注

在编译为 C 时， **isinf** 是一个宏，在编译为 c + + 时为内联模板函数。

## <a name="requirements"></a>要求

|函数|必需的标头 (C)|必需的标头 (C++)|
|--------------|---------------------------|-------------------------------|
|**isinf**|\<math.h>|\<math.h> 或 \<cmath>|

有关兼容性的详细信息，请参阅[兼容性](../../c-runtime-library/compatibility.md)。

## <a name="see-also"></a>请参阅

[浮点支持](../../c-runtime-library/floating-point-support.md)<br/>
[fpclassify](fpclassify.md)<br/>
[_fpclass、_fpclassf](fpclass-fpclassf.md)<br/>
[isfinite、_finite、_finitef](finite-finitef.md)<br/>
[isnan、_isnan、_isnanf](isnan-isnan-isnanf.md)<br/>
[isnormal](isnormal.md)<br/>
