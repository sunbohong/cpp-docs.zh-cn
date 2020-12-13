---
description: 了解详细信息： CDockState 类
title: CDockState 类
ms.date: 11/04/2016
f1_keywords:
- CDockState
- AFXADV/CDockState
- AFXADV/CDockState::Clear
- AFXADV/CDockState::GetVersion
- AFXADV/CDockState::LoadState
- AFXADV/CDockState::SaveState
- AFXADV/CDockState::m_arrBarInfo
helpviewer_keywords:
- CDockState [MFC], Clear
- CDockState [MFC], GetVersion
- CDockState [MFC], LoadState
- CDockState [MFC], SaveState
- CDockState [MFC], m_arrBarInfo
ms.assetid: 09e7c10b-3abd-4cb2-ad36-42420fe6bc36
ms.openlocfilehash: 4bdc17ec5a09b812609b8aa71e3f361603c1106f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97184954"
---
# <a name="cdockstate-class"></a>CDockState 类

在永久性内存（文件）中加载、卸载或清除一个或多个停靠控件条状态的序列化 `CObject` 类。

## <a name="syntax"></a>语法

```
class CDockState : public CObject
```

## <a name="members"></a>成员

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CDockState：： Clear](#clear)|清除停靠状态信息。|
|[CDockState：： GetVersion](#getversion)|检索存储的 bar 状态的版本号。|
|[CDockState：： LoadState](#loadstate)|从注册表或检索状态信息。INI 文件。|
|[CDockState：： SaveState](#savestate)|将状态信息保存到注册表或 INI 文件中。|

### <a name="public-data-members"></a>公共数据成员

|名称|描述|
|----------|-----------------|
|[CDockState：： m_arrBarInfo](#m_arrbarinfo)|指向存储的停靠状态信息的指针数组，其中每个控件栏都有一个条目。|

## <a name="remarks"></a>备注

停靠状态包括栏的大小和位置以及是否停靠。 检索存储的停靠状态时， `CDockState` 检查条形的位置，如果在当前屏幕设置下看不到条形，则 `CDockState` 缩放栏的位置以使其可见。 的主要用途 `CDockState` 是保存多个控制条的全部状态，并允许将该状态保存并加载到注册表、应用程序的。INI 文件，或以二进制形式包含在 `CArchive` 对象内容中。

此栏可以是任何可停靠的控制条，包括工具栏、状态栏或对话栏。 `CDockState` 对象通过对象写入或读取文件 `CArchive` 。

[CFrameWnd：： GetDockState](../../mfc/reference/cframewnd-class.md#getdockstate) 检索所有框架窗口对象的状态信息 `CControlBar` ，并将其放入 `CDockState` 对象。 然后，你可以 `CDockState` 通过 [序列化](../../mfc/reference/cobject-class.md#serialize) 或 [CDockState：： SaveState](#savestate)将对象的内容写入存储。 如果以后想要还原框架窗口中的控件条的状态，可以使用 `Serialize` 或 [CDockState：： LoadState](#loadstate)加载状态，然后使用 [CFrameWnd：： SetDockState](../../mfc/reference/cframewnd-class.md#setdockstate) 将保存的状态应用于框架窗口的控件条。

有关停靠控件条的详细信息，请参阅文章 [控件栏](../../mfc/control-bars.md)、 [工具栏：停靠和浮动](../../mfc/docking-and-floating-toolbars.md)以及 [框架窗口](../../mfc/frame-windows.md)。

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

`CDockState`

## <a name="requirements"></a>要求

**标头：** afxadv

## <a name="cdockstateclear"></a><a name="clear"></a> CDockState：： Clear

调用此函数可清除对象中存储的所有停靠信息 `CDockState` 。

```cpp
void Clear();
```

### <a name="remarks"></a>备注

这不仅包括是否停靠条形，还包括条形图的大小和位置以及它是否可见。

## <a name="cdockstategetversion"></a><a name="getversion"></a> CDockState：： GetVersion

调用此函数可检索存储的条状态的版本号。

```
DWORD GetVersion();
```

### <a name="return-value"></a>返回值

如果存储的栏信息早于当前栏状态，则为 1;如果存储的条形信息与当前栏状态相同，则为2。

### <a name="remarks"></a>备注

版本支持使修改后的栏能够添加新的持久性属性，同时仍然能够检测和加载由较早版本的 bar 创建的持久状态。

## <a name="cdockstateloadstate"></a><a name="loadstate"></a> CDockState：： LoadState

调用此函数可从注册表或检索状态信息。INI 文件。

```cpp
void LoadState(LPCTSTR lpszProfileName);
```

### <a name="parameters"></a>parameters

*lpszProfileName*<br/>
指向一个 null teminated 字符串，该字符串指定初始化文件中某一节的名称或 Windows 注册表中存储状态信息的键。

### <a name="remarks"></a>备注

配置文件名称是应用程序的部分。INI 文件或包含这些栏的状态信息的注册表。 可以将控制条状态信息保存到注册表或。INI 文件 `SaveState` 。

## <a name="cdockstatem_arrbarinfo"></a><a name="m_arrbarinfo"></a> CDockState：： m_arrBarInfo

一个 `CPtrArray` 对象，它是指向每个控件栏的存储控件条信息的指针的数组，这些控件栏在对象中保存了状态信息 `CDockState` 。

```
CPtrArray m_arrBarInfo;
```

## <a name="cdockstatesavestate"></a><a name="savestate"></a> CDockState：： SaveState

调用此函数可将状态信息保存到注册表或。INI 文件。

```cpp
void SaveState(LPCTSTR lpszProfileName);
```

### <a name="parameters"></a>parameters

*lpszProfileName*<br/>
指向一个 null teminated 字符串，该字符串指定初始化文件中某一节的名称或 Windows 注册表中存储状态信息的键。

### <a name="remarks"></a>备注

配置文件名称是应用程序的部分。INI 文件或包含控件条状态信息的注册表。 `SaveState` 还保存当前屏幕大小。 您可以从注册表或检索控件条信息。INI 文件 `LoadState` 。

## <a name="see-also"></a>请参阅

[CObject 类](../../mfc/reference/cobject-class.md)<br/>
[层次结构图](../../mfc/hierarchy-chart.md)
