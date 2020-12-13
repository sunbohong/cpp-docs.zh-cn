---
description: 了解详细信息：异常处理例程
title: 异常处理例程
ms.date: 11/04/2016
f1_keywords:
- c.exceptions
helpviewer_keywords:
- exception handling, routines
ms.assetid: f60548c6-850a-4e1e-a79b-a2a6a541ab62
ms.openlocfilehash: d241c3ef7f32a96f08d4ad499887963fda031967
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97331094"
---
# <a name="exception-handling-routines"></a>异常处理例程

在程序执行期间使用 C++ 异常处理函数从意外事件恢复。

## <a name="exception-handling-functions"></a>异常处理函数

|函数|使用|
|--------------|---------|
|[_set_se_translator](../c-runtime-library/reference/set-se-translator.md)|将 Win32 异常（C 结构的异常）处理为 C++ 类型的异常|
|[set_terminate](../c-runtime-library/reference/set-terminate-crt.md)|安装 terminate 将调用的自身的终止例程|
|[set_unexpected](../c-runtime-library/reference/set-unexpected-crt.md)|安装要由 unexpected 调用的自身的终止函数|
|[终止](../c-runtime-library/reference/terminate-crt.md)|引发异常后在特定情况下自动调用。 terminate 函数调用 abort 或使用 set_terminate 指定的函数|
|[之外](../c-runtime-library/reference/unexpected-crt.md)|调用 terminate 或使用 set_unexpected 指定的函数。 不会在当前 Microsoft C++ 异常处理实现中使用 unexpected 函数|

## <a name="see-also"></a>请参阅

[按类别分的通用 C 运行时例程](../c-runtime-library/run-time-routines-by-category.md)<br/>
