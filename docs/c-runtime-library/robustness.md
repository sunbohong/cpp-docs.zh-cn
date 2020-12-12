---
description: 了解详细信息：可靠性
title: 稳定性
ms.date: 11/04/2016
helpviewer_keywords:
- robustness [CRT]
ms.assetid: 7f1a87f8-eff9-4b76-ae9b-d133d3de6adf
ms.openlocfilehash: 7dfe3d40eae4c67f45d4332ce22255a44c33f728
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97284507"
---
# <a name="robustness"></a>稳定性

使用以下 C 运行时库函数以提高程序的可靠性。

## <a name="run-time-robustness-functions"></a>运行时可靠性函数

|函数|使用|
|--------------|---------|
|[_set_new_handler](../c-runtime-library/reference/set-new-handler.md)|如果运算符无法分配内存，则将控制权转移到错误处理机制 **`new`** 。|
|[_set_se_translator](../c-runtime-library/reference/set-se-translator.md)|将 Win32 异常（C 结构的异常）处理为 C++ 类型的异常。|
|[set_terminate](../c-runtime-library/reference/set-terminate-crt.md)|安装要由 [terminate](../c-runtime-library/reference/terminate-crt.md) 调用的自身的终止函数。|
|[set_unexpected](../c-runtime-library/reference/set-unexpected-crt.md)|安装要由 [unexpected](../c-runtime-library/reference/unexpected-crt.md) 调用的自身的终止函数。|

## <a name="see-also"></a>请参阅

[按类别分的通用 C 运行时例程](../c-runtime-library/run-time-routines-by-category.md)<br/>
[SetUnhandledExceptionFilter](/windows/win32/api/errhandlingapi/nf-errhandlingapi-setunhandledexceptionfilter)<br/>
