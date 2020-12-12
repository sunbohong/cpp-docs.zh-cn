---
description: 了解详细信息：编译器警告 (等级 1) C4176
title: 编译器警告（等级 1）C4176
ms.date: 11/04/2016
f1_keywords:
- C4176
helpviewer_keywords:
- C4176
ms.assetid: cfffb934-219a-4a63-9df6-ba54405bf766
ms.openlocfilehash: 9ba6e0ec6dff72d875aecc74e51d6f9a7e1c05e3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97266892"
---
# <a name="compiler-warning-level-1-c4176"></a>编译器警告（等级 1）C4176

“subcomponent”: #pragma component browser 的未知子组件

**component** 杂注包含无效子组件。 若要排除对特定名称的引用，必须在名称前使用 **references** 选项。

## <a name="example"></a>示例

```cpp
// C4176.cpp
// compile with: /W1 /LD
#pragma component(browser, off, i)  // C4176
#pragma component(browser, off, references, i) // ok
```
