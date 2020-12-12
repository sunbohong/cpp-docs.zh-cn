---
description: 了解详细信息： EXIT_SUCCESS、EXIT_FAILURE
title: EXIT_SUCCESS、EXIT_FAILURE
ms.date: 06/25/2018
f1_keywords:
- EXIT_FAILURE
- EXIT_SUCCESS
helpviewer_keywords:
- EXIT_SUCCESS constant
- EXIT_FAILURE constant
ms.assetid: ff2c82cb-c0bb-4556-a812-59aa278bfac5
ms.openlocfilehash: d92481635d553de4cfaa9bd026fd577cd51f6eff
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97300055"
---
# <a name="exit_success-exit_failure"></a>EXIT_SUCCESS、EXIT_FAILURE

## <a name="required-header"></a>必需的标头

```c
#include <stdlib.h>
```

## <a name="remarks"></a>备注

这些是 [exit](reference/exit-exit-exit.md) 和 [_exit](reference/exit-exit-exit.md) 函数的参数以及 [atexit](reference/atexit.md) 和 [_onexit](reference/onexit-onexit-m.md) 函数的返回值。

|返回的常量|已定义的值|
|-|-|
|EXIT_SUCCESS|0|
|EXIT_FAILURE|1|

## <a name="see-also"></a>请参阅

[全局常量](../c-runtime-library/global-constants.md)
