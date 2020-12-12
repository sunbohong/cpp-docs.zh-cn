---
description: 了解详细信息： CRecentFileList 类
title: CRecentFileList 类
ms.date: 11/04/2016
f1_keywords:
- CRecentFileList
- AFXADV/CRecentFileList
- AFXADV/CRecentFileList::CRecentFileList
- AFXADV/CRecentFileList::Add
- AFXADV/CRecentFileList::GetDisplayName
- AFXADV/CRecentFileList::GetSize
- AFXADV/CRecentFileList::ReadList
- AFXADV/CRecentFileList::Remove
- AFXADV/CRecentFileList::UpdateMenu
- AFXADV/CRecentFileList::WriteList
helpviewer_keywords:
- CRecentFileList [MFC], CRecentFileList
- CRecentFileList [MFC], Add
- CRecentFileList [MFC], GetDisplayName
- CRecentFileList [MFC], GetSize
- CRecentFileList [MFC], ReadList
- CRecentFileList [MFC], Remove
- CRecentFileList [MFC], UpdateMenu
- CRecentFileList [MFC], WriteList
ms.assetid: a77f0524-7584-4582-849a-7e97b76d186e
ms.openlocfilehash: 9433e65336cba1018c7bff8cf3a90e239ae5e3eb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97301121"
---
# <a name="crecentfilelist-class"></a>CRecentFileList 类

支持最近使用的 (MRU) 文件列表的控件。

## <a name="syntax"></a>语法

```
class CRecentFileList
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CRecentFileList::CRecentFileList](#crecentfilelist)|构造 `CRecentFileList` 对象。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CRecentFileList：： Add](#add)|将文件添加到 MRU 文件列表。|
|[CRecentFileList：： GetDisplayName](#getdisplayname)|为 MRU 文件名的菜单显示提供显示名称。|
|[CRecentFileList：： GetSize](#getsize)|检索 MRU 文件列表中的文件数。|
|[CRecentFileList：： ReadList](#readlist)|从注册表或读取 MRU 文件列表。INI 文件。|
|[CRecentFileList：： Remove](#remove)|从 MRU 文件列表中删除文件。|
|[CRecentFileList::UpdateMenu](#updatemenu)|更新 MRU 文件列表的菜单显示。|
|[CRecentFileList::WriteList](#writelist)|从注册表或写入 MRU 文件列表。INI 文件。|

### <a name="public-operators"></a>公共运算符

|名称|描述|
|----------|-----------------|
|[CRecentFileList：： operator \[\]](#operator_at)|返回 `CString` 位于给定位置的对象。|

## <a name="remarks"></a>备注

可以在 MRU 文件列表中添加或删除文件，可以从注册表或将文件列表读取或写入文件。INI 文件，可更新显示 MRU 文件列表的菜单。

## <a name="inheritance-hierarchy"></a>继承层次结构

`CRecentFileList`

## <a name="requirements"></a>要求

**标头：** afxadv

## <a name="crecentfilelistadd"></a><a name="add"></a> CRecentFileList：： Add

将文件添加到最近使用的 (MRU) 文件列表中。

```
virtual void Add(LPCTSTR lpszPathName);

virtual void Add(
    LPCTSTR lpszPathName,
    LPCTSTR lpszAppID);

void Add(
    IShellItem* pItem,
    LPCTSTR lpszAppID);

void Add(
    IShellLink* pLink,
    LPCTSTR lpszAppID);

void Add(
    PIDLIST_ABSOLUTE pidl,
    LPCTSTR lpszAppID);
```

### <a name="parameters"></a>parameters

*lpszPathName*<br/>
指定要添加到列表中的路径名。

*lpszAppID*<br/>
指定应用程序的应用程序用户模型 ID。

*pItem*<br/>
指定要添加到列表中的 Shell 项的指针。

*pLink*<br/>
指定指向要添加到列表中的 Shell 链接的指针。

*pidl*<br/>
指定应添加到 "最近使用的文档" 文件夹中的 shell 项的 IDLIST.TXT。

### <a name="remarks"></a>备注

文件名将添加到 MRU 列表的顶部。 如果该文件名已经存在于 MRU 列表中，则会将其移动到顶部。

## <a name="crecentfilelistcrecentfilelist"></a><a name="crecentfilelist"></a> CRecentFileList::CRecentFileList

构造 `CRecentFileList` 对象。

```
CRecentFileList(
    UINT nStart,
    LPCTSTR lpszSection,
    LPCTSTR lpszEntryFormat,
    int nSize,
    int nMaxDispLen = AFX_ABBREV_FILENAME_LEN);
```

### <a name="parameters"></a>parameters

*nStart*<br/>
用于显示 MRU (最近使用) 文件列表的菜单中的编号偏移量。

*lpszSection*<br/>
指向注册表的部分名称或应用程序的。读取和/或写入 MRU 文件列表的 INI 文件。

*lpszEntryFormat*<br/>
指向要用于注册表中或应用程序的项名称的格式字符串。INI 文件。

*nSize*<br/>
MRU 文件列表中的最大文件数。

*nMaxDispLen*<br/>
MRU 文件列表中文件名的菜单显示的最大长度（以字符数表示）。

### <a name="remarks"></a>备注

*LpszEntryFormat* 所指向的格式字符串应包含 "% d"，它将用于替换每个 MRU 项的索引。 例如，如果格式字符串为，则 `"file%d"` 项将命名为、等 `file0` `file1` 。

## <a name="crecentfilelistgetdisplayname"></a><a name="getdisplayname"></a> CRecentFileList：： GetDisplayName

获取 MRU 文件列表中的文件的显示名称，以便在显示的 MRU 列表的菜单中使用。

```
virtual BOOL GetDisplayName(
    CString& strName,
    int nIndex,
    LPCTSTR lpszCurDir,
    int nCurDir,
    BOOL bAtLeastName = TRUE) const;
```

### <a name="parameters"></a>parameters

*strName*<br/>
文件的完整路径，其名称将显示在 MRU 文件的菜单列表中。

*nIndex*<br/>
MRU 文件列表中该文件的从零开始的索引。

*lpszCurDir*<br/>
包含当前目录的字符串。

*nCurDir*<br/>
当前目录字符串的长度。

*bAtLeastName*<br/>
如果为非零值，则指示应返回文件的基名称，即使它超过最大显示长度 (作为 *nMaxDispLen* 参数传递到 `CRecentFileList` 构造函数) 。

### <a name="return-value"></a>返回值

如果最近使用的 (MRU) 文件列表中的指定索引处没有文件名，则 **为 FALSE** 。

### <a name="remarks"></a>备注

如果文件在当前目录中，则该函数将离开该目录。 如果文件名太长，则会去除目录和扩展名。 如果文件名仍过长，则显示名称将设置为空字符串，除非 *bAtLeastName* 为非零值。

## <a name="crecentfilelistgetsize"></a><a name="getsize"></a> CRecentFileList：： GetSize

检索 MRU 文件列表中的文件数。

```
int GetSize() const;
```

### <a name="return-value"></a>返回值

当前最常使用的文件数 (MRU) 文件列表。

## <a name="crecentfilelistoperator--"></a><a name="operator_at"></a> CRecentFileList：： operator []

重载的下标 (`[]`) 运算符返回 `CString` *nIndex* 中从零开始的索引指定的单个。

```
CString& operator[ ](int nindex);
```

### <a name="parameters"></a>parameters

*nIndex*<br/>
的中的从零开始的索引 `CString` `CString` 。

## <a name="crecentfilelistreadlist"></a><a name="readlist"></a> CRecentFileList：： ReadList

读取注册表中最近使用的 (MRU) 文件列表或应用程序的。INI 文件。

```
virtual void ReadList();
```

## <a name="crecentfilelistremove"></a><a name="remove"></a> CRecentFileList：： Remove

从 MRU 文件列表中删除文件。

```
virtual void Remove(int nIndex);
```

### <a name="parameters"></a>parameters

*nIndex*<br/>
要从最近使用 (MRU) 文件列表中删除的文件的从零开始的索引。

## <a name="crecentfilelistupdatemenu"></a><a name="updatemenu"></a> CRecentFileList::UpdateMenu

更新 MRU 文件列表的菜单显示。

```
virtual void UpdateMenu(CCmdUI* pCmdUI);
```

### <a name="parameters"></a>parameters

*pCmdUI*<br/>
一个指针，指向最近使用 (MRU) file list 菜单的 [CCmdUI](../../mfc/reference/ccmdui-class.md) 对象。

## <a name="crecentfilelistwritelist"></a><a name="writelist"></a> CRecentFileList::WriteList

将最近使用的 (MRU) 文件列表写入注册表或应用程序的。INI 文件。

```
virtual void WriteList();
```

## <a name="see-also"></a>请参阅

[层次结构图](../../mfc/hierarchy-chart.md)
