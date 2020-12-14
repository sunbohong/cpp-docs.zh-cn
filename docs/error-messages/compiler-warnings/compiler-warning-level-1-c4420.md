---
description: 了解详细信息：编译器警告 (等级 1) C4420
title: 编译器警告（等级 1）C4420
ms.date: 11/04/2016
f1_keywords:
- C4420
helpviewer_keywords:
- C4420
ms.assetid: 44a37754-7ddd-4764-a5f7-d33e05c20091
ms.openlocfilehash: 2a92d7296bf5c38655182e5c0dd2c200d0ccf42d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97311066"
---
# <a name="compiler-warning-level-1-c4420"></a>编译器警告（等级 1）C4420

"operator"：运算符不可用，请改用 "operator";可能会危及运行时检查

当你使用 [/RTCv](../../build/reference/rtc-run-time-error-checks.md) (向量 new/delete 检查) 并且找不到矢量窗体时，将生成此警告。 在这种情况下，将使用非向量窗体。

若要使/RTCv 正常工作， [](../../cpp/new-operator-cpp.md) / 如果使用向量语法，则编译器应始终调用新[删除](../../cpp/delete-operator-cpp.md)的矢量形式。
