---
description: 了解详细信息：消息处理和命令目标
title: 消息处理和命令目标
ms.date: 11/04/2016
f1_keywords:
- IOleCommandTarget
helpviewer_keywords:
- command targets [MFC]
- message handling [MFC], active documents
- IOleCommandTarget interface [MFC]
- command routing [MFC], command targets
ms.assetid: e45ce14c-e6b6-4262-8f3b-4e891e0ec2a3
ms.openlocfilehash: 35dc54687c7f3742f72d58f5c84cd274bc8fee09
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97203284"
---
# <a name="message-handling-and-command-targets"></a>消息处理和命令目标

命令调度接口 `IOleCommandTarget` 定义一种简单且可扩展的机制来查询和执行命令。 此机制比自动化更简单 `IDispatch` ，因为它完全依赖于一组标准的命令; 命令很少包含参数，并且不涉及任何类型信息 (类型安全对于命令参数也会降低) 。

在命令调度接口设计中，每个命令都属于 "命令组"，它本身用 **GUID** 标识。 因此，任何人都可以定义新组，并定义该组中的所有命令，而无需与 Microsoft 或任何其他供应商进行协调。  (这在本质上是与自动化中的 **调度接口** 和 **dispid** 相同的定义方法。 尽管此命令路由机制仅适用于命令路由，而不用于大规模的脚本编写/可编程性作为自动化句柄，但此处存在重叠。 ) 

`IOleCommandTarget` 处理以下方案：

- 当某个对象处于就地激活状态时，只会显示该对象的工具栏，并且该对象的工具栏可能会有一些容器命令（如 **打印**、 **打印预览**、 **保存**、 **新**、 **缩放** 等）的按钮。  (就地激活标准建议对象从其工具栏中删除此类按钮，或者至少禁用它们。 此设计允许启用这些命令，并将这些命令路由到正确的处理程序。 ) 目前，对象没有机制将这些命令调度到容器中。

- 如果活动文档嵌入到活动文档容器 (如 Office 活页夹) 中，则该容器可能需要向包含的活动文档发送诸如 **打印**、 **页面设置**、 **属性** 等命令。

这一简单的命令路由可以通过现有的自动化标准和来处理 `IDispatch` 。 但是，所涉及的开销超出了 `IDispatch` 需要，因此 `IOleCommandTarget` 提供了一个更简单的方法来实现相同的目的：

```
interface IOleCommandTarget : IUnknown
    {
    HRESULT QueryStatus(
        [in] GUID *pguidCmdGroup,
        [in] ULONG cCmds,
        [in,out][size_is(cCmds)] OLECMD *prgCmds,
        [in,out] OLECMDTEXT *pCmdText);
    HRESULT Exec(
        [in] GUID *pguidCmdGroup,
        [in] DWORD nCmdID,
        [in] DWORD nCmdExecOpt,
        [in] VARIANTARG *pvaIn,
        [in,out] VARIANTARG *pvaOut);
    }
```

`QueryStatus`此处的方法测试是否支持一组特定的命令（使用 **GUID** 标识的集）。 此调用使用受支持的命令列表，以及返回描述命令名称和/或状态信息的文本，来填充 **OLECMD** 值的数组，这些值 (结构) 。 当调用方想要调用命令时，它可以将命令 (和设置 **GUID**) `Exec` 连同选项和参数一起传递，从而获取返回值。

## <a name="see-also"></a>请参阅

[活动文档容器](active-document-containers.md)
