---
description: '了解详细信息：指定项目的线程模型 (ATL) '
title: 指定项目的线程模型 (ATL)
ms.date: 11/04/2016
helpviewer_keywords:
- _ATL_FREE_THREADED macro
- _ATL_APARTMENT_THREADED macro
- ATL, multithreading
- threading [ATL], models
- _ATL_SINGLE_THREADED macro
ms.assetid: 6b571078-521c-4f3e-9f08-482aa235a822
ms.openlocfilehash: 81bf8413a2118797ec0e0c177a06468b8e3c7ba0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97138471"
---
# <a name="specifying-the-threading-model-for-a-project-atl"></a>指定项目的线程模型 (ATL)

以下宏可用于指定 ATL 项目的线程模型：

|宏|使用准则|
|-----------|--------------------------|
|_ATL_SINGLE_THREADED|定义所有对象是否均使用单个线程模型。|
|_ATL_APARTMENT_THREADED|定义一个或多个对象是否使用单元线程处理。|
|_ATL_FREE_THREADED|定义一个或多个对象是否使用自由或非特定线程。 现有代码可能包含对等效宏 [_ATL_MULTI_THREADED](reference/compiler-options-macros.md#_atl_multi_threaded)的引用。|

如果没有为项目定义任何这些宏，_ATL_FREE_THREADED 将生效。

宏会影响运行时性能，如下所示：

- 指定与项目中的对象相对应的宏可以提高运行时性能。

- 指定较高级别的宏，例如，如果您在所有对象都是单线程的情况下指定 _ATL_APARTMENT_THREADED，则会稍微降低运行时性能。

- 指定较低级别的宏（例如，如果在一个或多个对象使用单元线程或自由线程处理时指定 _ATL_SINGLE_THREADED），会导致应用程序在运行时失败。

有关适用于 ATL 对象的线程模型的说明，请参阅 [Atl 简单对象向导中的选项](../atl/reference/options-atl-simple-object-wizard.md) 。

## <a name="see-also"></a>请参阅

[概念](../atl/active-template-library-atl-concepts.md)
