---
description: 了解更多：编译器错误 C2834
title: 编译器错误 C2834
ms.date: 11/04/2016
f1_keywords:
- C2834
helpviewer_keywords:
- C2834
ms.assetid: 28f9f6eb-ab2a-4e64-aaaa-9d14f955de41
ms.openlocfilehash: 6f74853f264af653988ed77ddb9a9c7935f3c542
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97194431"
---
# <a name="compiler-error-c2834"></a>编译器错误 C2834

"operator operator" 必须是全局限定的

`new`和 `delete` 运算符关联到它们所在的类。 范围解析不能用于 `new` 从不同的类中选择或的版本 `delete` 。 若要实现或运算符的多种形式 `new` `delete` ，请创建具有额外形参的运算符版本。
