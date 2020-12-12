---
description: '了解详细信息： CCustomCommand (CustomRS) '
title: CCustomCommand (CustomRS.H)
ms.date: 10/22/2018
f1_keywords:
- cmyprovidercommand
- ccustomcommand
helpviewer_keywords:
- OLE DB providers, wizard-generated files
- CMyProviderCommand class in MyProviderRS.H
- CCustomCommand class in CustomRS.H
ms.assetid: b30b956e-cc91-4cf5-9fe6-f8b1ce9cc2a5
ms.openlocfilehash: 35b0e1a1628920a85343a52ce4a003302468884b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97170498"
---
# <a name="ccustomcommand-customrsh"></a>CCustomCommand (CustomRS.H)

`CCustomCommand`类是提供程序命令对象的实现。 它提供 `IAccessor` 、和接口的实现 `ICommandText` `ICommandProperties` 。 `IAccessor`接口与行集中的接口相同。 Command 对象使用访问器指定参数的绑定。 行集对象使用它们来指定输出列的绑定。 `ICommandText`接口是一种以一种方式指定命令的有效方法。 此示例将在 `ICommandText` 以后添加自定义代码时使用该接口; 它还将重写 `ICommand::Execute` 方法。 `ICommandProperties`接口处理命令和行集对象的所有属性。

```cpp
// CCustomCommand
class ATL_NO_VTABLE CCustomCommand :
class ATL_NO_VTABLE CCustomCommand :
   public CComObjectRootEx<CComSingleThreadModel>,
   public IAccessorImpl<CCustomCommand>,
   public ICommandTextImpl<CCustomCommand>,
   public ICommandPropertiesImpl<CCustomCommand>,
   public IObjectWithSiteImpl<CCustomCommand>,
   public IConvertTypeImpl<CCustomCommand>,
   public IColumnsInfoImpl<CCustomCommand>
```

`IAccessor`接口管理命令和行集中使用的所有绑定。 使用者调用了 `IAccessor::CreateAccessor` `DBBINDING` 结构数组。 每个 `DBBINDING` 结构都包含有关应如何处理列绑定 (如类型和长度) 的信息。 提供程序接收结构，然后确定应该如何传输数据以及是否需要进行任何转换。 `IAccessor`接口用于在命令对象中处理命令中的任何参数。

Command 对象还提供的实现 `IColumnsInfo` 。 OLE DB 需要 `IColumnsInfo` 接口。 接口允许使用者从命令检索有关参数的信息。 行集对象使用 `IColumnsInfo` 接口将有关输出列的信息返回给提供程序。

提供程序还包含一个名为的接口 `IObjectWithSite` 。 `IObjectWithSite`接口是在 ATL 2.0 中实现的，并允许实施者将自己的信息传递到其子级。 Command 对象使用 `IObjectWithSite` 信息告诉任何生成的行集对象。

## <a name="see-also"></a>请参阅

[提供程序 Wizard-Generated 文件](../../data/oledb/provider-wizard-generated-files.md)
