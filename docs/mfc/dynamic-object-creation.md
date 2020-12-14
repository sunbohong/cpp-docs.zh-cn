---
description: 了解详细信息：动态对象创建
title: 动态对象创建
ms.date: 03/27/2020
helpviewer_keywords:
- object creation [MFC], dynamically at run time
- CObject class [MFC], dynamic object creation
- objects [MFC], creating dynamically at run time
- dynamic object creation [MFC]
ms.assetid: 3e0f51cb-3e24-4231-817f-1c0ce9f2d5df
ms.openlocfilehash: b39c0561a98807030c471b3de4cd5921883f9f0e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97290968"
---
# <a name="dynamic-object-creation"></a>动态对象创建

本文说明了如何在运行时动态地创建对象。 此过程使用运行时类信息，如 [访问 Run-Time 类信息](accessing-run-time-class-information.md)一文中所述。

#### <a name="dynamically-create-an-object-given-its-run-time-class"></a>根据给定的运行时类动态创建对象

1. 使用以下代码通过的函数动态创建对象 `CreateObject` `CRuntimeClass` 。 失败时，将 `CreateObject` 返回 **NULL** ，而不是引发异常：

   [!code-cpp[NVC_MFCCObjectSample#6](codesnippet/cpp/dynamic-object-creation_1.cpp)]

## <a name="see-also"></a>请参阅

[销毁窗口对象](tn017-destroying-window-objects.md) 
[使用 CObject](using-cobject.md)
