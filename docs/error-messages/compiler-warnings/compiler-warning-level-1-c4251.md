---
description: 了解详细信息：编译器警告 (等级 1) C4251
title: 编译器警告（等级 1）C4251
ms.date: 04/21/2020
f1_keywords:
- C4251
helpviewer_keywords:
- C4251
ms.assetid: a9992038-f0c2-4fc4-a9be-4509442cbc1e
ms.openlocfilehash: 4d08462442fd64ebef85573f5d538d6a884c8131
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97266229"
---
# <a name="compiler-warning-level-1-c4251"></a>编译器警告（等级 1）C4251

> "*type*"：类 "*type1*" 需要由类 "*type2*" 的客户端使用的 dll 接口

## <a name="remarks"></a>备注

为了最大程度地减少将 [ (dllexport) ](../../cpp/dllexport-dllimport.md)声明为 __declspec 的类时数据损坏的可能性，请确保：

- 所有静态数据都可以通过从 DLL 导出的函数进行访问。

- 类的任何内联方法都不能修改静态数据。

- 类的任何内联方法都不使用 CRT 函数或其他使用静态数据的库函数。 有关详细信息，请参阅 [跨 DLL 边界传递 CRT 对象时出现的潜在错误](../../c-runtime-library/potential-errors-passing-crt-objects-across-dll-boundaries.md)。

- 类的任何方法都不 (内联或不) 是否可以使用 EXE 和 DLL 中的实例化具有静态数据差异的类型。

从 DLL 导出类时可以避免出现问题：定义类以具有虚函数，并使用函数来实例化和删除类型的对象。 然后，就可以对类型调用虚函数。

如果类是从 c + + 标准库中的类型派生的，则可以忽略 C4251，而是编译调试版本 (**/MTd**) ，以及编译器错误消息所引用的位置 `_Container_base` 。

## <a name="example"></a>示例

此示例导出 `VecWrapper` 派生自的专用类 `std::vector` 。

```cpp
// C4251.cpp
// compile with: /EHsc /MTd /W2 /c
#include <vector>
using namespace std;
class Node;
class __declspec(dllexport) VecWrapper : vector<Node *> {};   // C4251
```
