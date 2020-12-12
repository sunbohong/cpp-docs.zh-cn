---
description: 了解详细信息： ATL 和自由线程封送拆收器
title: ATL 和自由线程封送拆收器
ms.date: 11/04/2016
helpviewer_keywords:
- ATL, free threaded marshaler
- free threaded marshaler
- threading [C++], marshaler in ATL
- threading [ATL], free threaded marshaler
- FTM in ATL
ms.assetid: 2db88a13-2217-4ebc-aa7e-432d5da902eb
ms.openlocfilehash: 01fb54386b5f48c8e49cc805e047c0faf8b0c39b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97166065"
---
# <a name="atl-and-the-free-threaded-marshaler"></a>ATL 和自由线程封送拆收器

ATL 简单对象向导的 "属性" 页提供了一个选项，该选项允许您的类将自由线程封送拆收器 (INTERNAL.H) 。

向导将生成代码以在中创建自由线程封送拆收器的实例 `FinalConstruct` ，并在中释放该实例 `FinalRelease` 。 COM_INTERFACE_ENTRY_AGGREGATE 宏会自动添加到 COM 映射，以确保 IMarshal 的 `QueryInterface` 请求由[](/windows/win32/api/objidlbase/nn-objidlbase-imarshal)自由线程封送拆收器处理。

自由线程封送拆收器允许从同一进程中的任何线程直接访问你的对象上的接口，从而加快了跨单元调用。 此选项用于使用这两种线程模型的类。

使用此选项时，类必须负责其数据的线程安全性。 此外，聚合自由线程封送拆收器并需要使用从其他对象获取的接口指针的对象必须执行额外的步骤，以确保正确封送接口。 通常，这涉及到将接口指针存储 (GIT) ，并在每次使用时从 GIT 获取指针。 ATL 提供类 [CComGITPtr](../atl/reference/ccomgitptr-class.md) 来帮助你使用存储在 GIT 中的接口指针。

## <a name="see-also"></a>请参阅

[概念](../atl/active-template-library-atl-concepts.md)<br/>
[CoCreateFreeThreadedMarshaler](/windows/win32/api/combaseapi/nf-combaseapi-cocreatefreethreadedmarshaler)<br/>
[IMarshal](/windows/win32/api/objidlbase/nn-objidlbase-imarshal)<br/>
[何时使用全局接口表](/windows/win32/com/when-to-use-the-global-interface-table)<br/>
[进程内服务器线程问题](/windows/win32/com/in-process-server-threading-issues)
