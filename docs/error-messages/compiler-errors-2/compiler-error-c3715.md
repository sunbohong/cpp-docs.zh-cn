---
description: 了解更多：编译器错误 C3715
title: 编译器错误 C3715
ms.date: 11/04/2016
f1_keywords:
- C3715
helpviewer_keywords:
- C3715
ms.assetid: ee5dce88-ddc4-4bdb-9464-47467ce1674f
ms.openlocfilehash: b64f7039b15363b36f6cc761f834c64dae255f76
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97189452"
---
# <a name="compiler-error-c3715"></a>编译器错误 C3715

"指针"：必须是指向 "class" 的指针

您在或中指定的指针 [`__hook`](../../cpp/hook.md) [`__unhook`](../../cpp/unhook.md) 不指向有效的类。 若要修复此错误，请确保 **`__hook`** 和 **`__unhook`** 调用指定指向有效类的指针。
