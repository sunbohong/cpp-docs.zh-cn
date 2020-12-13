---
description: 了解更多相关信息：使 ATL 对象 Noncreatable
title: 使 ATL 对象不可创建
ms.date: 11/04/2016
f1_keywords:
- vc.appwiz.ATL.objects
helpviewer_keywords:
- noncreatable ATL objects
- ATL projects, noncreatable objects
ms.assetid: 80d0bca2-dea0-4801-9a85-6243124437f6
ms.openlocfilehash: 0a7a07081546722e5a960cb8bf0384a1d7e47f9b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97139173"
---
# <a name="making-an-atl-object-noncreatable"></a>使 ATL 对象不可创建

您可以更改基于 ATL 的 COM 对象的属性，以便客户端不能直接创建对象。 在这种情况下，将通过其他对象上的方法调用返回对象，而不是直接创建对象。

## <a name="to-make-an-object-noncreatable"></a>使对象 noncreatable

1. 删除对象的 [OBJECT_ENTRY_AUTO](object-map-macros.md#object_entry_auto) 。 如果希望对象 noncreatable，但要注册的控件，请将 OBJECT_ENTRY_AUTO 替换为 [OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO](object-map-macros.md#object_entry_non_createable_ex_auto)。

1. 将 [noncreatable](../../windows/attributes/noncreatable.md) 特性添加到 .idl 文件中的 coclass。 例如：

    ```
    [uuid(A1992E3D-3CF0-11D0-826F-00A0C90F2851),
    helpstring("MyObject"),
    noncreatable]
    coclass MyObject
    {
        [default] interface IMyInterface;
    }
    ```

## <a name="see-also"></a>请参阅

[ATL 项目向导](../../atl/reference/atl-project-wizard.md)<br/>
[Visual Studio 中的 C++ 项目类型](../../build/reference/visual-cpp-project-types.md)<br/>
[用 ATL 和 C Run-Time 代码编程](../../atl/programming-with-atl-and-c-run-time-code.md)<br/>
[ATL COM 对象的基本知识](../../atl/fundamentals-of-atl-com-objects.md)<br/>
[默认 ATL 项目配置](../../atl/reference/default-atl-project-configurations.md)
