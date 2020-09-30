---
title: 编译器警告 C4394
ms.date: 11/04/2016
f1_keywords:
- C4394
helpviewer_keywords:
- C4394
ms.assetid: 5de94de0-17e3-4e7c-92f4-5c3c1b825120
ms.openlocfilehash: fc4d66444b4ddc5c855e88d466ccc2f42c60e0ca
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/29/2020
ms.locfileid: "91510059"
---
# <a name="compiler-warning-c4394"></a>编译器警告 C4394

"function"：不应将每个 appdomain 符号标记 __declspec (dllexport) 

使用 [appdomain](../../cpp/appdomain.md)修饰符标记的函数 **`__declspec`** 编译为 MSIL (不是本机) ，而导出表 ([导出](../../windows/attributes/export.md) **`__declspec`** 修饰符) 对于托管函数不受支持。

您可以将托管函数声明为具有公共可访问性。 有关详细信息，请参阅 [类型可见性](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Type_visibility) 和 [成员可见性](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Member_visibility)。

C4394 始终作为错误发出。  可以通过或/wd 关闭此警告 `#pragma warning` ; 有关 **/wd**详细信息，请参阅[警告](../../preprocessor/warning.md)或[/W、/W0、/W1、/W2、/W3、/W4、/W1、/W2、/W3、/W4、/Wall、/Wd、/WE、/Wo、/Wv、/wx (warning Level) ](../../build/reference/compiler-option-warning-level.md) 。

## <a name="example"></a>示例

下面的示例生成 C4394。

```cpp
// C4394.cpp
// compile with: /clr /c
__declspec(dllexport) __declspec(appdomain) int g1 = 0;   // C4394
__declspec(dllexport) int g2 = 0;   // OK
```
