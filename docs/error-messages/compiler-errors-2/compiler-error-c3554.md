---
description: 了解更多：编译器错误 C3554
title: 编译器错误 C3554
ms.date: 11/04/2016
f1_keywords:
- C3554
helpviewer_keywords:
- C3554
ms.assetid: aede18d5-fefc-4da9-9b69-adfe90bfa742
ms.openlocfilehash: 39bc1a673af37d6b73941bb300d86df5f41a4704
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97223173"
---
# <a name="compiler-error-c3554"></a>编译器错误 C3554

“decltype”不能与任何其他类型说明符组合

不可用任何类型说明符来限定 `decltype()` 关键字。 例如，下述代码片段产生错误 C3554。

```
int x;
unsigned decltype(x); // C3554
```
