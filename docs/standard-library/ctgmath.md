---
description: 了解详细信息： &lt; ctgmath&gt;
title: '&lt;ctgmath&gt;'
ms.date: 07/11/2019
f1_keywords:
- <ctgmath>
- ctgmath
helpviewer_keywords:
- ctgmath header
ms.assetid: ff521893-f445-4dc8-a2f6-699185bb7024
ms.openlocfilehash: f1033a944699f4c124114c49e0e30f8b30804a1e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97324690"
---
# <a name="ltctgmathgt"></a>&lt;ctgmath&gt;

实际上，包括 c + + 标准库标头 \<complex> 和 \<cmath> ，它们提供等效于的类型泛型数学宏 \<tgmath.h> 。

> [!NOTE]
> C 标准库 \<tgmath.h> 标头未包含 \<ctgmath> 在中，因为它实际上被和中的 c + + 重载替换 \<complex> \<cmath> 。 这会使 \<ctgmath> 标头冗余。 \<tgmath.h>C + + 中弃用了标头。 \<ctgmath>标头已在 c + + 17 中弃用，并已在草案 c + + 20 标准中删除。

## <a name="requirements"></a>要求

**标头：**\<ctgmath>

**命名空间:** std

## <a name="remarks"></a>备注

C 标准库标头的功能 \<tgmath.h> 由和中的重载提供 \<complex> \<cmath> 。

## <a name="see-also"></a>请参阅

[\<complex>](complex.md)\
[\<cmath>](cmath.md)\
[标头文件引用](cpp-standard-library-header-files.md)\
[C + + 标准库概述](cpp-standard-library-overview.md)\
[C + + 标准库中的线程安全](thread-safety-in-the-cpp-standard-library.md)
