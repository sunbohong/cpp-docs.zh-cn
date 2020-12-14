---
description: 了解更多：编译器错误 C2865
title: 编译器错误 C2865
ms.date: 11/04/2016
f1_keywords:
- C2865
helpviewer_keywords:
- C2865
ms.assetid: 973eb6a0-c99a-4d25-b3e5-fe0539794d77
ms.openlocfilehash: 0c57fdb120eb147b3877cc834e142ab92f147aaa
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97220742"
---
# <a name="compiler-error-c2865"></a>编译器错误 C2865

"function"：非法比较 handle_or_pointer

您可以比较对 [类和结构](../../extensions/classes-and-structs-cpp-component-extensions.md) 或托管引用类型的引用，以确定它们是否引用相同的对象 (= =) 或 (！ =) 的不同对象。

由于 .NET 运行时可能随时移动托管对象，因此不能对它们进行比较以便进行排序。
