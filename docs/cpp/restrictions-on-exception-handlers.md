---
title: 对于异常处理程序的限制
description: 介绍跳转到结构化异常处理块的限制。
ms.date: 08/24/2020
helpviewer_keywords:
- restrictions, exception handlers
- exception handling [C++], exception handlers
ms.assetid: 31d63524-0e8c-419f-b87c-061f4c0ea470
ms.openlocfilehash: c4182f065789533bf7599621d8d2829b2d52d6ed
ms.sourcegitcommit: efc8c32205c9d610f40597556273a64306dec15d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2020
ms.locfileid: "88898454"
---
# <a name="restrictions-on-exception-handlers"></a>对于异常处理程序的限制

在代码中使用异常处理程序的主要限制是不能使用 **`goto`** 语句跳转到 **`__try`** 语句块。 相反，您必须通过常规控制流进入此语句块。 您可以跳出 **`__try`** 语句块，并可以在选择时嵌套异常处理程序。

## <a name="see-also"></a>请参阅

[编写异常处理程序](../cpp/writing-an-exception-handler.md)<br/>
[Structured Exception Handling (C/C++)](../cpp/structured-exception-handling-c-cpp.md)
