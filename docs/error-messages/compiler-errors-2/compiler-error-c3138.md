---
description: 了解更多：编译器错误 C3138
title: 编译器错误 C3138
ms.date: 11/04/2016
f1_keywords:
- C3138
helpviewer_keywords:
- C3138
ms.assetid: 364ee9e8-9358-410e-bd35-9c4a226a3753
ms.openlocfilehash: 07fa48cc4c14773eeb41420eb63d659028de8caf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97304254"
---
# <a name="compiler-error-c3138"></a>编译器错误 C3138

"interface"： "attribute" 接口必须从 IDispatch 继承，或者从继承自 IDispatch 的接口继承

具有 [双重](../../windows/attributes/dual.md) 或 [调度](../../windows/attributes/dispinterface.md) 接口属性的接口不具有 `IDispatch` 作为直接或间接基接口。

下面的示例生成 C3138：

```cpp
// C3138.cpp
#include <unknwn.h>

[ object, uuid("77ac9240-6e9a-11d2-97de-0000f805d73b") ]
__interface IMyCustomInterface
{
   HRESULT mf1(void);
};

[ dispinterface, uuid("3536f8a0-6e9a-11d2-97de-0000f805d73b") ]
__interface IMyDispInterface : IUnknown
{
   [id(1)] HRESULT mf2(void);
};

[ object, dual, uuid("34e90a10-6e9a-11d2-97de-0000f805d73b") ]
__interface IMyDualInterface : IMyCustomInterface  // C3138 expected
{
   HRESULT mf3(void);
};
```
