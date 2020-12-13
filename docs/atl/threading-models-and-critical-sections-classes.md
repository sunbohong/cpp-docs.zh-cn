---
description: 了解详细信息：线程模型和临界区类
title: '线程模型和临界区类 (ATL) '
ms.date: 11/04/2016
helpviewer_keywords:
- ATL, critical sections
- ATL, multithreading
- threading [ATL], models
- critical sections
ms.assetid: 759f05ef-6285-4be6-a2cc-78572dd75146
ms.openlocfilehash: 51ad5a5f2f03bfe080395966d0c480615c49a109
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97138276"
---
# <a name="threading-models-and-critical-sections-classes"></a>线程模型和临界区类

以下类定义线程模型和临界区：

- [CAtlAutoThreadModule](../atl/reference/catlautothreadmodule-class.md) 实现一个线程池的单元模型 COM 服务器。

- [CAtlAutoThreadModuleT](../atl/reference/catlautothreadmodulet-class.md) 提供用于实现线程池单元模型 COM 服务器的方法。

- [CComMultiThreadModel](../atl/reference/ccommultithreadmodel-class.md) 提供用于递增和递减变量的线程安全方法。 提供临界区。

- [CComMultiThreadModelNoCS](../atl/reference/ccommultithreadmodelnocs-class.md) 提供用于递增和递减变量的线程安全方法。 不提供临界区。

- [CComSingleThreadModel](../atl/reference/ccomsinglethreadmodel-class.md) 提供用于递增和递减变量的方法。 不提供临界区。

- [CComObjectThreadModel](../atl/reference/atl-typedefs.md#ccomobjectthreadmodel) 确定单个对象类的适当线程模式类。

- [CComGlobalsThreadModel](../atl/reference/atl-typedefs.md#ccomglobalsthreadmodel) 为全局可用的对象确定相应的线程模式类。

- [CComAutoCriticalSection](../atl/reference/ccomautocriticalsection-class.md) 包含用于获取和释放关键部分的方法。 临界区会自动初始化。

- [CComCriticalSection](../atl/reference/ccomcriticalsection-class.md) 包含用于获取和释放关键部分的方法。 必须显式初始化临界区。

- [CComFakeCriticalSection](../atl/reference/ccomfakecriticalsection-class.md) 镜像中的方法 `CComCriticalSection` 而不提供关键部分。 中的方法 `CComFakeCriticalSection` 不执行任何操作。

- [CRTThreadTraits](../atl/reference/crtthreadtraits-class.md) 为 CRT 线程提供创建函数。 如果线程将使用 CRT 函数，请使用此类。

- [Win32ThreadTraits](../atl/reference/win32threadtraits-class.md) 为 Windows 线程提供创建函数。 如果线程不使用 CRT 函数，请使用此类。

## <a name="see-also"></a>请参阅

[类概述](../atl/atl-class-overview.md)
