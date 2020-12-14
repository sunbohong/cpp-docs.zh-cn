---
description: 了解详细信息： CMenuTearOffManager 类
title: CMenuTearOffManager 类
ms.date: 10/18/2018
f1_keywords:
- CMenuTearOffManager
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::CMenuTearOffManager
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::Build
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::GetRegPath
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::Initialize
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::IsDynamicID
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::Parse
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::Reset
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::SetInUse
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::SetupTearOffMenus
helpviewer_keywords:
- CMenuTearOffManager [MFC], CMenuTearOffManager
- CMenuTearOffManager [MFC], Build
- CMenuTearOffManager [MFC], GetRegPath
- CMenuTearOffManager [MFC], Initialize
- CMenuTearOffManager [MFC], IsDynamicID
- CMenuTearOffManager [MFC], Parse
- CMenuTearOffManager [MFC], Reset
- CMenuTearOffManager [MFC], SetInUse
- CMenuTearOffManager [MFC], SetupTearOffMenus
ms.assetid: ab7ca272-ce42-4678-95f7-6ad75038f5a0
ms.openlocfilehash: b80f2e935f8d1dd47bf19a11522e4556b35490b4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336638"
---
# <a name="cmenutearoffmanager-class"></a>CMenuTearOffManager 类

管理可拖曳菜单。 可拖曳菜单是菜单栏上的菜单。 用户可以从菜单栏移开可拖曳菜单，从而使可拖拽菜单浮动。

   有关更多详细信息，请参阅位于 Visual Studio 安装的 **VC \\ atlmfc \\ src \\ mfc** 文件夹中的源代码。

## <a name="syntax"></a>语法

```
class CMenuTearOffManager : public CObject
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CMenuTearOffManager::CMenuTearOffManager](#cmenutearoffmanager)|构造 `CMenuTearOffManager` 对象。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CMenuTearOffManager：： Build](#build)||
|[CMenuTearOffManager::GetRegPath](#getregpath)||
|[CMenuTearOffManager：： Initialize](#initialize)|初始化 `CMenuTearOffManager` 对象。|
|[CMenuTearOffManager::IsDynamicID](#isdynamicid)||
|[CMenuTearOffManager：:P arse](#parse)||
|[CMenuTearOffManager：： Reset](#reset)||
|[CMenuTearOffManager::SetInUse](#setinuse)||
|[CMenuTearOffManager::SetupTearOffMenus](#setuptearoffmenus)||

## <a name="remarks"></a>备注

若要在应用程序中使用分离菜单，必须有一个 `CMenuTearOffManager` 对象。 在大多数情况下，你不会直接创建或初始化 `CMenuTearOffManager` 对象。 调用 [CWinAppEx：： EnableTearOffMenus](../../mfc/reference/cwinappex-class.md#enabletearoffmenus) 函数时，会对此进行处理。

## <a name="example"></a>示例

下面的示例演示如何通过调用方法来构造和初始化 `CMenuTearOffManager` 对象 `CWinAppEX::EnableTearOffMenus` 。 此代码片段属于 [Word Pad 示例](../../overview/visual-cpp-samples.md)。

[!code-cpp[NVC_MFC_WordPad#12](../../mfc/reference/codesnippet/cpp/cmenutearoffmanager-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

`CMenuTearOffManager`

## <a name="requirements"></a>要求

**标头：** afxmenutearoffmanager

## <a name="cmenutearoffmanagerbuild"></a><a name="build"></a> CMenuTearOffManager：： Build

```cpp
void Build(
    UINT uiTearOffBarID,
    CString& strText);
```

### <a name="parameters"></a>parameters

中 *uiTearOffBarID*<br/>

中 *strText*<br/>

### <a name="remarks"></a>备注

## <a name="cmenutearoffmanagercmenutearoffmanager"></a><a name="cmenutearoffmanager"></a> CMenuTearOffManager::CMenuTearOffManager

构造 [CMenuTearOffManager](../../mfc/reference/cmenutearoffmanager-class.md) 对象。

```
CMenuTearOffManager();
```

### <a name="remarks"></a>备注

在大多数情况下，不应手动创建 `CMenuTearOffManager` 。 `CMenuTearOffManager`调用[CWinAppEx：： EnableTearOffMenus](../../mfc/reference/cwinappex-class.md#enabletearoffmenus)时，应用程序的框架会创建对象。

## <a name="cmenutearoffmanagergetregpath"></a><a name="getregpath"></a> CMenuTearOffManager::GetRegPath

```
LPCTSTR GetRegPath() const;
```

### <a name="return-value"></a>返回值

### <a name="remarks"></a>备注

## <a name="cmenutearoffmanagerinitialize"></a><a name="initialize"></a> CMenuTearOffManager：： Initialize

初始化 [CMenuTearOffManager](../../mfc/reference/cmenutearoffmanager-class.md) 对象。

```
BOOL Initialize(
    LPCTSTR lpszRegEntry,
    UINT uiTearOffMenuFirst,
    UINT uiTearOffMenuLast);
```

### <a name="parameters"></a>parameters

*lpszRegEntry*<br/>
中一个字符串，其中包含注册表项的路径。 您的应用程序会在此注册表项中存储拆离栏的设置。

*uiTearOffMenuFirst*<br/>
中用于撕开菜单的第一个菜单 ID。

*uiTearOffMenuLast*<br/>
中用于撕开菜单的最后一个菜单 ID。

### <a name="return-value"></a>返回值

如果成功，则不为 0；否则为 0。

### <a name="remarks"></a>备注

从 *uiTearOffMenuFirst* 到 *UiTearOffMenuLast* 的菜单 id 的范围必须是连续的间隔。 间隔定义了应用程序中可同时出现的可拆卸菜单数。

## <a name="cmenutearoffmanagerisdynamicid"></a><a name="isdynamicid"></a> CMenuTearOffManager::IsDynamicID

```
BOOL IsDynamicID(UINT uiID) const;
```

### <a name="parameters"></a>parameters

中 *uiID*<br/>

### <a name="return-value"></a>返回值

### <a name="remarks"></a>备注

## <a name="cmenutearoffmanagerparse"></a><a name="parse"></a> CMenuTearOffManager：:P arse

```
UINT Parse(CString& str);
```

### <a name="parameters"></a>parameters

中 *str*<br/>

### <a name="return-value"></a>返回值

### <a name="remarks"></a>备注

## <a name="cmenutearoffmanagerreset"></a><a name="reset"></a> CMenuTearOffManager：： Reset

```cpp
void Reset(HMENU hmenu);
```

### <a name="parameters"></a>parameters

中 *hmenu*<br/>

### <a name="remarks"></a>备注

## <a name="cmenutearoffmanagersetinuse"></a><a name="setinuse"></a> CMenuTearOffManager::SetInUse

```cpp
void SetInUse(
    UINT uiCmdId,
    BOOL bUse = TRUE);
```

### <a name="parameters"></a>parameters

中 *uiCmdId*<br/>

中 *bUse*<br/>

### <a name="remarks"></a>备注

## <a name="cmenutearoffmanagersetuptearoffmenus"></a><a name="setuptearoffmenus"></a> CMenuTearOffManager::SetupTearOffMenus

```cpp
void SetupTearOffMenus(HMENU hMenu);
```

### <a name="parameters"></a>parameters

中 *hMenu*<br/>

### <a name="remarks"></a>备注

## <a name="see-also"></a>请参阅

[层次结构图](../../mfc/hierarchy-chart.md)<br/>
[Classes](../../mfc/reference/mfc-classes.md)<br/>
[CWinAppEx 类](../../mfc/reference/cwinappex-class.md)
