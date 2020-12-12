---
description: 了解更多：过时调用约定
title: 已过时调用约定
ms.date: 11/04/2016
f1_keywords:
- __fortran
- __pascal
- __syscall
helpviewer_keywords:
- WINAPI [C++]
- __syscall keyword [C++]
- __pascal keyword [C++]
- __fortran keyword [C++]
- calling conventions, obsolete
ms.assetid: a91fc665-034a-48ce-b6bd-d27125f308a7
ms.openlocfilehash: 0dfbb34215ba79b54d01ce12fe4d543dbe1d6859
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97146037"
---
# <a name="obsolete-calling-conventions"></a>已过时调用约定

**Microsoft 专用**

不再支持 **__pascal**、 **__fortran** 和 **__syscall** 调用约定。 通过使用支持的调用约定之一和适当的链接器选项，可以模拟其功能。

\<windows.h> 现在支持 WINAPI 宏，该宏可转换为目标的适当调用约定。 使用 WINAPI，其中你以前使用了 PASCAL 或 **__far \_ _pascal**。

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[参数传递和命名约定](../cpp/argument-passing-and-naming-conventions.md)
