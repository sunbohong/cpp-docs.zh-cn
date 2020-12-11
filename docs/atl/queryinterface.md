---
description: 了解有关以下内容的详细信息： QueryInterface
title: QueryInterface
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- interfaces, pointers
- interfaces, availability
- QueryInterface method
ms.assetid: 62fce95e-aafa-4187-b50b-e6611b74c3b3
ms.openlocfilehash: b22163c9e69bd5573f8e6060df0457862813c366
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97159162"
---
# <a name="queryinterface"></a>QueryInterface

尽管有一些机制，对象可以通过这些机制来表示它在) 实例化之前提供的静态 (功能，但基本的 COM 机制是使用 `IUnknown` 称为 [QueryInterface](/windows/win32/api/unknwn/nf-unknwn-iunknown-queryinterface(q))的方法。

每个接口均派生自 `IUnknown` ，因此每个接口都有一个实现 `QueryInterface` 。 无论实现如何，此方法都使用调用方想要指针的接口的 IID 来查询对象。 如果对象支持该接口，则 `QueryInterface` 检索指向接口的指针，同时调用 `AddRef` 。 否则，它将返回 E_NOINTERFACE 错误代码。

请注意，必须始终遵守 [引用计数](../atl/reference-counting.md) 规则。 如果 `Release` 在接口指针上调用以将引用计数递减为零，则不应再次使用该指针。 有时你可能需要获取对某个对象的弱引用 (也就是说，你可能希望获取指向它的某个接口的指针，而不会使引用计数递增) ，但通过调用后跟，这是不允许的 `QueryInterface` `Release` 。 以这种方式获取的指针无效，不应使用。 定义 [_ATL_DEBUG_INTERFACES](reference/debugging-and-error-reporting-macros.md#_atl_debug_interfaces) 时，这会变得很明显，因此定义此宏是查找引用计数 bug 的有用方法。

## <a name="see-also"></a>请参阅

[COM 简介](../atl/introduction-to-com.md)<br/>
[QueryInterface：在对象中导航](/windows/win32/com/queryinterface--navigating-in-an-object)
