---
description: 了解详细信息：参数访问
title: 参数访问
ms.date: 04/04/2018
f1_keywords:
- c.arguments
helpviewer_keywords:
- argument access macros [C++]
- variable-length argument lists
ms.assetid: 7046ae34-a0ec-44f0-815d-3209492a3e19
ms.openlocfilehash: f62ac2bc4ae895afe763d0a0a4caa32601e82713
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97221860"
---
# <a name="argument-access"></a>参数访问

当参数数量可变时，va_arg、va_end 和 va_start 宏提供对函数参数的访问。 这些宏在中定义 \<stdarg.h> 为 ANSI/ISO C 兼容性和中的，以 \<varargs.h> 实现与 UNIX 系统 V 的兼容。

## <a name="argument-access-macros"></a>参数-访问宏

|宏|使用|
|-----------|-------------------------------|
|[va_arg](../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md)|从列表中检索自变量|
|[va_end](../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md)|重置指针|
|[va_start](../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md)|将指针设置到自变量列表的开始位置|

## <a name="see-also"></a>请参阅

[按类别分的通用 C 运行时例程](../c-runtime-library/run-time-routines-by-category.md)
