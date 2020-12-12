---
description: 了解更多：编译器错误 C3552
title: 编译器错误 C3552
ms.date: 11/04/2016
f1_keywords:
- C3552
helpviewer_keywords:
- C3552
ms.assetid: 83401524-1bf1-44c0-8aca-a6eb35c4224c
ms.openlocfilehash: aca1474f53c8ac1a8257b23d0042550b76b3c0e8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97223251"
---
# <a name="compiler-error-c3552"></a>编译器错误 C3552

“typename”: 后指定返回类型不能包含“auto”

如果使用 **`auto`** 关键字作为函数返回类型的占位符，则必须提供一个后期指定的返回类型。 但是，不能使用其他 **`auto`** 关键字来指定后指定返回类型。 例如，下述代码片段产生错误 C3552。

`auto myFunction->auto; // C3552`
