---
description: 了解详细信息： CMouseManager 类
title: CMouseManager 类
ms.date: 11/04/2016
f1_keywords:
- CMouseManager
- AFXMOUSEMANAGER/CMouseManager
- AFXMOUSEMANAGER/CMouseManager::AddView
- AFXMOUSEMANAGER/CMouseManager::GetViewDblClickCommand
- AFXMOUSEMANAGER/CMouseManager::GetViewIconId
- AFXMOUSEMANAGER/CMouseManager::GetViewIdByName
- AFXMOUSEMANAGER/CMouseManager::GetViewNames
- AFXMOUSEMANAGER/CMouseManager::LoadState
- AFXMOUSEMANAGER/CMouseManager::SaveState
- AFXMOUSEMANAGER/CMouseManager::SetCommandForDblClk
helpviewer_keywords:
- CMouseManager [MFC], AddView
- CMouseManager [MFC], GetViewDblClickCommand
- CMouseManager [MFC], GetViewIconId
- CMouseManager [MFC], GetViewIdByName
- CMouseManager [MFC], GetViewNames
- CMouseManager [MFC], LoadState
- CMouseManager [MFC], SaveState
- CMouseManager [MFC], SetCommandForDblClk
ms.assetid: a4d05017-4e44-4a40-8b57-4ece0de20481
ms.openlocfilehash: 9816583aa9d05b76f97f1be1487898b5827fbcae
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97331560"
---
# <a name="cmousemanager-class"></a>CMouseManager 类

允许用户在该视图内双击时将不同的命令与特定的 [CView](../../mfc/reference/cview-class.md) 对象相关联。

## <a name="syntax"></a>语法

```
class CMouseManager : public CObject
```

## <a name="members"></a>成员

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CMouseManager：： AddView](#addview)|将 `CView` 对象添加到 " **自定义** " 对话框。 使用 " **自定义** " 对话框，用户可以为列出的每个视图将双击与一个命令相关联。|
|[CMouseManager：： GetViewDblClickCommand](#getviewdblclickcommand)|返回当用户在提供的视图内双击时执行的命令。|
|[CMouseManager：： GetViewIconId](#getviewiconid)|返回与所提供的视图 ID 相关联的图标。|
|[CMouseManager：： GetViewIdByName](#getviewidbyname)|返回与所提供的视图名称关联的视图 ID。|
|[CMouseManager：： GetViewNames](#getviewnames)|检索添加的所有视图名称的列表。|
|[CMouseManager：： LoadState](#loadstate)|`CMouseManager`从 Windows 注册表加载状态。|
|[CMouseManager：： SaveState](#savestate)|将 `CMouseManager` 状态写入 Windows 注册表。|
|[CMouseManager：： SetCommandForDblClk](#setcommandfordblclk)|将提供的命令与提供的视图关联。|

## <a name="remarks"></a>备注

`CMouseManager`类维护对象的集合 `CView` 。 每个视图都由名称和 ID 标识。 这些视图显示在 " **自定义** " 对话框中。 用户通过 " **自定义** " 对话框可以更改与任何视图关联的命令。 当用户在该视图中双击时，将执行关联的命令。 若要从编码角度支持此功能，必须处理 WM_LBUTTONDBLCLK 消息，并在该对象的代码中调用[CWinAppEx：： OnViewDoubleClick](../../mfc/reference/cwinappex-class.md#onviewdoubleclick)函数。 `CView`

不应 `CMouseManager` 手动创建对象。 它将由应用程序的框架创建。 当用户退出应用程序时，也会自动销毁此应用程序。 若要获取应用程序的鼠标管理器指针，请调用 [CWinAppEx：： GetMouseManager](../../mfc/reference/cwinappex-class.md#getmousemanager)。

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

`CMouseManager`

## <a name="requirements"></a>要求

**标头：** afxmousemanager

## <a name="cmousemanageraddview"></a><a name="addview"></a> CMouseManager：： AddView

使用[CMouseManager 类](../../mfc/reference/cmousemanager-class.md)注册[CView](../../mfc/reference/cview-class.md)对象，以支持自定义鼠标行为。

```
BOOL AddView(
    int iViewId,
    UINT uiViewNameResId,
    UINT uiIconId = 0);

BOOL AddView(
    int iId,
    LPCTSTR lpszViewName,
    UINT uiIconId = 0);
```

### <a name="parameters"></a>parameters

*iViewId*<br/>
中视图 ID。

*uiViewNameResId*<br/>
中引用视图名称的资源字符串 ID。

*uiIconId*<br/>
中视图图标 ID。

*iId*<br/>
中视图 ID。

*lpszViewName*<br/>
中视图名称。

### <a name="return-value"></a>返回值

如果成功，则不为 0；否则为 0。

### <a name="remarks"></a>备注

若要支持自定义鼠标行为，必须向对象注册视图 `CMouseManager` 。 派生自类的任何对象 `CView` 都可以通过鼠标管理器注册。 与视图关联的字符串和图标显示在 "**自定义**" 对话框的 "**鼠标**" 选项卡中。

程序员负责创建和维护视图 Id，如 *iViewId* 和 *iId*。

有关如何提供自定义鼠标行为的详细信息，请参阅 [键盘和鼠标自定义](../../mfc/keyboard-and-mouse-customization.md)。

### <a name="example"></a>示例

下面的示例演示如何 `CMouseManager` 使用 `CWinAppEx::GetMouseManager` 方法和 `AddView` 类中的方法来检索指向对象的指针 `CMouseManager` 。 此代码片段是 [状态收集示例](../../overview/visual-cpp-samples.md)的一部分。

[!code-cpp[NVC_MFC_StateCollection#4](../../mfc/reference/codesnippet/cpp/cmousemanager-class_1.cpp)]

## <a name="cmousemanagergetviewdblclickcommand"></a><a name="getviewdblclickcommand"></a> CMouseManager：： GetViewDblClickCommand

返回当用户在提供的视图内双击时执行的命令。

```
UINT GetViewDblClickCommand(int iId) const;
```

### <a name="parameters"></a>parameters

*iId*<br/>
中视图 ID。

### <a name="return-value"></a>返回值

如果视图与命令相关联，则为命令标识符;否则为0。

## <a name="cmousemanagergetviewiconid"></a><a name="getviewiconid"></a> CMouseManager：： GetViewIconId

检索与视图 ID 关联的图标。

```
UINT GetViewIconId(int iViewId) const;
```

### <a name="parameters"></a>parameters

*iViewId*<br/>
中视图 ID。

### <a name="return-value"></a>返回值

如果成功，则为图标资源标识符;否则为0。

### <a name="remarks"></a>备注

如果未使用 [CMouseManager：： AddView](#addview)第一次注册视图，则此方法将失败。

## <a name="cmousemanagergetviewidbyname"></a><a name="getviewidbyname"></a> CMouseManager：： GetViewIdByName

检索与视图名称关联的视图 ID。

```
int GetViewIdByName(LPCTSTR lpszName) const;
```

### <a name="parameters"></a>parameters

*lpszName*<br/>
中视图名称。

### <a name="return-value"></a>返回值

如果成功，则为视图 ID;否则为0。

### <a name="remarks"></a>备注

此方法在通过使用 [CMouseManager：： AddView](#addview)注册的视图中进行搜索。

## <a name="cmousemanagergetviewnames"></a><a name="getviewnames"></a> CMouseManager：： GetViewNames

检索所有已注册的视图名称的列表。

```cpp
void GetViewNames(CStringList& listOfNames) const;
```

### <a name="parameters"></a>parameters

*listOfNames*<br/>
弄对对象的引用 `CStringList` 。

### <a name="remarks"></a>备注

此方法使用 `listOfNames` [CMouseManager：： AddView](#addview)注册的所有视图的名称填充参数。

## <a name="cmousemanagerloadstate"></a><a name="loadstate"></a> CMouseManager：： LoadState

从注册表加载 [CMouseManager 类](../../mfc/reference/cmousemanager-class.md) 的状态。

```
BOOL LoadState(LPCTSTR lpszProfileName = NULL);
```

### <a name="parameters"></a>parameters

*lpszProfileName*<br/>
中注册表项的路径。

### <a name="return-value"></a>返回值

如果成功，则不为 0；否则为 0。

### <a name="remarks"></a>备注

从注册表加载的状态信息包括已注册的视图、视图标识符和关联的命令。 如果参数 *lpszProfileName* 为 NULL，则此函数将加载 `CMouseManager` 由 [CWinAppEx 类](../../mfc/reference/cwinappex-class.md)控制的默认注册表位置的数据。

在大多数情况下，无需直接调用此函数。 它作为工作区初始化过程的一部分被调用。 有关工作区初始化过程的详细信息，请参阅 [CWinAppEx：： LoadState](../../mfc/reference/cwinappex-class.md#loadstate)。

## <a name="cmousemanagersavestate"></a><a name="savestate"></a> CMouseManager：： SaveState

将 [CMouseManager 类](../../mfc/reference/cmousemanager-class.md) 的状态写入注册表。

```
BOOL SaveState(LPCTSTR lpszProfileName = NULL);
```

### <a name="parameters"></a>parameters

*lpszProfileName*<br/>
中注册表项的路径。

### <a name="return-value"></a>返回值

如果成功，则不为 0；否则为 0。

### <a name="remarks"></a>备注

写入注册表的状态信息包括所有已注册的视图、视图标识符和关联的命令。 如果参数 *lpszProfileName* 为 NULL，则此函数会将 `CMouseManager` 数据写入由 [CWinAppEx 类](../../mfc/reference/cwinappex-class.md)控制的默认注册表位置。

在大多数情况下，无需直接调用此函数。 它作为工作区序列化过程的一部分进行调用。 有关工作区序列化过程的详细信息，请参阅 [CWinAppEx：： SaveState](../../mfc/reference/cwinappex-class.md#savestate)。

## <a name="cmousemanagersetcommandfordblclk"></a><a name="setcommandfordblclk"></a> CMouseManager：： SetCommandForDblClk

将自定义命令与首先注册到鼠标管理器的视图关联。

```cpp
void SetCommandForDblClk(
    int iViewId,
    UINT uiCmd);
```

### <a name="parameters"></a>parameters

*iViewId*<br/>
中视图标识符。

*uiCmd*<br/>
中命令标识符。

### <a name="remarks"></a>备注

若要将自定义命令与视图相关联，必须先使用 [CMouseManager：： AddView](#addview)注册视图。 `AddView`方法需要视图标识符作为输入参数。 注册视图后，可以 `CMouseManager::SetCommandForDblClk` 使用提供给的相同视图标识符输入参数调用 `AddView` 。 此后，当用户在注册的视图中双击鼠标时，应用程序将执行 UiCmd 指示的命令 *。* 若要支持自定义鼠标行为，还需要自定义用鼠标管理器注册的视图。 有关自定义鼠标行为的详细信息，请参阅 [键盘和鼠标自定义](../keyboard-and-mouse-customization.md)。

如果将 *uiCmd* 设置为0，则指定的视图将不再与命令相关联。

## <a name="see-also"></a>请参阅

[层次结构图](../../mfc/hierarchy-chart.md)<br/>
[Classes](../../mfc/reference/mfc-classes.md)<br/>
[CWinAppEx 类](../../mfc/reference/cwinappex-class.md)<br/>
[键盘和鼠标自定义](../../mfc/keyboard-and-mouse-customization.md)
