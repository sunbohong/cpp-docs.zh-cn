---
description: 了解详细信息： CJumpList 类
title: CJumpList 类
ms.date: 03/27/2019
f1_keywords:
- CJumpList
- AFXADV/CJumpList
- AFXADV/CJumpList::CJumpList
- AFXADV/CJumpList::AbortList
- AFXADV/CJumpList::AddDestination
- AFXADV/CJumpList::AddKnownCategory
- AFXADV/CJumpList::AddTask
- AFXADV/CJumpList::AddTasks
- AFXADV/CJumpList::AddTaskSeparator
- AFXADV/CJumpList::ClearAll
- AFXADV/CJumpList::ClearAllDestinations
- AFXADV/CJumpList::CommitList
- AFXADV/CJumpList::GetDestinationList
- AFXADV/CJumpList::GetMaxSlots
- AFXADV/CJumpList::GetRemovedItems
- AFXADV/CJumpList::InitializeList
- AFXADV/CJumpList::SetAppID
helpviewer_keywords:
- CJumpList [MFC], CJumpList
- CJumpList [MFC], AbortList
- CJumpList [MFC], AddDestination
- CJumpList [MFC], AddKnownCategory
- CJumpList [MFC], AddTask
- CJumpList [MFC], AddTasks
- CJumpList [MFC], AddTaskSeparator
- CJumpList [MFC], ClearAll
- CJumpList [MFC], ClearAllDestinations
- CJumpList [MFC], CommitList
- CJumpList [MFC], GetDestinationList
- CJumpList [MFC], GetMaxSlots
- CJumpList [MFC], GetRemovedItems
- CJumpList [MFC], InitializeList
- CJumpList [MFC], SetAppID
ms.assetid: d364d27e-f512-4b12-9872-c2a17c78ab1f
ms.openlocfilehash: 07e896c5b3a205a44850d45dcc4876103a48f2fa
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97236901"
---
# <a name="cjumplist-class"></a>CJumpList 类

`CJumpList`是右键单击任务栏中的图标时显示的快捷方式列表。

## <a name="syntax"></a>语法

```
class CJumpList;
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CJumpList::CJumpList](#cjumplist)|构造 `CJumpList` 对象。|
|[CJumpList：： ~ CJumpList](#_dtorcjumplist)|销毁 `CJumpList` 对象。|

|名称|描述|
|----------|-----------------|
|[CJumpList::AbortList](#abortlist)|中止列表生成事务，而不进行提交。|
|[CJumpList::AddDestination](#adddestination)|已重载。 将目标添加到列表。|
|[CJumpList::AddKnownCategory](#addknowncategory)|向列表追加一个已知类别。|
|[CJumpList：： AddTask](#addtask)|已重载。 向规范任务类别中添加项。|
|[CJumpList::AddTasks](#addtasks)|向规范任务类别中添加项。|
|[CJumpList::AddTaskSeparator](#addtaskseparator)|在任务之间添加分隔符。|
|[CJumpList：： ClearAll](#clearall)|删除目前已添加到的当前实例中的所有任务和目标 `CJumpList` 。|
|[CJumpList::ClearAllDestinations](#clearalldestinations)|删除目前已添加到的当前实例中的所有目标 `CJumpList` 。|
|[CJumpList::CommitList](#commitlist)|在这种情况下，结束列表生成事务并将报告的列表提交给关联的存储 (注册表。 ) |
|[CJumpList::GetDestinationList](#getdestinationlist)|检索指向目标列表的接口指针。|
|[CJumpList::GetMaxSlots](#getmaxslots)|检索可在调用应用程序的目标菜单中显示的最大项数。|
|[CJumpList::GetRemovedItems](#getremoveditems)|返回表示删除目标的项的数组。|
|[CJumpList::InitializeList](#initializelist)|开始生成列表事务。|
|[CJumpList::SetAppID](#setappid)|设置要生成的列表的应用程序用户模型 ID。|

## <a name="inheritance-hierarchy"></a>继承层次结构

[CJumpList](../../mfc/reference/cjumplist-class.md)

## <a name="requirements"></a>要求

**标头：** afxadv

## <a name="cjumplistcjumplist"></a><a name="_dtorcjumplist"></a> CJumpList：： ~ CJumpList

销毁 `CJumpList` 对象。

```
~CJumpList();
```

## <a name="cjumplistabortlist"></a><a name="abortlist"></a> CJumpList::AbortList

中止列表生成事务，而不进行提交。

```cpp
void AbortList();
```

### <a name="remarks"></a>备注

调用此方法与在未调用的情况下销毁的效果相同 `CJumpList` `CommitList` 。

## <a name="cjumplistadddestination"></a><a name="adddestination"></a> CJumpList::AddDestination

将目标添加到列表。

```
BOOL AddDestination(
    LPCTSTR lpcszCategoryName,
    LPCTSTR strDestinationPath);

BOOL AddDestination(
    LPCTSTR strCategoryName,
    IShellItem* pShellItem);

BOOL AddDestination(
    LPCTSTR strCategoryName,
    IShellLink* pShellLink);
```

### <a name="parameters"></a>parameters

*lpcszCategoryName*<br/>
指定类别名称。 如果指定的类别不存在，将创建它。

*strDestinationPath*<br/>
指定目标文件的路径。

*strCategoryName*<br/>
指定类别名称。 如果指定的类别不存在，将创建它。

*pShellItem*<br/>
指定表示要添加的目标的 Shell 项。

*pShellLink*<br/>
指定表示要添加的目标的 Shell 链接。

### <a name="return-value"></a>返回值

### <a name="remarks"></a>备注

实例在 `CJumpList` 内部累计添加的目标，然后在中提交它们 `CommitList` 。

## <a name="cjumplistaddknowncategory"></a><a name="addknowncategory"></a> CJumpList::AddKnownCategory

向列表追加一个已知类别。

```
BOOL AddKnownCategory(KNOWNDESTCATEGORY category);
```

### <a name="parameters"></a>parameters

*category*<br/>
指定一个已知的类别类型。 可以是 KDC_RECENT 或 KDC_KNOWN。

### <a name="return-value"></a>返回值

### <a name="remarks"></a>备注

已知类别是经常和最近的类别，我们将为利用 (的每个应用程序自动计算这些类别， `SHAddToRecentDocs` 或间接使用该类别，因为 shell 将在某些情况下代表应用程序调用它) 。

## <a name="cjumplistaddtask"></a><a name="addtask"></a> CJumpList：： AddTask

向规范任务类别中添加项。

```
BOOL AddTask(
    LPCTSTR strTargetExecutablePath,
    LPCTSTR strCommandLineArgs,
    LPCTSTR strTitle,
    LPCTSTR strIconLocation,
    int iIconIndex);

BOOL AddTask(IShellLink* pShellLink);
```

### <a name="parameters"></a>parameters

*strTargetExecutablePath*<br/>
指定目标任务路径。

*strCommandLineArgs*<br/>
指定由 *strTargetExecutablePath* 指定的可执行文件的命令行参数。

*strTitle*<br/>
将显示在目标列表中的任务名称。

*strIconLocation*<br/>
将显示在目标列表中的图标的位置以及标题。

*iIconIndex*<br/>
图标索引。

*pShellLink*<br/>
Shell 链接，表示要添加的任务。

### <a name="return-value"></a>返回值

### <a name="remarks"></a>备注

的实例 `CJumpList` 累积指定的任务，并在期间将它们添加到目标列表中 `CommitList` 。 任务项将出现在应用程序 "目标" 菜单底部的 "类别" 中。 此类别在用户填充 UI 时优先于所有其他类别。

## <a name="cjumplistaddtasks"></a><a name="addtasks"></a> CJumpList::AddTasks

向规范任务类别中添加项。

```
BOOL AddTasks(IObjectArray* pObjectCollection);
```

### <a name="parameters"></a>parameters

*pObjectCollection*<br/>
要添加的任务的集合。

### <a name="return-value"></a>返回值

### <a name="remarks"></a>备注

CJumpList 实例累积指定的任务，并在期间将它们添加到目标列表 `CommitList` 。 任务项将出现在应用程序 "目标" 菜单底部的 "类别" 中。 此类别在用户填充 UI 时优先于所有其他类别。

## <a name="cjumplistaddtaskseparator"></a><a name="addtaskseparator"></a> CJumpList::AddTaskSeparator

在任务之间添加分隔符。

```
BOOL AddTaskSeparator();
```

### <a name="return-value"></a>返回值

如果成功，则为非零; 否则为0。

## <a name="cjumplistcjumplist"></a><a name="cjumplist"></a> CJumpList::CJumpList

构造 `CJumpList` 对象。

```
CJumpList(BOOL bAutoCommit = TRUE);
```

### <a name="parameters"></a>parameters

*bAutoCommit*<br/>
如果此参数为 FALSE，则不会在析构函数中自动提交列表。

## <a name="cjumplistclearall"></a><a name="clearall"></a> CJumpList：： ClearAll

删除目前已添加到的当前实例中的所有任务和目标 `CJumpList` 。

```cpp
void ClearAll();
```

### <a name="remarks"></a>备注

此方法清除并释放所有数据和内部接口。

## <a name="cjumplistclearalldestinations"></a><a name="clearalldestinations"></a> CJumpList::ClearAllDestinations

删除目前已添加到 CJumpList 的当前实例中的所有目标。

```cpp
void ClearAllDestinations();
```

### <a name="remarks"></a>备注

如果需要删除目前目标列表生成的当前会话中已添加的所有目标，并再次添加其他目标，请调用此函数。 如果内部 `ICustomDestinationList` 已初始化，则会保持活动状态。

## <a name="cjumplistcommitlist"></a><a name="commitlist"></a> CJumpList::CommitList

结束一个列表生成事务，并将报告的列表提交给关联的存储 (注册表的这种情况下) 。

```
BOOL CommitList();
```

### <a name="return-value"></a>返回值

### <a name="remarks"></a>备注

Commit 是原子的。 如果提交失败，将返回错误。  `CommitList`调用时，将清除已删除项的当前列表。 调用此方法将重置对象，使其没有活动的列表生成事务。 若要更新列表， `BeginList` 需再次调用。

## <a name="cjumplistgetdestinationlist"></a><a name="getdestinationlist"></a> CJumpList::GetDestinationList

检索指向目标列表的接口指针。

```
ICustomDestinationList* GetDestinationList();
```

### <a name="return-value"></a>返回值

### <a name="remarks"></a>备注

如果跳转列表尚未初始化，或已提交或中止，则返回的值将为 NULL。

## <a name="cjumplistgetmaxslots"></a><a name="getmaxslots"></a> CJumpList::GetMaxSlots

检索可在调用应用程序的目标菜单中显示的最大项数。

```
UINT GetMaxSlots() const;
```

### <a name="return-value"></a>返回值

### <a name="remarks"></a>备注

应用程序只会报告多个项目和类别标题与此值的组合。 如果对 `AppendCategory` 、或的调用 `AppendKnownCategory` `AddUserTasks` 超过此数字，则它们将返回失败。

## <a name="cjumplistgetremoveditems"></a><a name="getremoveditems"></a> CJumpList::GetRemovedItems

返回表示删除目标的项的数组。

```
IObjectArray* GetRemovedItems();
```

### <a name="return-value"></a>返回值

### <a name="remarks"></a>备注

删除的目标将在跳转列表初始化期间检索。 生成新的目标列表时，应用程序应首先处理删除的目标列表，并清除删除的列表枚举器返回的任何项的跟踪数据。 如果应用程序尝试提供刚在当前调用开始的事务中删除的项 `BeginList` ，则重新添加该项的方法调用将失败，以确保应用程序遵循删除的列表。

## <a name="cjumplistinitializelist"></a><a name="initializelist"></a> CJumpList::InitializeList

开始生成列表事务。

```
BOOL InitializeList();
```

### <a name="return-value"></a>返回值

### <a name="remarks"></a>备注

无需显式调用此方法，除非你想要使用、使用的 `ICustomDestinationList` `GetDestinationList` 可用槽的数目 `GetMaxSlots` 或使用移除的项的列表 `GetRemovedItems` 。

## <a name="cjumplistsetappid"></a><a name="setappid"></a> CJumpList::SetAppID

设置要生成的列表的应用程序用户模型 ID。

```cpp
void SetAppID(LPCTSTR strAppID);
```

### <a name="parameters"></a>parameters

*strAppID*<br/>
一个字符串，指定应用程序用户模型 ID。

## <a name="see-also"></a>请参阅

[类](../../mfc/reference/mfc-classes.md)
