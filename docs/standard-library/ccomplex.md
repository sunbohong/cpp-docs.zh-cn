---
description: 了解详细信息： &lt; ccomplex&gt;
title: '&lt;ccomplex&gt;'
ms.date: 07/11/2019
f1_keywords:
- <ccomplex>
- ccomplex
helpviewer_keywords:
- ccomplex header
ms.assetid: a9fcb5f0-88e3-464b-a5fd-d1afb8cd7e6f
ms.openlocfilehash: d657d7b0b2a203bcbad93ff1c78f6b78eb4d7707
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97325310"
---
# <a name="ltccomplexgt"></a>&lt;ccomplex&gt;

包括 c + + 标准库标头 [\<complex>](complex.md) 。

> [!NOTE]
> C 标准库 \<complex.h> 标头未包含 \<ccomplex> 在中，因为它实际上被和中的 c + + 重载替换 \<complex> \<cmath> 。 这会使 \<ccomplex> 标头冗余。 \<complex.h>C + + 中弃用了标头。 \<ccomplex>标头已在 c + + 17 中弃用，并已在草案 c + + 20 标准中删除。

## <a name="requirements"></a>要求

**标头：**\<ccomplex>

**命名空间:** std

## <a name="remarks"></a>备注

命名空间中声明的名称不是在 `clog` \<complex.h> 命名空间中定义的， `std` 因为可能与 `clog` 在中声明的发生冲突 [\<iostream>](iostream.md) 。

## <a name="see-also"></a>请参阅

[\<complex>](complex.md)\
[\<cmath>](cmath.md)\
[标头文件引用](cpp-standard-library-header-files.md)\
[C + + 标准库概述](cpp-standard-library-overview.md)\
[C + + 标准库中的线程安全](thread-safety-in-the-cpp-standard-library.md)
