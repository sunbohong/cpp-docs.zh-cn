---
title: 编译器错误 C3466
ms.date: 11/04/2016
f1_keywords:
- C3466
helpviewer_keywords:
- C3466
ms.assetid: 69a877d9-a749-474b-bfc3-8d3fd53ba8fd
ms.openlocfilehash: 689a0ca837cf305840d6f080e615527f01879225
ms.sourcegitcommit: 72161bcd21d1ad9cc3f12261aa84a5b026884afa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/17/2020
ms.locfileid: "90742835"
---
# <a name="compiler-error-c3466"></a>编译器错误 C3466

"type"：泛型类的专用化不能被转发

不能对泛型类的专用化使用类型转发。

有关详细信息，请参阅 [类型转发 (c + +/cli) ](../../extensions/type-forwarding-cpp-cli.md)。

## <a name="examples"></a>示例

下面的示例创建一个组件。

```cpp
// C3466.cpp
// compile with: /clr /LD
generic<typename T>
public ref class GR {};

public ref class GR2 {};
```

下面的示例生成 C3466。

```cpp
// C3466_b.cpp
// compile with: /clr /c
#using "C3466.dll"
[assembly:TypeForwardedTo(GR<int>::typeid)];   // C3466
[assembly:TypeForwardedTo(GR2::typeid)];   // OK
```
