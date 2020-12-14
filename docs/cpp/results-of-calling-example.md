---
description: 了解更多：调用示例的结果
title: 调用示例的结果
ms.date: 11/19/2018
helpviewer_keywords:
- examples [C++], results of calling
- results, thiscall call
- results, __fastcall keyword call
- results, __cdecl call
- results, __stdcall call
ms.assetid: aa70a7cb-ba1d-4aa6-bd0a-ba783da2e642
ms.openlocfilehash: 91da3182742414dc4850013463b74ae36aa782c0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97262914"
---
# <a name="results-of-calling-example"></a>调用示例的结果

**Microsoft 专用**

## <a name="__cdecl"></a>__cdecl

C 修饰函数名称为 `_MyFunc` 。

![CDECL 调用约定](../cpp/media/vc37i01.gif "CDECL 调用约定") <br/>
**`__cdecl`** 调用约定

## <a name="__stdcall-and-thiscall"></a>__stdcall 和 thiscall

) 的 C 修饰名称 (**`__stdcall`** 为 `_MyFunc@20` 。 C + + 修饰名称是特定于实现的。

![&#95;&#95;stdcall 和 thiscall 调用约定](../cpp/media/vc37i02.gif "&#95;&#95;stdcall 和 thiscall 调用约定") <br/>
__stdcall 和 thiscall 调用约定

## <a name="__fastcall"></a>__fastcall

) 的 C 修饰名称 (**`__fastcall`** 为 `@MyFunc@20` 。 C + + 修饰名称是特定于实现的。

![ &#95;&#95;fastcall 的调用约定](../cpp/media/vc37i03.gif " &#95;&#95;fastcall 的调用约定") <br/>
__fastcall 调用约定

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[调用示例：函数原型和调用](../cpp/calling-example-function-prototype-and-call.md)
