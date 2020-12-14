---
description: 了解详细信息： ICommandUI 接口
title: ICommandUI 接口
ms.date: 09/07/2019
f1_keywords:
- ICommandUI
- AFXWINFORMS/ICommandUI
- AFXWINFORMS/icommandui__Check
- AFXWINFORMS/ICommandUI::ContinueRouting
- AFXWINFORMS/ICommandUI::Enabled
- AFXWINFORMS/ICommandUI::ID
- AFXWINFORMS/ICommandUI::Index
- AFXWINFORMS/ICommandUI::Radio
- AFXWINFORMS/ICommandUI::Text
helpviewer_keywords:
- ICommandUI interface [MFC]
ms.assetid: 134afe8d-dcdf-47ca-857a-a166a6b665dd
ms.openlocfilehash: 26ddd4366994c9e0cecba2b4902a36e1038896c2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97219533"
---
# <a name="icommandui-interface"></a>ICommandUI 接口

管理用户界面命令。

## <a name="syntax"></a>语法

```
interface class ICommandUI
```

## <a name="members"></a>成员

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[icommandui__Check](#check)|将此命令的用户界面项设置为相应的复选状态。|
|[ICommandUI::ContinueRouting](#continuerouting)|告诉命令路由机制继续向下传递处理程序链中的当前消息。|
|[ICommandUI：： Enabled](#enabled)|启用或禁用此命令的用户界面项。|
|[ICommandUI：： ID](#id)|获取由对象表示的用户界面对象的 ID `ICommandUI` 。|
|[ICommandUI：： Index](#index)|获取由对象表示的用户界面对象的索引 `ICommandUI` 。|
|[ICommandUI：：收音机](#radio)|将此命令的用户界面项设置为相应的复选状态。|
|[ICommandUI：： Text](#text)|为此命令设置用户界面项的文本。|

### <a name="remarks"></a>备注

此接口提供管理用户界面命令的方法和属性。 `ICommandUI` 类似于 [CCmdUI 类](../../mfc/reference/ccmdui-class.md)，但 `ICommandUI` 用于与 .net 组件进行互操作的 MFC 应用程序除外。

`ICommandUI` 在 [ICommandTarget](../../mfc/reference/icommandtarget-interface.md)派生的类中的 ON_UPDATE_COMMAND_UI 处理程序中使用。 当激活应用程序的用户 (选中或单击菜单) 时，每个菜单项都将显示为 "已启用" 或 "已禁用"。 每个菜单命令的目标通过实现 ON_UPDATE_COMMAND_UI 处理程序来提供此信息。 对于应用程序中的每个命令用户界面对象，使用 [类向导](mfc-class-wizard.md) 创建每个处理程序的消息映射项和函数原型。

有关如何 `ICommandUI` 在命令路由中使用接口的详细信息，请参阅 [如何：将命令路由添加到 Windows 窗体控件](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)。

有关使用 Windows 窗体的详细信息，请参阅 [在 MFC 中使用 Windows 窗体用户控件](../../dotnet/using-a-windows-form-user-control-in-mfc.md)。

有关如何在 MFC 中管理用户界面命令的详细信息，请参阅 [CCmdUI 类](../../mfc/reference/ccmdui-class.md)。

## <a name="icommanduicheck"></a><a name="check"></a> ICommandUI：： Check

将此命令的用户界面项设置为相应的复选状态。

```
property UICheckState Check;
```

### <a name="remarks"></a>备注

此属性将此命令的用户界面项设置为相应的复选状态。 将 "检查" 设置为以下值：

- 0取消选中
- 1个检查
- 2集不确定

## <a name="icommanduicontinuerouting"></a><a name="continuerouting"></a> ICommandUI::ContinueRouting

告诉命令路由机制继续向下传递处理程序链中的当前消息。

```cpp
void ContinueRouting();
```

### <a name="remarks"></a>备注

这是一个高级成员函数，应与返回 FALSE 的 ON_COMMAND_EX 处理程序结合使用。 有关详细信息，请参阅技术说明 TN006：消息映射。

## <a name="icommanduienabled"></a><a name="enabled"></a> ICommandUI：： Enabled

启用或禁用此命令的用户界面项。

```
property bool Enabled;
```

### <a name="remarks"></a>备注

此属性将启用或禁用此命令的用户界面项。 设置为 TRUE 可启用项，设置为 FALSE 可禁用项。

## <a name="icommanduiid"></a><a name="id"></a> ICommandUI：： ID

获取由 ICommandUI 对象表示的用户界面对象的 ID。

```
property unsigned int ID;
```

### <a name="remarks"></a>备注

此属性获取 ICommandUI 对象所表示的菜单项、工具栏按钮或其他用户界面对象的句柄)  (ID。

## <a name="icommanduiindex"></a><a name="index"></a> ICommandUI：： Index

获取由 ICommandUI 对象表示的用户界面对象的索引。

```
property unsigned int Index;
```

### <a name="remarks"></a>备注

此属性获取 ICommandUI 对象所表示的菜单项、工具栏按钮或其他用户界面对象的句柄) 的索引 (。

## <a name="icommanduiradio"></a><a name="radio"></a> ICommandUI：：收音机

将此命令的用户界面项设置为相应的复选状态。

```
property bool Radio;
```

### <a name="remarks"></a>备注

此属性将此命令的用户界面项设置为相应的复选状态。 将 "收音机" 设置为 "TRUE" 以启用该项;否则为 FALSE。

## <a name="icommanduitext"></a><a name="text"></a> ICommandUI：： Text

为此命令设置用户界面项的文本。

```
property String^ Text;
```

### <a name="remarks"></a>备注

此属性设置此命令的用户界面项的文本。 将文本设置为文本字符串句柄。

## <a name="requirements"></a>要求

**标头：** 在程序集 atlmfc\lib\mfcmifc80.dll 中定义的 afxwinforms () 

## <a name="see-also"></a>请参阅

[CCmdUI 类](../../mfc/reference/ccmdui-class.md)
