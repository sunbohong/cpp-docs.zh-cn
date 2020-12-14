---
description: 了解详细信息： CUserToolsManager 类
title: CUserToolsManager 类
ms.date: 11/04/2016
f1_keywords:
- CUserToolsManager
- AFXUSERTOOLSMANAGER/CUserToolsManager
- AFXUSERTOOLSMANAGER/CUserToolsManager::CUserToolsManager
- AFXUSERTOOLSMANAGER/CUserToolsManager::CreateNewTool
- AFXUSERTOOLSMANAGER/CUserToolsManager::FindTool
- AFXUSERTOOLSMANAGER/CUserToolsManager::GetArgumentsMenuID
- AFXUSERTOOLSMANAGER/CUserToolsManager::GetDefExt
- AFXUSERTOOLSMANAGER/CUserToolsManager::GetFilter
- AFXUSERTOOLSMANAGER/CUserToolsManager::GetInitialDirMenuID
- AFXUSERTOOLSMANAGER/CUserToolsManager::GetMaxTools
- AFXUSERTOOLSMANAGER/CUserToolsManager::GetToolsEntryCmd
- AFXUSERTOOLSMANAGER/CUserToolsManager::GetUserTools
- AFXUSERTOOLSMANAGER/CUserToolsManager::InvokeTool
- AFXUSERTOOLSMANAGER/CUserToolsManager::IsUserToolCmd
- AFXUSERTOOLSMANAGER/CUserToolsManager::LoadState
- AFXUSERTOOLSMANAGER/CUserToolsManager::MoveToolDown
- AFXUSERTOOLSMANAGER/CUserToolsManager::MoveToolUp
- AFXUSERTOOLSMANAGER/CUserToolsManager::RemoveTool
- AFXUSERTOOLSMANAGER/CUserToolsManager::SaveState
- AFXUSERTOOLSMANAGER/CUserToolsManager::SetDefExt
- AFXUSERTOOLSMANAGER/CUserToolsManager::SetFilter
helpviewer_keywords:
- CUserToolsManager [MFC], CUserToolsManager
- CUserToolsManager [MFC], CreateNewTool
- CUserToolsManager [MFC], FindTool
- CUserToolsManager [MFC], GetArgumentsMenuID
- CUserToolsManager [MFC], GetDefExt
- CUserToolsManager [MFC], GetFilter
- CUserToolsManager [MFC], GetInitialDirMenuID
- CUserToolsManager [MFC], GetMaxTools
- CUserToolsManager [MFC], GetToolsEntryCmd
- CUserToolsManager [MFC], GetUserTools
- CUserToolsManager [MFC], InvokeTool
- CUserToolsManager [MFC], IsUserToolCmd
- CUserToolsManager [MFC], LoadState
- CUserToolsManager [MFC], MoveToolDown
- CUserToolsManager [MFC], MoveToolUp
- CUserToolsManager [MFC], RemoveTool
- CUserToolsManager [MFC], SaveState
- CUserToolsManager [MFC], SetDefExt
- CUserToolsManager [MFC], SetFilter
ms.assetid: bdfa37ae-efca-4616-abb5-9d0dcd2d335b
ms.openlocfilehash: 1c6b3b6ec2912a0093929ac117d878d54ed9757f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97344947"
---
# <a name="cusertoolsmanager-class"></a>CUserToolsManager 类

维护应用程序中的 [CUserTool 类](../../mfc/reference/cusertool-class.md) 对象的集合。 用户工具是运行外部应用程序的菜单项。 `CUserToolsManager` 对象使用户或开发人员能够将新的用户工具添加到应用程序中。 它支持与用户工具关联的命令的执行，并将与用户工具相关的信息保存到 Windows 注册表中。

## <a name="syntax"></a>语法

```
class CUserToolsManager : public CObject
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CUserToolsManager::CUserToolsManager](#cusertoolsmanager)|构造一个 `CUserToolsManager`。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CUserToolsManager::CreateNewTool](#createnewtool)|创建新的用户工具。|
|[CUserToolsManager::FindTool](#findtool)|返回指向对象的指针，该 `CMFCUserTool` 对象与指定的命令 ID 相关联。|
|[CUserToolsManager::GetArgumentsMenuID](#getargumentsmenuid)|返回与 "**自定义**" 对话框的 "**工具**" 选项卡上的 "**参数**" 菜单相关联的资源 ID。|
|[CUserToolsManager::GetDefExt](#getdefext)|返回 "**文件打开**" 对话框 ( [CFileDialog](../../mfc/reference/cfiledialog-class.md#cfiledialog) ") 在"**自定义**"对话框的"**工具**"选项卡上的"**命令**"字段中使用的默认扩展名。|
|[CUserToolsManager::GetFilter](#getfilter)|返回 "**文件打开**" 对话框 ( [CFileDialog 类](../../mfc/reference/cfiledialog-class.md)) 在 "**自定义**" 对话框的 "**工具**" 选项卡上的 "**命令**" 字段中使用的文件筛选器。|
|[CUserToolsManager::GetInitialDirMenuID](#getinitialdirmenuid)|返回与 "**自定义**" 对话框的 "**工具**" 选项卡上的 "**初始目录**" 菜单相关联的资源 ID。|
|[CUserToolsManager::GetMaxTools](#getmaxtools)|返回可在应用程序中分配的用户工具的最大数目。|
|[CUserToolsManager::GetToolsEntryCmd](#gettoolsentrycmd)|返回用户工具菜单项占位符的命令 ID。|
|[CUserToolsManager::GetUserTools](#getusertools)|返回对用户工具列表的引用。|
|[CUserToolsManager::InvokeTool](#invoketool)|执行与具有指定命令 ID 的用户工具相关联的应用程序。|
|[CUserToolsManager::IsUserToolCmd](#isusertoolcmd)|确定命令 ID 是否与用户工具相关联。|
|[CUserToolsManager：： LoadState](#loadstate)|从 Windows 注册表加载有关用户工具的信息。|
|[CUserToolsManager::MoveToolDown](#movetooldown)|在用户工具列表中向下移动指定的用户工具。|
|[CUserToolsManager::MoveToolUp](#movetoolup)|在用户工具列表中上移指定的用户工具。|
|[CUserToolsManager::RemoveTool](#removetool)|从应用程序中删除指定的用户工具。|
|[CUserToolsManager：： SaveState](#savestate)|在 Windows 注册表中存储有关用户工具的信息。|
|[CUserToolsManager::SetDefExt](#setdefext)|指定 **文件打开** 对话框 ( [CFileDialog) 类](../../mfc/reference/cfiledialog-class.md)在 "**自定义**" 对话框的 "**工具**" 选项卡上的 "**命令**" 字段中使用的默认扩展名。|
|[CUserToolsManager::SetFilter](#setfilter)|指定文件 **打开** 对话框 ( [CFileDialog 类](../../mfc/reference/cfiledialog-class.md)) 在 "**自定义**" 对话框的 "**工具**" 选项卡上的 "**命令**" 字段中使用的文件筛选器。|

## <a name="remarks"></a>备注

若要将用户工具合并到您的应用程序中，您必须：

1. 为用户工具菜单项保留一个菜单项和一个关联的命令 ID。

2. 为用户可在应用程序中定义的每个用户工具保留顺序命令 ID。

3. 调用 [CWinAppEx：： EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools) 方法，并提供以下参数：菜单命令 ID、第一个用户工具命令 id 以及最后一个用户工具命令 id。

`CUserToolsManager`每个应用程序只能有一个全局对象。

有关用户工具的示例，请参阅 VisualStudioDemo 示例项目。

## <a name="example"></a>示例

下面的示例演示如何检索对对象的引用 `CUserToolsManager` 以及如何创建新的用户工具。 此代码片段是 [Visual Studio 演示示例](../../overview/visual-cpp-samples.md)的一部分。

[!code-cpp[NVC_MFC_VisualStudioDemo#38](../../mfc/codesnippet/cpp/cusertoolsmanager-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

`CUserToolsManager`

## <a name="requirements"></a>要求

**标头：** afxusertoolsmanager

## <a name="cusertoolsmanagercreatenewtool"></a><a name="createnewtool"></a> CUserToolsManager::CreateNewTool

创建新的用户工具。

```
CUserTool* CreateNewTool();
```

### <a name="return-value"></a>返回值

指向新创建的用户工具的指针; 如果用户工具的数量超过最大值，则为 NULL。 返回的类型与 `CWinAppEx::EnableUserTools` 作为 *pToolRTC* 参数传递给的类型相同。

### <a name="remarks"></a>备注

此方法查找在对 [CWinAppEx：： EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools) 的调用中提供的范围中的第一个可用菜单命令 ID，并为该用户工具指定此 id。

如果工具的数量已达到最大值，则该方法将失败。 当范围内的所有命令 Id 都分配给用户工具时，会发生这种情况。 可以通过调用 [CUserToolsManager：： GetMaxTools](#getmaxtools)来检索工具的最大数目。 可以通过调用 [CUserToolsManager：： GetUserTools](#getusertools) 方法获取对工具列表的访问权限。

## <a name="cusertoolsmanagercusertoolsmanager"></a><a name="cusertoolsmanager"></a> CUserToolsManager::CUserToolsManager

构造一个 `CUserToolsManager`。 每个应用程序最多只能有一个用户工具管理器。

```
CUserToolsManager();

CUserToolsManager(
    const UINT uiCmdToolsDummy,
    const UINT uiCmdFirst,
    const UINT uiCmdLast,
    CRuntimeClass* pToolRTC=RUNTIME_CLASS(CUserTool),
    UINT uArgMenuID=0,
    UINT uInitDirMenuID=0);
```

### <a name="parameters"></a>parameters

*uiCmdToolsDummy*<br/>
中一个无符号整数，框架使用该整数作为 "用户工具" 菜单的命令 ID 占位符。

*uiCmdFirst*<br/>
中第一个用户工具命令的命令 ID。

*uiCmdLast*<br/>
中最后一个用户工具命令的命令 ID。

*pToolRTC*<br/>
中 [CUserToolsManager：： CreateNewTool](#createnewtool) 创建的类。 通过使用此类，可以使用 [CUserTool 类](../../mfc/reference/cusertool-class.md) 的派生类型，而不是使用默认实现。

*uArgMenuID*<br/>
中参数弹出菜单的菜单资源 ID。

*uInitDirMenuID*<br/>
中初始目录弹出菜单的菜单资源 ID。

### <a name="remarks"></a>备注

请勿调用此构造函数。 改为调用 [CWinAppEx：： EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools) 以启用用户工具，并调用 [CWinAppEx：： GetUserToolsManager](../../mfc/reference/cwinappex-class.md#getusertoolsmanager) 来获取指向的指针 `CUserToolsManager` 。 有关详细信息，请参阅 [用户定义的工具](../../mfc/user-defined-tools.md)。

## <a name="cusertoolsmanagerfindtool"></a><a name="findtool"></a> CUserToolsManager::FindTool

返回指向与指定的命令 ID 相关联的 [CUserTool 类](../../mfc/reference/cusertool-class.md) 对象的指针。

```
CUserTool* FindTool(UINT uiCmdId) const;
```

### <a name="parameters"></a>parameters

*uiCmdId*<br/>
中菜单命令标识符。

### <a name="return-value"></a>返回值

如果成功，则为指向 [CUserTool 类](../../mfc/reference/cusertool-class.md) 或 `CUserTool` 派生对象的指针; 否则为 NULL。

### <a name="remarks"></a>备注

如果 `FindTool` 成功，则返回的类型与 [CWinAppEx：： EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools)的 *pToolRTC* 参数的类型相同。

## <a name="cusertoolsmanagergetargumentsmenuid"></a><a name="getargumentsmenuid"></a> CUserToolsManager::GetArgumentsMenuID

返回与 "**自定义**" 对话框的 "**工具**" 选项卡上的 "**参数**" 菜单相关联的资源 ID。

```
UINT GetArgumentsMenuID() const;
```

### <a name="return-value"></a>返回值

菜单资源的标识符。

### <a name="remarks"></a>备注

[CWinAppEx：： EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools)的 *uArgMenuID* 参数指定资源的 ID。

## <a name="cusertoolsmanagergetdefext"></a><a name="getdefext"></a> CUserToolsManager::GetDefExt

返回 "**文件打开**" 对话框 ( [CFileDialog](../../mfc/reference/cfiledialog-class.md#cfiledialog) ") 在"**自定义**"对话框的"**工具**"选项卡上的"**命令**"字段中使用的默认扩展名。

```
const CString& GetDefExt() const;
```

### <a name="return-value"></a>返回值

对 `CString` 包含扩展名的对象的引用。

## <a name="cusertoolsmanagergetfilter"></a><a name="getfilter"></a> CUserToolsManager::GetFilter

返回 "**文件打开**" 对话框 ( [CFileDialog 类](../../mfc/reference/cfiledialog-class.md)) 在 "**自定义**" 对话框的 "**工具**" 选项卡上的 "**命令**" 字段中使用的文件筛选器。

```
const CString& GetFilter() const;
```

### <a name="return-value"></a>返回值

对 `CString` 包含筛选器的对象的引用。

## <a name="cusertoolsmanagergetinitialdirmenuid"></a><a name="getinitialdirmenuid"></a> CUserToolsManager::GetInitialDirMenuID

返回与 "**自定义**" 对话框的 "**工具**" 选项卡上的 "**初始目录**" 菜单相关联的资源 ID。

```
UINT GetInitialDirMenuID() const;
```

### <a name="return-value"></a>返回值

菜单资源标识符。

### <a name="remarks"></a>备注

返回的 ID 在 [CWinAppEx：： EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools)的 *uInitDirMenuID* 参数中指定。

## <a name="cusertoolsmanagergetmaxtools"></a><a name="getmaxtools"></a> CUserToolsManager::GetMaxTools

返回可在应用程序中分配的用户工具的最大数目。

```
int GetMaxTools() const;
```

### <a name="return-value"></a>返回值

可分配的用户工具的最大数目。

### <a name="remarks"></a>备注

调用此方法以检索可在应用程序中分配的最大工具数。 此数字是通过传递给 [CWinAppEx：： EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools)的 *UiCmdLast* 参数从 *uiCmdFirst* 范围中的 id 数。

## <a name="cusertoolsmanagergettoolsentrycmd"></a><a name="gettoolsentrycmd"></a> CUserToolsManager::GetToolsEntryCmd

返回用户工具菜单项占位符的命令 ID。

```
UINT GetToolsEntryCmd() const;
```

### <a name="return-value"></a>返回值

占位符的命令 ID。

### <a name="remarks"></a>备注

若要启用用户工具，请调用 [CWinAppEx：： EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools)。 *UiCmdToolsDummy* 参数指定 tools 条目命令的命令 ID。 此方法返回工具条目命令 ID。 在菜单中使用该 ID 的任何位置时，菜单显示时，会将其替换为用户工具列表。

## <a name="cusertoolsmanagergetusertools"></a><a name="getusertools"></a> CUserToolsManager::GetUserTools

返回对用户工具列表的引用。

```
const CObList& GetUserTools() const;
```

### <a name="return-value"></a>返回值

对包含用户工具列表的 [CObList 类](../../mfc/reference/coblist-class.md) 对象的常量引用。

### <a name="remarks"></a>备注

调用此方法可检索 [CUserToolsManager](../../mfc/reference/cusertoolsmanager-class.md) 对象维护的用户工具的列表。 每个用户工具由 [CUserTool 类](../../mfc/reference/cusertool-class.md) 类型的对象或从派生的类型表示 `CUserTool` 。 当你调用 [CWinAppEx：： EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools)来启用用户工具时，该类型由 *pToolRTC* 参数指定。

## <a name="cusertoolsmanagerinvoketool"></a><a name="invoketool"></a> CUserToolsManager::InvokeTool

执行与具有指定命令 ID 的用户工具相关联的应用程序。

```
BOOL InvokeTool(UINT uiCmdId);
```

### <a name="parameters"></a>parameters

*uiCmdId*<br/>
中与用户工具关联的菜单命令 ID。

### <a name="return-value"></a>返回值

如果成功执行与用户工具相关联的命令，则为非零值;否则为0。

### <a name="remarks"></a>备注

调用此方法以执行与用户工具相关联的应用程序，该应用程序具有由 *uiCmdId* 指定的命令 ID。

## <a name="cusertoolsmanagerisusertoolcmd"></a><a name="isusertoolcmd"></a> CUserToolsManager::IsUserToolCmd

确定命令 ID 是否与用户工具相关联。

```
BOOL IsUserToolCmd(UINT uiCmdId) const;
```

### <a name="parameters"></a>parameters

*uiCmdId*<br/>
中菜单项的命令 ID。

### <a name="return-value"></a>返回值

如果给定的命令 ID 与用户工具相关联，则为非零值;否则为0。

### <a name="remarks"></a>备注

此方法检查给定的命令 ID 是否在命令 ID 范围内。 在调用 [CWinAppEx：： EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools) 启用用户工具时，可以指定范围。

## <a name="cusertoolsmanagerloadstate"></a><a name="loadstate"></a> CUserToolsManager：： LoadState

从 Windows 注册表加载有关用户工具的信息。

```
BOOL LoadState(LPCTSTR lpszProfileName=NULL);
```

### <a name="parameters"></a>parameters

*lpszProfileName*<br/>
中Windows 注册表项的路径。

### <a name="return-value"></a>返回值

如果状态成功加载，则为非零值;否则为0。

### <a name="remarks"></a>备注

此方法 `CUserToolsManager` 从 Windows 注册表加载对象的状态。

通常不会直接调用此方法。 [CWinAppEx：： LoadState](../../mfc/reference/cwinappex-class.md#loadstate) 将它作为工作区初始化过程的一部分进行调用。

## <a name="cusertoolsmanagermovetooldown"></a><a name="movetooldown"></a> CUserToolsManager::MoveToolDown

在用户工具列表中向下移动指定的用户工具。

```
BOOL MoveToolDown(CUserTool* pTool);
```

### <a name="parameters"></a>parameters

*pTool*<br/>
中指定要移动的用户工具。

### <a name="return-value"></a>返回值

如果成功地向下移动了用户工具，则为非零;否则为0。

### <a name="remarks"></a>备注

如果 *pTool* 指定的工具不在内部列表中，或者该工具是列表中的最后一个，则该方法将失败。

## <a name="cusertoolsmanagermovetoolup"></a><a name="movetoolup"></a> CUserToolsManager::MoveToolUp

在用户工具列表中上移指定的用户工具。

```
BOOL MoveToolUp(CUserTool* pTool);
```

### <a name="parameters"></a>parameters

*pTool*<br/>
中指定要移动的用户工具。

### <a name="return-value"></a>返回值

如果成功移动用户工具，则为非零;否则为0。

### <a name="remarks"></a>备注

如果 *pTool* 参数指定的工具不在内部列表中，或者该工具是列表中的第一个工具项，则该方法将失败。

## <a name="cusertoolsmanagerremovetool"></a><a name="removetool"></a> CUserToolsManager::RemoveTool

从应用程序中删除指定的用户工具。

```
BOOL RemoveTool(CUserTool* pTool);
```

### <a name="parameters"></a>parameters

*pTool*<br/>
[in，out]指向要删除的用户工具的指针。

### <a name="return-value"></a>返回值

如果成功删除该工具，则为 TRUE。 否则为 FALSE。

### <a name="remarks"></a>备注

如果成功删除该工具，则此方法将删除 *pTool*。

## <a name="cusertoolsmanagersavestate"></a><a name="savestate"></a> CUserToolsManager：： SaveState

在 Windows 注册表中存储有关用户工具的信息。

```
BOOL SaveState(LPCTSTR lpszProfileName=NULL);
```

### <a name="parameters"></a>parameters

*lpszProfileName*<br/>
中Windows 注册表项的路径。

### <a name="return-value"></a>返回值

如果成功保存状态，则为非零值;否则为0。

### <a name="remarks"></a>备注

方法 `CUserToolsManager` 在 Windows 注册表中存储对象的当前状态。

通常情况下，不需要直接调用此方法， [CWinAppEx：： SaveState](../../mfc/reference/cwinappex-class.md#savestate) 会在应用程序的工作区序列化过程中自动调用此方法。

## <a name="cusertoolsmanagersetdefext"></a><a name="setdefext"></a> CUserToolsManager::SetDefExt

指定 **文件打开** 对话框 ( [CFileDialog) 类](../../mfc/reference/cfiledialog-class.md)在 "**自定义**" 对话框的 "**工具**" 选项卡上的 "**命令**" 字段中使用的默认扩展名。

```cpp
void SetDefExt(const CString& strDefExt);
```

### <a name="parameters"></a>parameters

*strDefExt*<br/>
中包含默认文件扩展名的文本字符串。

### <a name="remarks"></a>备注

调用此方法以在 " **文件打开** " 对话框中指定默认文件扩展名，用户选择要与用户工具相关联的应用程序时，会显示该对话框。 默认值为 "exe"。

## <a name="cusertoolsmanagersetfilter"></a><a name="setfilter"></a> CUserToolsManager::SetFilter

指定文件 **打开** 对话框 ( [CFileDialog 类](../../mfc/reference/cfiledialog-class.md)) 在 "**自定义**" 对话框的 "**工具**" 选项卡上的 "**命令**" 字段中使用的文件筛选器。

```cpp
void SetFilter(const CString& strFilter);
```

### <a name="parameters"></a>parameters

*strFilter*<br/>
中指定筛选器。

## <a name="see-also"></a>请参阅

[层次结构图](../../mfc/hierarchy-chart.md)<br/>
[Classes](../../mfc/reference/mfc-classes.md)<br/>
[CWinAppEx 类](../../mfc/reference/cwinappex-class.md)<br/>
[CUserTool 类](../../mfc/reference/cusertool-class.md)
