---
description: 了解详细信息： CDaoIndexInfo 结构
title: CDaoIndexInfo 结构
ms.date: 06/25/2018
f1_keywords:
- CDaoIndexInfo
helpviewer_keywords:
- DAO (Data Access Objects), Indexes collection
- CDaoIndexInfo structure [MFC]
ms.assetid: 251d8285-78ce-4716-a0b3-ccc3395fc437
ms.openlocfilehash: 2e09846789dc91e4d0df67665f3e975b557c07c8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97250759"
---
# <a name="cdaoindexinfo-structure"></a>CDaoIndexInfo 结构

该 `CDaoIndexInfo` 结构包含有关为 (DAO) 的数据访问对象定义的索引对象的信息。

## <a name="syntax"></a>语法

```cpp
struct CDaoIndexInfo {
    CDaoIndexInfo();                    // Constructor
    CString m_strName;                  // Primary
    CDaoIndexFieldInfo* m_pFieldInfos;  // Primary
    short m_nFields;                    // Primary
    BOOL m_bPrimary;                    // Secondary
    BOOL m_bUnique;                     // Secondary
    BOOL m_bClustered;                  // Secondary
    BOOL m_bIgnoreNulls;                // Secondary
    BOOL m_bRequired;                   // Secondary
    BOOL m_bForeign;                    // Secondary
    long m_lDistinctCount;              // All

    // Below the // Implementation comment:
    // Destructor, not otherwise documented
};
```

### <a name="parameters"></a>parameters

*m_strName*<br/>
对 field 对象进行唯一命名。 有关详细信息，请参阅 DAO 帮助中的主题 "名称属性"。

*m_pFieldInfos*<br/>
指向 [CDaoIndexFieldInfo](../../mfc/reference/cdaoindexfieldinfo-structure.md) 对象数组的指针，指示哪些 tabledef 或记录集字段是索引中的键字段。 每个对象都标识索引中的一个字段。 默认索引排序为 "升序"。 索引对象可以有一个或多个字段，这些字段表示每条记录的索引键。 这些可能是升序、降序或组合。

*m_nFields*<br/>
存储在中的字段数 `m_pFieldInfos` 。

*m_bPrimary*<br/>
如果主属性为 TRUE，则索引对象表示主索引。 主索引由一个或多个字段组成，这些字段可按预定义的顺序唯一地标识表中的所有记录。 因为索引字段必须是唯一的，所以在 DAO 中索引对象的唯一属性也设置为 TRUE。 如果主索引包含多个字段，则每个字段可以包含重复的值，但所有索引字段中的值的每个组合都必须是唯一的。 主索引由表的键组成，通常包含与主键相同的字段。

设置表的主键时，主键将自动定义为表的主索引。 有关详细信息，请参阅 DAO 帮助中的主题 "主要属性" 和 "唯一属性"。

> [!NOTE]
> 表中最多只能有一个主索引。

*m_bUnique*<br/>
指示索引对象是否表示表的唯一索引。 如果此属性为 TRUE，则索引对象表示唯一的索引。 唯一索引由一个或多个字段组成，这些字段按唯一的预定义顺序对表中的所有记录进行逻辑排列。 如果索引包含一个字段，则该字段中的值对于整个表必须是唯一的。 如果索引包含多个字段，则每个字段可能包含重复值，但所有索引字段中的值的每个组合都必须是唯一的。

如果索引对象的唯一属性和主属性均设置为 TRUE，则索引是唯一的，而是主要的：它以预定义的逻辑顺序唯一地标识表中的所有记录。 如果主属性设置为 "FALSE"，则索引为辅助索引。 辅助索引 (键和非键) 以逻辑方式按预定义顺序排列记录，而无需作为表中记录的标识符。

有关详细信息，请参阅 DAO 帮助中的主题 "主要属性" 和 "唯一属性"。

*m_bClustered*<br/>
指示索引对象是否表示表的聚集索引。 如果此属性为 TRUE，则索引对象表示聚集索引;否则，它不会。 聚集索引由一个或多个非键字段组成，这些字段将组合在一起，按预定义的顺序排列表中的所有记录。 使用聚集索引时，表中的数据按原义按聚集索引指定的顺序存储。 聚集索引提供对表中记录的有效访问。 有关详细信息，请参阅 DAO 帮助中的主题 "聚集属性"。

> [!NOTE]
> 对于使用 Microsoft Jet 数据库引擎的数据库，将忽略聚集属性，因为 Jet 数据库引擎不支持聚集索引。

*m_bIgnoreNulls*<br/>
指示在其索引字段中是否存在具有 Null 值的记录的索引条目。 如果此属性为 TRUE，则具有 Null 值的字段没有索引条目。 为了更快地使用字段搜索记录，可以为字段定义索引。 如果在索引字段中允许空项并且预计许多条目为 Null，则可以将索引对象的 IgnoreNulls 属性设置为 TRUE，以减少索引使用的存储空间量。 IgnoreNulls 属性设置和所需的属性设置共同确定具有 Null 索引值的记录是否具有索引项，如下表所示。

|IgnoreNulls|必需|索引字段中为 Null|
|-----------------|--------------|-------------------------|
|正确|错误|允许为 Null 值;未添加索引项。|
|False|False|允许为 Null 值;添加的索引条目。|
|是或否|正确|不允许为 Null 值;未添加索引项。|

有关详细信息，请参阅 DAO 帮助中的主题 "IgnoreNulls 属性"。

*m_bRequired*<br/>
指示 DAO 索引对象是否需要非 Null 值。 如果此属性为 TRUE，则索引对象不允许使用 Null 值。 有关详细信息，请参阅 DAO 帮助中的主题 "Required 属性"。

> [!TIP]
> 如果可以将 DAO 索引对象或字段对象的此属性设置为 tabledef、recordset 或 querydef 对象) 包含的 (，请为 field 对象设置此属性。 在索引对象之前检查字段对象的属性设置的有效性。

*m_bForeign*<br/>
指示索引对象是否表示表中的外键。 如果此属性为 TRUE，则索引表示表中的外键。 外键由外表中唯一标识行的一个或多个字段组成。 Microsoft Jet 数据库引擎在创建强制引用完整性的关系时，为外部表创建索引对象并设置外部属性。 有关详细信息，请参阅 DAO 帮助中的主题 "外部属性"。

*m_lDistinctCount*<br/>
指示关联表中包含的索引对象的唯一值数。 检查 DistinctCount 属性以确定索引中的唯一值或键的数目。 即使在索引允许重复值的情况下，也会对任何键进行一次计数。 此信息可用于尝试通过评估索引信息来优化数据访问的应用程序。 唯一值的数目也称为索引对象的基数。 DistinctCount 属性不会始终反映特定时间的实际键数。 例如，事务回滚导致的更改将不会立即反映在 DistinctCount 属性中。 有关详细信息，请参阅 DAO 帮助中的主题 "DistinctCount 属性"。

## <a name="remarks"></a>备注

对主要、次要和以上的引用指示 `GetIndexInfo` 类 [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md#getindexinfo) 和 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md#getindexinfo)中的成员函数返回信息的方式。

索引对象不由 MFC 类表示。 而是 [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md) 或 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) 类的基本 MFC 对象的 DAO 对象包含索引对象（称为索引集合）的集合。 这些类提供成员函数以访问索引信息的各个项，或者可以 `CDaoIndexInfo` 通过调用 `GetIndexInfo` 包含对象的成员函数，同时通过对象访问所有这些项。

`CDaoIndexInfo` 具有构造函数和析构函数，以便正确地分配和解除分配中的索引字段信息 `m_pFieldInfos` 。

Tabledef 对象的成员函数检索到的信息 `GetIndexInfo` 存储在 `CDaoIndexInfo` 结构中。 调用 `GetIndexInfo` 包含 tabledef 对象的成员函数，该对象的索引集合存储索引对象。 `CDaoIndexInfo` 还定义了 `Dump` 调试版本中的成员函数。 可以使用 `Dump` 转储对象的内容 `CDaoIndexInfo` 。

## <a name="requirements"></a>要求

**标头：** afxdao

## <a name="see-also"></a>请参阅

[结构、样式、回调和消息映射](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CDaoTableDef：： GetIndexInfo](../../mfc/reference/cdaotabledef-class.md#getindexinfo)
