---
description: 了解更多：编译器错误 C3846
title: 编译器错误 C3846
ms.date: 11/04/2016
f1_keywords:
- C3846
helpviewer_keywords:
- C3846
ms.assetid: c470f8a5-106b-4efb-b8dc-e1319e04130f
ms.openlocfilehash: 13c9cb7a9dde3710cac31d8ee79fb148f8ff67bb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97255387"
---
# <a name="compiler-error-c3846"></a>编译器错误 C3846

"symbol"：无法从 "assembly2" 导入符号：因为 "symbol" 已从另一个程序集 "assembly1" 导入

无法从引用的程序集导入符号，因为它以前是从引用的程序集导入的。

## <a name="example"></a>示例

下面的示例生成 C3846：

```cpp
// C3846a.cpp
// compile with: /LD /clr
public ref struct G
{
};
```

然后编译以下内容：

```cpp
// C3846b.cpp
// compile with: /clr
#using "c3846a.dll"
#using "c3846a.obj"   // C3846

int main()
{
}
```
