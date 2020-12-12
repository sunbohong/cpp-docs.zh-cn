---
description: 了解更多：编译器错误 C2696
title: 编译器错误 C2696
ms.date: 11/04/2016
f1_keywords:
- C2696
helpviewer_keywords:
- C2696
ms.assetid: 6c6eb7df-1230-4346-9a73-abf14c20785d
ms.openlocfilehash: 2d4a798258ba6f9bb467c4da32e75860b96874e1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97326610"
---
# <a name="compiler-error-c2696"></a>编译器错误 C2696

无法创建托管类型 "type" 的临时对象

**`const`** 在非托管程序中引用将导致编译器调用构造函数并在堆栈上创建临时对象。 但是，不能在堆栈上创建托管类。

只能使用过时的编译器选项 **/clr： oldSyntax** 来访问 C2696。
