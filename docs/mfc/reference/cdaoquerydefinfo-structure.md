---
description: 了解详细信息： CDaoQueryDefInfo 结构
title: CDaoQueryDefInfo 结构
ms.date: 11/04/2016
f1_keywords:
- CDaoQueryDefInfo
helpviewer_keywords:
- DAO (Data Access Objects), QueryDefs collection
- CDaoQueryDefInfo structure [MFC]
ms.assetid: e20837dc-e78d-4171-a195-1b4075fb5d2a
ms.openlocfilehash: 46b9b49d91d3d005d941eb585663c205fe30b2da
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97271806"
---
# <a name="cdaoquerydefinfo-structure"></a>CDaoQueryDefInfo 结构

该 `CDaoQueryDefInfo` 结构包含有关为 (DAO) 的数据访问对象定义的 querydef 对象的信息。

## <a name="syntax"></a>语法

```
struct CDaoQueryDefInfo
{
    CString m_strName;               // Primary
    short m_nType;   // Primary
    COleDateTime m_dateCreated;      // Secondary
    COleDateTime m_dateLastUpdated;  // Secondary
    BOOL m_bUpdatable;               // Secondary
    BOOL m_bReturnsRecords;          // Secondary
    CString m_strSQL;                // All
    CString m_strConnect;            // All
    short m_nODBCTimeout;            // All
};
```

#### <a name="parameters"></a>parameters

*m_strName*<br/>
对 querydef 对象进行唯一命名。 有关详细信息，请参阅 DAO 帮助中的主题 "名称属性"。 调用 [CDaoQueryDef：： GetName](../../mfc/reference/cdaoquerydef-class.md#getname) 直接检索此属性。

*m_nType*<br/>
指示 querydef 对象的操作类型的值。 值可以是下列任一值：

- `dbQSelect` Select-查询选择记录。

- `dbQAction` 操作-查询移动或更改数据，但不返回记录。

- `dbQCrosstab` 交叉表-查询以类似电子表格的格式返回数据。

- `dbQDelete` 删除-查询删除一组指定的行。

- `dbQUpdate` Update-查询更改一组记录。

- `dbQAppend` 追加-查询在表或查询的末尾添加新记录。

- `dbQMakeTable` "生成表"-查询从记录集创建新表。

- `dbQDDL` 数据定义-查询会影响表或其部件的结构。

- `dbQSQLPassThrough` 传递-SQL 语句直接传递到数据库后端，而无需进行中间处理。

- `dbQSetOperation` Union-查询创建一个快照类型记录集对象，该对象包含两个或多个表中所有指定记录的数据，并删除所有重复记录。 若要包含重复项，请在 querydef 的 SQL 语句中添加关键字 **ALL** 。

- `dbQSPTBulk` 与结合使用 `dbQSQLPassThrough` 可指定不返回记录的查询。

> [!NOTE]
> 若要创建 SQL 传递查询，请不要设置 `dbQSQLPassThrough` 常量。 当你创建 querydef 对象并设置 "连接" 属性时，Microsoft Jet 数据库引擎会自动设置此属性。

有关详细信息，请参阅 DAO 帮助中的 "类型属性" 主题。

*m_dateCreated*<br/>
创建 querydef 的日期和时间。 若要直接检索创建 querydef 的日期，请调用与该表关联的对象的 [GetDateCreated](../../mfc/reference/cdaotabledef-class.md#getdatecreated) 成员函数 `CDaoTableDef` 。 有关详细信息，请参阅下面的注释。 另请参阅 DAO 帮助中的主题 "DateCreated，LastUpdated Properties"。

*m_dateLastUpdated*<br/>
对 querydef 进行的最新更改的日期和时间。 若要直接检索上次更新表的日期，请调用 querydef 的 [GetDateLastUpdated](../../mfc/reference/cdaoquerydef-class.md#getdatelastupdated) 成员函数。 有关详细信息，请参阅下面的注释。 并参阅 DAO 帮助中的主题 "DateCreated，LastUpdated Properties"。

*m_bUpdatable*<br/>
指示是否可以对 querydef 对象进行更改。 如果此属性为 TRUE，则 querydef 可更新;否则为。 可更新意味着可以更改 querydef 对象的查询定义。 如果查询定义可以更新，则 querydef 对象的可更新属性将设置为 TRUE，即使生成的记录集不可更新。 若要直接检索此属性，请调用 querydef 的 [CanUpdate](../../mfc/reference/cdaoquerydef-class.md#canupdate) 成员函数。 有关详细信息，请参阅 DAO 帮助中的主题 "可更新属性"。

*m_bReturnsRecords*<br/>
指示对外部数据库的 SQL 传递查询是否返回记录。 如果此属性为 TRUE，则查询将返回记录。 若要直接检索此属性，请调用 [CDaoQueryDef：： GetReturnsRecords](../../mfc/reference/cdaoquerydef-class.md#getreturnsrecords)。 并非所有对外部数据库的 SQL 传递查询都返回记录。 例如，SQL **UPDATE** 语句更新记录，而不返回记录，而 sql **SELECT** 语句则返回记录。 有关详细信息，请参阅 DAO 帮助中的主题 "ReturnsRecords 属性"。

*m_strSQL*<br/>
定义由 querydef 对象执行的查询的 SQL 语句。 SQL 属性包含 SQL 语句，该语句确定在执行查询时如何选择、分组和排序记录。 您可以使用查询来选择要包括在动态集或快照类型记录集对象中的记录。 您还可以定义批量查询来修改数据，而不返回记录。 可以通过调用 querydef 的 [GetSQL](../../mfc/reference/cdaoquerydef-class.md#getsql) 成员函数，直接检索此属性的值。

*m_strConnect*<br/>
提供有关传递查询中使用的数据库的源的信息。 此信息采用连接字符串的形式。 有关连接字符串的详细信息，以及有关直接检索此属性的值的信息，请参阅 [CDaoDatabase：： GetConnect](../../mfc/reference/cdaodatabase-class.md#getconnect) 成员函数。

*m_nODBCTimeout*<br/>
当查询在 ODBC 数据库上运行时，Microsoft Jet 数据库引擎等待的秒数，出现超时错误。 使用 ODBC 数据库（如 Microsoft SQL Server）时，可能会由于网络流量或大量使用 ODBC 服务器而导致延迟。 您可以指定 Microsoft Jet 引擎在生成错误之前等待的时间，而不是无限期等待。 默认超时值为60秒。 可以通过调用 querydef 的 [GetODBCTimeout](../../mfc/reference/cdaoquerydef-class.md#getodbctimeout) 成员函数，直接检索此属性的值。 有关详细信息，请参阅 DAO 帮助中的主题 "ODBCTimeout 属性"。

## <a name="remarks"></a>备注

Querydef 是 [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md)类的对象。 对主要、次要和全部的引用指示类中的 [GetQueryDefInfo](../../mfc/reference/cdaodatabase-class.md#getquerydefinfo) 成员函数返回信息的方式 `CDaoDatabase` 。

[CDaoDatabase：： GetQueryDefInfo](../../mfc/reference/cdaodatabase-class.md#getquerydefinfo)成员函数检索的信息存储在 `CDaoQueryDefInfo` 结构中。 调用 `GetQueryDefInfo` ，其中存储了 querydef 对象的 QueryDefs 集合中的数据库对象。 `CDaoQueryDefInfo` 还定义了 `Dump` 调试版本中的成员函数。 可以使用 `Dump` 转储对象的内容 `CDaoQueryDefInfo` 。 类 `CDaoDatabase` 还提供成员函数以直接访问对象中返回的所有属性 `CDaoQueryDefInfo` ，因此很少需要调用 `GetQueryDefInfo` 。

向 querydef 对象的字段或参数集合追加新的字段或参数对象时，如果基础数据库不支持为新对象指定的数据类型，则会引发异常。

日期和时间设置派生自创建了 querydef 的计算机或上次更新的计算机。 在多用户环境中，用户应使用 **net time** 命令直接从文件服务器获取这些设置，以避免 DateCreated 和 LastUpdated 属性设置中的差异。

## <a name="requirements"></a>要求

**标头：** afxdao

## <a name="see-also"></a>请参阅

[结构、样式、回调和消息映射](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CDaoQueryDef 类](../../mfc/reference/cdaoquerydef-class.md)<br/>
[CDaoDatabase 类](../../mfc/reference/cdaodatabase-class.md)
