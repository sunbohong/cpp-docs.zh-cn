---
description: 详细了解：调试和异常类
title: 调试和异常类
ms.date: 11/04/2016
f1_keywords:
- vc.classes.debug
helpviewer_keywords:
- debugging [MFC], exception classes
- debugging [MFC], classes for debugging
ms.assetid: 0d158efd-2e62-452e-9d2a-d3c30dfee7f9
ms.openlocfilehash: 2c14ea8d51fd1b63427ad1495e711a906e013ea4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97291111"
---
# <a name="debugging-and-exception-classes"></a>调试和异常类

这些类为调试动态内存分配和将异常信息从引发异常的函数传递到捕获异常的函数提供支持。

在开发过程中使用类 [CDumpContext](reference/cdumpcontext-class.md) 和 [CMemoryState](reference/cmemorystate-structure.md) 来协助调试，如 [调试 MFC 应用程序](/visualstudio/debugger/mfc-debugging-techniques)中所述。 在运行时使用 [CRuntimeClass](reference/cruntimeclass-structure.md) 来确定任何对象的类，如 [访问 Run-Time 类信息](accessing-run-time-class-information.md)一文中所述。 框架使用 `CRuntimeClass` 动态创建特定类的对象。

## <a name="see-also"></a>请参阅

[类概述](class-library-overview.md)
