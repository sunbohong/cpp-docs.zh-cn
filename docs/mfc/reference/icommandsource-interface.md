---
description: 了解详细信息： ICommandSource 接口
title: ICommandSource 接口
ms.date: 03/27/2019
f1_keywords:
- ICommandSource
- AFXWINFORMS/ICommandSource
- AFXWINFORMS/ICommandSource::AddCommandHandler
- AFXWINFORMS/ICommandSource::AddCommandRangeHandler
- AFXWINFORMS/ICommandSource::AddCommandRangeUIHandler
- AFXWINFORMS/ICommandSource::AddCommandUIHandler
- AFXWINFORMS/ICommandSource::PostCommand
- AFXWINFORMS/ICommandSource::RemoveCommandHandler
- AFXWINFORMS/ICommandSource::RemoveCommandRangeHandler
- AFXWINFORMS/ICommandSource::RemoveCommandRangeUIHandler
- AFXWINFORMS/ICommandSource::RemoveCommandUIHandler
- AFXWINFORMS/ICommandSource::SendCommand
helpviewer_keywords:
- ICommandSource interface [MFC]
ms.assetid: a4b1f698-c09f-4ba8-9b13-0e74a0a4967e
ms.openlocfilehash: 711baeccd76c88db365b465cbc3c4cc05048a0f2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97219585"
---
# <a name="icommandsource-interface"></a>ICommandSource 接口

管理从命令源对象发送到用户控件的命令。

## <a name="syntax"></a>语法

```cpp
interface class ICommandSource
```

## <a name="members"></a>成员

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[ICommandSource：： AddCommandHandler](#addcommandhandler)|将命令处理程序添加到命令源对象。|
|[ICommandSource：： AddCommandRangeHandler](#addcommandrangehandler)|向命令源对象添加一组命令处理程序。|
|[ICommandSource：： AddCommandRangeUIHandler](#addcommandrangeuihandler)|向命令源对象添加一组用户界面命令消息处理程序。|
|[ICommandSource：： AddCommandUIHandler](#addcommandrangeuihandler)|向命令源对象添加用户界面命令消息处理程序。|
|[ICommandSource：:P ostCommand](#postcommand)|在不等待消息处理的情况下发布消息。|
|[ICommandSource：： RemoveCommandHandler](#removecommandhandler)|从命令源对象中删除命令处理程序。|
|[ICommandSource：： RemoveCommandRangeHandler](#removecommandrangehandler)|从命令源对象中移除一组命令处理程序。|
|[ICommandSource：： RemoveCommandRangeUIHandler](#removecommandrangeuihandler)|从命令源对象中移除一组用户界面命令消息处理程序。|
|[ICommandSource：： RemoveCommandUIHandler](#removecommandrangeuihandler)|从命令源对象中删除用户界面命令消息处理程序。|
|[ICommandSource：： SendCommand](#sendcommand)|发送消息，并在返回前等待处理。|

### <a name="remarks"></a>备注

在 MFC 视图中承载用户控件时， [CWinFormsView 类](../../mfc/reference/cwinformsview-class.md) 将命令和更新命令 UI 消息路由到用户控件，以允许它处理 MFC 命令 (例如，框架菜单项和工具栏按钮) 。 通过实现 [ICommandTarget 接口](../../mfc/reference/icommandtarget-interface.md)，可为用户控件指定对对象的引用 `ICommandSource` 。

有关如何使用的示例，请参阅 [如何：将命令路由添加到 Windows 窗体控件](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md) `ICommandTarget` 。

有关使用 Windows 窗体的详细信息，请参阅 [在 MFC 中使用 Windows 窗体用户控件](../../dotnet/using-a-windows-form-user-control-in-mfc.md)。

### <a name="requirements"></a>要求

**标头：** 在程序集 atlmfc\lib\mfcmifc80.dll 中定义的 afxwinforms () 

## <a name="icommandsourceaddcommandhandler"></a><a name="addcommandhandler"></a> ICommandSource：： AddCommandHandler

将命令处理程序添加到命令源对象。

```cpp
void AddCommandHandler(
    unsigned int cmdID,
    CommandHandler^ cmdHandler);
```

### <a name="parameters"></a>parameters

*cmdID*<br/>
命令 ID。
*cmdHandler*<br/>
命令处理程序方法的句柄。

### <a name="remarks"></a>备注

此方法将命令处理程序 cmdHandler 添加到命令源对象，并将该处理程序映射到 cmdID。
有关如何使用 AddCommandHandler 的示例，请参阅 [如何：将命令路由添加到 Windows 窗体控件](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md) 。

## <a name="icommandsourceaddcommandrangehandler"></a><a name="addcommandrangehandler"></a> ICommandSource：： AddCommandRangeHandler

向命令源对象添加一组命令处理程序。

```cpp
void AddCommandRangeHandler(
    unsigned int cmdIDMin,
    unsigned int cmdIDMax,
    CommandHandler^ cmdHandler);
```

### <a name="parameters"></a>parameters

*cmdIDMin*<br/>
命令 ID 范围的起始索引。
*cmdIDMax*<br/>
命令 ID 范围的结束索引。
*cmdHandler*<br/>
命令映射到的消息处理程序方法的句柄。

### <a name="remarks"></a>备注

此方法将一系列连续的命令 Id 映射到单个消息处理程序，并将其添加到命令源对象。 这用于处理一组具有一种方法的相关按钮。

## <a name="icommandsourceaddcommandrangeuihandler"></a><a name="addcommandrangeuihandler"></a> ICommandSource：： AddCommandRangeUIHandler

向命令源对象添加一组用户界面命令消息处理程序。

```cpp
void AddCommandRangeUIHandler(
    unsigned int cmdIDMin,
    unsigned int cmdIDMax,
    CommandUIHandler^ cmdUIHandler);
```

### <a name="parameters"></a>parameters

*cmdIDMin*<br/>
命令 ID 范围的起始索引。
*cmdIDMax*<br/>
命令 ID 范围的结束索引。
*cmdHandler*<br/>
命令映射到的消息处理程序方法的句柄。

### <a name="remarks"></a>备注

此方法将一系列连续的命令 Id 映射到一个用户界面命令消息处理程序，并将其添加到命令源对象。 这用于处理一组具有一种方法的相关按钮。

## <a name="icommandsourceaddcommanduihandler"></a><a name="addcommanduihandler"></a> ICommandSource：： AddCommandUIHandler

向命令源对象添加用户界面命令消息处理程序。

```cpp
void AddCommandUIHandler(
    unsigned int cmdID,
    CommandUIHandler^ cmdUIHandler);
```

### <a name="parameters"></a>parameters

*cmdID*<br/>
命令 ID。
*cmdUIHandler*<br/>
用户界面命令消息处理程序方法的句柄。

### <a name="remarks"></a>备注

此方法将用户界面命令消息处理程序 cmdHandler 添加到命令源对象，并将该处理程序映射到 cmdID。

## <a name="icommandsourcepostcommand"></a><a name="postcommand"></a> ICommandSource：:P ostCommand

在不等待消息处理的情况下发布消息。

```cpp
void PostCommand(unsigned int command);
```

### <a name="parameters"></a>parameters

*command*<br/>
要发布的消息的命令 ID。

### <a name="remarks"></a>备注

此方法以异步方式发布映射到由命令指定的 ID 的消息。 它调用 CWnd：:P ostMessage 将消息放入窗口的消息队列中，然后返回而不等待相应的窗口处理该消息。

## <a name="icommandsourceremovecommandhandler"></a><a name="removecommandhandler"></a> ICommandSource：： RemoveCommandHandler

从命令源对象中删除命令处理程序。

```cpp
void RemoveCommandHandler(unsigned int cmdID);
```

### <a name="parameters"></a>parameters

*cmdID*<br/>
命令 ID。

### <a name="remarks"></a>备注

此方法从命令源对象中删除映射到 cmdID 的命令处理程序。

## <a name="icommandsourceremovecommandrangehandler"></a><a name="removecommandrangehandler"></a> ICommandSource：： RemoveCommandRangeHandler

从命令源对象中移除一组命令处理程序。

```cpp
void RemoveCommandRangeUIHandler(
    unsigned int cmdIDMin,
    unsigned int cmdIDMax);
```

### <a name="parameters"></a>parameters

*cmdIDMin*<br/>
命令 ID 范围的起始索引。
*cmdIDMax*<br/>
命令 ID 范围的结束索引。

### <a name="remarks"></a>备注

此方法从命令源对象中删除一组消息处理程序，这些消息处理程序映射到由 cmdIDMin 和 cmdIDMax 指定的命令 Id。

## <a name="icommandsourceremovecommandrangeuihandler"></a><a name="removecommandrangeuihandler"></a> ICommandSource：： RemoveCommandRangeUIHandler

从命令源对象中移除一组用户界面命令消息处理程序。

```cpp
void RemoveCommandRangeUIHandler(
    unsigned int cmdIDMin,
    unsigned int cmdIDMax);
```

### <a name="parameters"></a>parameters

*cmdIDMin*<br/>
命令 ID 范围的起始索引。
*cmdIDMax*<br/>
命令 ID 范围的结束索引。

### <a name="remarks"></a>备注

此方法从命令源对象中移除一组用户界面命令消息处理程序，并映射到由 cmdIDMin 和 cmdIDMax 指定的命令 Id。

## <a name="icommandsourceremovecommanduihandler"></a><a name="removecommanduihandler"></a> ICommandSource：： RemoveCommandUIHandler

从命令源对象中删除用户界面命令消息处理程序。

```cpp
void RemoveCommandUIHandler(unsigned int cmdID);
```

### <a name="parameters"></a>parameters

*cmdID*<br/>
命令 ID。

### <a name="remarks"></a>备注

此方法从命令源对象中删除映射到 cmdID 的用户界面命令消息处理程序。

## <a name="icommandsourcesendcommand"></a><a name="sendcommand"></a> ICommandSource：： SendCommand

发送消息，并在返回前等待处理。

```cpp
void SendCommand(unsigned int command);
```

### <a name="parameters"></a>parameters

*command*<br/>
要发送的消息的命令 ID。

### <a name="remarks"></a>备注

此方法同步发送映射到由命令指定的 ID 的消息。 它调用 CWnd：： SendMessage 将消息放入窗口的消息队列中，并等待该窗口过程在返回前处理该消息。

## <a name="see-also"></a>请参阅

[如何：将命令路由添加到 Windows 窗体控件](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)<br/>
[ICommandTarget 接口](../../mfc/reference/icommandtarget-interface.md)
