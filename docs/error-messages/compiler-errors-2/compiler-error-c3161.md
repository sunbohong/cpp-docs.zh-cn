---
description: 了解更多：编译器错误 C3161
title: 编译器错误 C3161
ms.date: 11/04/2016
f1_keywords:
- C3161
helpviewer_keywords:
- C3161
ms.assetid: 1fe2be85-a343-487b-8476-bf9e257eb29d
ms.openlocfilehash: 4e45d64e1c1f318a126122148c2dd8e3ddb9c5af
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97203960"
---
# <a name="compiler-error-c3161"></a>编译器错误 C3161

"interface"：接口中的嵌套类、结构、联合或接口是非法的;类、结构或联合中的嵌套接口是非法的

[__Interface](../../cpp/interface.md)只能出现在全局范围或命名空间中。 类、结构或联合不能出现在接口中。

## <a name="example"></a>示例

下面的示例生成 C3161。

```cpp
// C3161.cpp
// compile with: /c
__interface X {
   __interface Y {};   // C3161 A nested interface
};
```
