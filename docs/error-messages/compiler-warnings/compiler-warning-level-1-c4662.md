---
description: 了解详细信息：编译器警告 (等级 1) C4662
title: 编译器警告（等级 1）C4662
ms.date: 11/04/2016
f1_keywords:
- C4662
helpviewer_keywords:
- C4662
ms.assetid: 7efda273-d04a-47b7-ad65-ff1ff94b5ffc
ms.openlocfilehash: 60de9a5f5f4a70fc80eff5322a4757571efd5902
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97318762"
---
# <a name="compiler-warning-level-1-c4662"></a>编译器警告（等级 1）C4662

显式实例化；模板类“identifier1”无用于专用化“identifier2”的定义

已声明但未定义指定的模板类。

## <a name="example"></a>示例

```cpp
// C4662.cpp
// compile with: /W1 /LD
template<class T, int i> class MyClass; // no definition
template MyClass< int, 1>;              // C4662
```
