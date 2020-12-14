---
description: 了解更多：编译器错误 C3372
title: 编译器错误 C3372
ms.date: 11/04/2016
f1_keywords:
- C3372
helpviewer_keywords:
- C3372
ms.assetid: 38ee39ed-03ff-4e6d-9104-f1977b96645d
ms.openlocfilehash: 6da2517585f4d50251884810f5c4a951f93ff257
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97245234"
---
# <a name="compiler-error-c3372"></a>编译器错误 C3372

必须至少为组件类的 "source" 特性指定 1 个接口

对于某些特性，必须将接口名称作为参数传递。

下面的示例生成 C3372：

```cpp
// C3372.cpp
#include <windows.h>
[module(name="MyModule")];

[ object, uuid(373a1a4c-469b-11d3-a6b0-00c04f79ae8f) ]
__interface IMyIface {
   HRESULT f1();
};
// to resolve, pass an interface name to the source attribute
// for example, source(IMyIface)
[ coclass, uuid(373a1a4d-469b-11d3-a6b0-00c04f79ae8f), source,
  default(IMyIface) ] // C3372
class CMyClass {
};

int main() {
}
```
