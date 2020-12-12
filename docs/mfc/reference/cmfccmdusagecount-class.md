---
description: 了解详细信息： CMFCCmdUsageCount 类
title: CMFCCmdUsageCount 类
ms.date: 11/04/2016
f1_keywords:
- CMFCCmdUsageCount
- AFXCMDUSAGECOUNT/CMFCCmdUsageCount
- AFXCMDUSAGECOUNT/CMFCCmdUsageCount::AddCmd
- AFXCMDUSAGECOUNT/CMFCCmdUsageCount::GetCount
- AFXCMDUSAGECOUNT/CMFCCmdUsageCount::HasEnoughInformation
- AFXCMDUSAGECOUNT/CMFCCmdUsageCount::IsFreqeuntlyUsedCmd
- AFXCMDUSAGECOUNT/CMFCCmdUsageCount::Reset
- AFXCMDUSAGECOUNT/CMFCCmdUsageCount::Serialize
- AFXCMDUSAGECOUNT/CMFCCmdUsageCount::SetOptions
helpviewer_keywords:
- CMFCCmdUsageCount [MFC], AddCmd
- CMFCCmdUsageCount [MFC], GetCount
- CMFCCmdUsageCount [MFC], HasEnoughInformation
- CMFCCmdUsageCount [MFC], IsFreqeuntlyUsedCmd
- CMFCCmdUsageCount [MFC], Reset
- CMFCCmdUsageCount [MFC], Serialize
- CMFCCmdUsageCount [MFC], SetOptions
ms.assetid: 9c33b783-37c0-43ea-9f31-3c75e246c841
ms.openlocfilehash: 40d09e96672cafb022baab98787fe10b1258048b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97327725"
---
# <a name="cmfccmdusagecount-class"></a>CMFCCmdUsageCount 类

跟踪 Windows 消息的使用计数，例如当用户从菜单中选择项时。

## <a name="syntax"></a>语法

```
class CMFCCmdUsageCount : public CObject
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|-|-|
|`CMFCCmdUsageCount::CMFCCmdUsageCount`|默认构造函数。|
|`CMFCCmdUsageCount::~CMFCCmdUsageCount`|析构函数。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|-|-|
|[CMFCCmdUsageCount::AddCmd](#addcmd)|增加一个与给定命令关联的计数器。|
|[CMFCCmdUsageCount：： GetCount](#getcount)|检索与给定的命令 ID 相关联的使用计数。|
|[CMFCCmdUsageCount::HasEnoughInformation](#hasenoughinformation)|确定此对象是否已收集最小数量的跟踪数据。|
|[CMFCCmdUsageCount::IsFreqeuntlyUsedCmd](#isfreqeuntlyusedcmd)|确定是否经常使用给定命令。|
|[CMFCCmdUsageCount：： Reset](#reset)|清除所有命令的使用计数。|
|[CMFCCmdUsageCount：：串行化](#serialize)|从存档中读取此对象或将其写入存档。 （重写 [CObject::Serialize](../../mfc/reference/cobject-class.md#serialize)。）|
|[CMFCCmdUsageCount：： SetOptions](#setoptions)|设置共享 `CMFCCmdUsageCount` 类数据成员的值。|

### <a name="data-members"></a>数据成员

|名称|描述|
|-|-|
|`m_CmdUsage`|将 `CMap` 命令映射到其使用计数的对象。|
|`m_nMinUsagePercentage`|要频繁使用的命令的最小用量百分比。|
|`m_nStartCount`|用于确定此对象是否已收集最小跟踪数据量的开始计数器。|
|`m_nTotalUsage`|所有跟踪的命令的计数。|

### <a name="remarks"></a>备注

`CMFCCmdUsageCount`类将每个数字 Windows 消息标识符映射到32位无符号整数计数器。 `CMFCToolBar` 使用此类显示经常使用的工具栏项。 有关的详细信息 `CMFCToolBar` ，请参阅 [CMFCToolBar 类](../../mfc/reference/cmfctoolbar-class.md)。

可以在 `CMFCCmdUsageCount` 程序运行之间保留类数据。 使用 [CMFCCmdUsageCount：：串行化](#serialize) 方法可序列化类成员数据，使用 [CMFCCmdUsageCount：： SetOptions](#setoptions) 方法可设置共享的成员数据。

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

[CMFCCmdUsageCount](../../mfc/reference/cmfccmdusagecount-class.md)

## <a name="requirements"></a>要求

**标头：** afxcmdusagecount

## <a name="cmfccmdusagecountaddcmd"></a><a name="addcmd"></a> CMFCCmdUsageCount::AddCmd

增加一个与给定命令关联的计数器。

```cpp
void AddCmd(UINT uiCmd);
```

### <a name="parameters"></a>parameters

*uiCmd*\
中指定要递增的命令计数器。

### <a name="remarks"></a>备注

如果该条目不存在，则此方法会将新条目添加到命令计数的映射结构中 `m_CmdUsage` 。

此方法在以下情况下不执行任何操作：

- 工具栏框架处于自定义模式 ([CMFCToolBar：： IsCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode) 方法) 返回非零值。

- 命令引用子菜单或菜单分隔符 ( *uiCmd* 等于0或-1) 。

- *uiCmd* 引用标准命令 (global `IsStandardCommand` 函数) 返回非零值。

## <a name="cmfccmdusagecountgetcount"></a><a name="getcount"></a> CMFCCmdUsageCount：： GetCount

检索与给定的命令 ID 相关联的使用计数。

```
UINT GetCount(UINT uiCmd) const;
```

### <a name="parameters"></a>parameters

*uiCmd*\
中要检索的命令计数器的 ID。

### <a name="return-value"></a>返回值

与给定的命令 ID 相关联的使用计数。

## <a name="cmfccmdusagecounthasenoughinformation"></a><a name="hasenoughinformation"></a> CMFCCmdUsageCount::HasEnoughInformation

确定此对象是否已接收到最小数量的跟踪数据。

```
BOOL HasEnoughInformation() const;
```

### <a name="return-value"></a>返回值

如果此对象已接收到最小数量的跟踪数据，则为非零值;否则为0。

### <a name="remarks"></a>备注

如果 `m_nTotalUsage` 所有跟踪命令的总数等于或大于初始计数，则此方法将返回一个非零值 `m_nStartCount` 。 默认情况下，框架设置初始计数0。 可以通过使用 [CMFCCmdUsageCount：： SetOptions](#setoptions) 方法来重写此值。

[CMFCMenuBar：： IsShowAllCommands](../../mfc/reference/cmfcmenubar-class.md#isshowallcommands)使用此方法来确定是否显示所有可用的菜单命令。

## <a name="cmfccmdusagecountisfreqeuntlyusedcmd"></a><a name="isfreqeuntlyusedcmd"></a> CMFCCmdUsageCount::IsFreqeuntlyUsedCmd

确定是否经常使用给定命令。

```
BOOL IsFreqeuntlyUsedCmd(UINT uiCmd) const;
```

### <a name="parameters"></a>parameters

*uiCmd*\
中指定要检查的命令。

### <a name="return-value"></a>返回值

如果经常使用命令，则为非零值;否则为0。

### <a name="remarks"></a>备注

如果命令使用总数为0，则此方法返回 0 `m_nTotalUsage` 。 否则，如果使用指定命令的百分比大于最小百分比，此方法将返回非零值 `m_nMinUsagePercentage` 。 默认情况下，框架将最小百分比设置为5。 可以通过使用 [CMFCCmdUsageCount：： SetOptions](#setoptions) 方法来重写此值。 如果最小百分比为0，则如果指定的命令计数大于0，则此方法将返回非零值。

[CMFCToolBar：： IsCommandRarelyUsed](../../mfc/reference/cmfctoolbar-class.md#iscommandrarelyused) 使用此方法来确定是否很少使用某个命令。

## <a name="cmfccmdusagecountreset"></a><a name="reset"></a> CMFCCmdUsageCount：： Reset

清除所有命令的使用计数。

```cpp
void Reset();
```

### <a name="remarks"></a>备注

调用此方法以清除命令计数的映射结构中的所有条目， `m_CmdUsage` 并将其重置为 `m_nTotalUsage` 0。

## <a name="cmfccmdusagecountserialize"></a><a name="serialize"></a> CMFCCmdUsageCount：：串行化

从存档中读取此对象，或将其写入存档。

```
virtual void Serialize(CArchive& ar);
```

### <a name="parameters"></a>parameters

*ar*\
中 `CArchive` 要从或序列化到的对象。

### <a name="remarks"></a>备注

此方法会序列化命令计数的映射结构，以及 `m_CmdUsage` `m_nTotalUsage` 从或到指定存档的总命令用法。

有关序列化示例，请参阅 [序列化：序列化对象](../../mfc/serialization-serializing-an-object.md)。

## <a name="cmfccmdusagecountsetoptions"></a><a name="setoptions"></a> CMFCCmdUsageCount：： SetOptions

设置共享 `CMFCCmdUsageCount` 类数据成员的值。

```
static BOOL __stdcall SetOptions(
    UINT nStartCount,
    UINT nMinUsagePercentage);
```

### <a name="parameters"></a>parameters

*nStartCount*\
中所有跟踪的命令的新初始计数。

*nMinUsagePercentage*\
中新的最小使用量百分比。

### <a name="return-value"></a>返回值

如果该方法成功，则为 TRUE; 如果 *nMinUsagePercentage* 参数大于或等于100，则为 FALSE。

### <a name="remarks"></a>备注

此方法会将共享 `CMFCCmdUsageCount` 类数据成员 `m_nStartCount` 和 `m_nMinUsagePercentage` 分别设置为 *nStartCount* 和 *nMinUsagePercentage*。 `m_nStartCount` 由 [CMFCCmdUsageCount：： HasEnoughInformation](#hasenoughinformation) 方法使用，以确定此对象是否收集了最少的跟踪数据量。 `m_nMinUsagePercentage`[CMFCCmdUsageCount：： IsFreqeuntlyUsedCmd](#isfreqeuntlyusedcmd)方法使用来确定是否经常使用给定命令。

在调试版本中，如果 *nMinUsagePercentage* 参数大于或等于100，则此方法将生成断言失败。

## <a name="see-also"></a>请参阅

[层次结构图](../../mfc/hierarchy-chart.md)<br/>
[Classes](../../mfc/reference/mfc-classes.md)<br/>
[CMFCToolBar 类](../../mfc/reference/cmfctoolbar-class.md)
