---
description: 了解详细信息： ICommandTarget 接口
title: ICommandTarget 接口
ms.date: 11/04/2016
f1_keywords:
- ICommandTarget
- AFXWINFORMS/ICommandTarget
- AFXWINFORMS/ICommandTarget::Initialize
helpviewer_keywords:
- ICommandTarget interface [MFC]
ms.assetid: dd9927f6-3479-4e7c-8ef9-13206cf901f3
ms.openlocfilehash: 6deb11ecca94160ea19225fb955826845a4cdefa
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97219572"
---
# <a name="icommandtarget-interface"></a>ICommandTarget 接口

为用户控件提供一个接口，用于从命令源对象接收命令。

## <a name="syntax"></a>语法

```
interface class ICommandTarget
```

## <a name="members"></a>成员

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[ICommandTarget：： Initialize](#initialize)|初始化命令目标对象。|

## <a name="remarks"></a>备注

在 MFC 视图中承载用户控件时， [CWinFormsView](../../mfc/reference/cwinformsview-class.md) 将命令和更新命令 UI 消息路由到用户控件，以允许它处理 MFC 命令 (例如，框架菜单项和工具栏按钮) 。 通过实现 `ICommandTarget` ，可以为用户控件指定对 [ICommandSource](../../mfc/reference/icommandsource-interface.md) 对象的引用。

有关如何使用的示例，请参阅 [如何：将命令路由添加到 Windows 窗体控件](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md) `ICommandTarget` 。

有关使用 Windows 窗体的详细信息，请参阅 [在 MFC 中使用 Windows 窗体用户控件](../../dotnet/using-a-windows-form-user-control-in-mfc.md)。

## <a name="requirements"></a>要求

**标头：** 在程序集 atlmfc\lib\mfcmifc80.dll 中定义的 afxwinforms () 

## <a name="icommandtargetinitialize"></a><a name="initialize"></a> ICommandTarget：： Initialize

初始化命令目标对象。

```cpp
void Initialize(ICommandSource^ cmdSource);
```

### <a name="parameters"></a>parameters

*cmdSource*<br/>
命令源对象的句柄。

### <a name="remarks"></a>备注

在 MFC 视图中承载用户控件时，CWinFormsView 将命令和更新命令 UI 消息路由到用户控件，以允许它处理 MFC 命令。

此方法初始化命令目标对象，并将其与指定的命令源对象 cmdSource 关联。 应在用户控件类实现中调用此方法。 在初始化时，应通过调用初始化实现中的 ICommandSource：： AddCommandHandler，向命令源对象注册命令处理程序。 有关如何使用 Initialize 实现此目的的示例，请参阅如何：将命令路由添加到 Windows 窗体控件。

## <a name="see-also"></a>请参阅

[如何：将命令路由添加到 Windows 窗体控件](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)<br/>
[ICommandSource 接口](../../mfc/reference/icommandsource-interface.md)
