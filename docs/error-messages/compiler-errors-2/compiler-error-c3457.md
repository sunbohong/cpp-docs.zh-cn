---
description: 了解更多：编译器错误 C3457
title: 编译器错误 C3457
ms.date: 11/04/2016
f1_keywords:
- C3457
helpviewer_keywords:
- C3457
ms.assetid: 5c1e366a-fa75-4cca-b9a3-86d4ebe4090e
ms.openlocfilehash: 42e30946c57da585ed1339e49b6081372b141a2c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97113592"
---
# <a name="compiler-error-c3457"></a>编译器错误 C3457

“attribute”：特性不支持未命名参数

源 annotation 特性与 CLR 自定义特性或编译器特性不同，仅支持命名参数。

## <a name="example"></a>示例

以下示例生成 C3457。

```
#include "SourceAnnotations.h"
[vc_attributes::Post( 1 )] int f();   // C3457
[vc_attributes::Post( Valid=vc_attributes::Yes )] int f2();   // OK
```
