---
description: 了解更多：编译器错误 C3550
title: 编译器错误 C3550
ms.date: 11/04/2016
f1_keywords:
- C3550
helpviewer_keywords:
- C3550
ms.assetid: 9f2d5ffc-e429-41a1-89e3-7acc4fd47e14
ms.openlocfilehash: 4cb459e3f8e7fdd0dbb00c1d4dfaa3c3c6b1eb71
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97112409"
---
# <a name="compiler-error-c3550"></a>编译器错误 C3550

此上下文只允许纯“decltype(auto)”

如果 `decltype(auto)` 用作函数的返回类型的占位符，则它必须被其自身使用。 它无法用作指针声明 (`decltype(auto*)`)、引用声明 (`decltype(auto&)`) 或其他此类限定的一部分。

## <a name="see-also"></a>请参阅

[auto](../../cpp/auto-cpp.md)
