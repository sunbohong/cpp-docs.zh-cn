---
description: 了解详细信息： CDaoTableDefInfo 结构
title: CDaoTableDefInfo 结构
ms.date: 11/04/2016
f1_keywords:
- CDaoTableDefInfo
helpviewer_keywords:
- CDaoTableDefInfo structure [MFC]
- DAO (Data Access Objects), TableDefs collection
ms.assetid: c01ccebb-5615-434e-883c-4f60eac943dd
ms.openlocfilehash: 953a255b35860dcce0ac8d3ef5081951dd15c344
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97247964"
---
# <a name="cdaotabledefinfo-structure"></a>CDaoTableDefInfo 结构

该 `CDaoTableDefInfo` 结构包含有关为 (DAO) 的数据访问对象定义的 tabledef 对象的信息。

## <a name="syntax"></a>语法

```
struct CDaoTableDefInfo
{
    CString m_strName;               // Primary
    BOOL m_bUpdatable;               // Primary
    long m_lAttributes;              // Primary
    COleDateTime m_dateCreated;      // Secondary
    COleDateTime m_dateLastUpdated;  // Secondary
    CString m_strSrcTableName;       // Secondary
    CString m_strConnect;            // Secondary
    CString m_strValidationRule;     // All
    CString m_strValidationText;     // All
    long m_lRecordCount;             // All
};
```

#### <a name="parameters"></a>parameters

*m_strName*<br/>
对 tabledef 对象进行唯一命名。 若要直接检索此属性的值，请调用 tabledef 对象的 [GetName](../../mfc/reference/cdaotabledef-class.md#getname) 成员函数。 有关详细信息，请参阅 DAO 帮助中的主题 "名称属性"。

*m_bUpdatable*<br/>
指示是否可对表进行更改。 确定表是否可更新的快速方法是打开 `CDaoTableDef` 表的对象，并调用该对象的 [CanUpdate](../../mfc/reference/cdaotabledef-class.md#canupdate) 成员函数。 `CanUpdate` 对于新创建的 tabledef 对象，始终返回非零 (TRUE) ，为附加 tabledef 对象返回 0 (FALSE) 。 只能将新的 tabledef 对象追加到当前用户对其具有写入权限的数据库。 如果表只包含 nonupdatable 字段，则 `CanUpdate` 返回0。 如果一个或多个字段可更新，则 `CanUpdate` 返回非零值。 你只能编辑可更新字段。 有关详细信息，请参阅 DAO 帮助中的主题 "可更新属性"。

*m_lAttributes*<br/>
指定 tabledef 对象所表示的表的特征。 若要检索 tabledef 的当前属性，请调用其 [GetAttributes](../../mfc/reference/cdaotabledef-class.md#getattributes) 成员函数。 返回的值可以是这些长常量的组合 (使用按位 "或" (**&#124;**) 运算符) ：

- `dbAttachExclusive` 对于使用 Microsoft Jet 数据库引擎的数据库，指示表是一个打开以供独占使用的附加表。

- `dbAttachSavePWD` 对于使用 Microsoft Jet 数据库引擎的数据库，指示附加表的用户 ID 和密码与连接信息一起保存。

- `dbSystemObject` 指示表是由 Microsoft Jet 数据库引擎提供的系统表。 （只读。）

- `dbHiddenObject` 指示表是 Microsoft Jet 数据库引擎提供的隐藏表， (暂时使用) 。 （只读。）

- `dbAttachedTable` 指示表是来自非 ODBC 数据库（如 Paradox 数据库）的附加表。

- `dbAttachedODBC` 指示表是来自 ODBC 数据库的附加表，如 Microsoft SQL Server。

*m_dateCreated*<br/>
表的创建日期和时间。 若要直接检索表的创建日期，请调用与该表关联的对象的 [GetDateCreated](../../mfc/reference/cdaotabledef-class.md#getdatecreated) 成员函数 `CDaoTableDef` 。 有关详细信息，请参阅下面的注释。 相关信息，请参阅 DAO 帮助中的主题 "DateCreated，LastUpdated Properties"。

*m_dateLastUpdated*<br/>
对表的设计所做的最新更改的日期和时间。 若要直接检索上次更新表的日期，请调用与该表关联的对象的 [GetDateLastUpdated](../../mfc/reference/cdaotabledef-class.md#getdatelastupdated) 成员函数 `CDaoTableDef` 。 有关详细信息，请参阅下面的注释。 相关信息，请参阅 DAO 帮助中的主题 "DateCreated，LastUpdated Properties"。

*m_strSrcTableName*<br/>
指定附加表的名称（如果有）。 若要直接检索源表名称，请调用与该表关联的对象的 [GetSourceTableName](../../mfc/reference/cdaotabledef-class.md#getsourcetablename) 成员函数 `CDaoTableDef` 。

*m_strConnect*<br/>
提供有关打开的数据库的源的信息。 可以通过调用对象的 [GetConnect](../../mfc/reference/cdaotabledef-class.md#getconnect) 成员函数来检查此属性 `CDaoTableDef` 。 有关连接字符串的详细信息，请参阅 `GetConnect` 。

*m_strValidationRule*<br/>
一个值，该值在 tabledef 字段中的数据更改或添加到表中时对其进行验证。 只有使用 Microsoft Jet 数据库引擎的数据库才支持验证。 若要直接检索验证规则，请调用与该表关联的对象的 [GetValidationRule](../../mfc/reference/cdaotabledef-class.md#getvalidationrule) 成员函数 `CDaoTableDef` 。 有关相关信息，请参阅 DAO 帮助中的主题 "有效性规则属性"。

*m_strValidationText*<br/>
一个值，该值指定当不满足 ValidationRule 属性指定的验证规则时，应用程序应显示的消息文本。 有关相关信息，请参阅 DAO 帮助中的主题 "有效性文本属性"。

*m_lRecordCount*<br/>
在 tabledef 对象中访问的记录数。 此属性设置是只读的。 若要直接检索记录计数，请调用对象的 [GetRecordCount](../../mfc/reference/cdaotabledef-class.md#getrecordcount) 成员函数 `CDaoTableDef` 。 有关 `GetRecordCount` 记录计数的详细说明，请参阅。 请注意，如果表中包含很多记录，则检索此计数可能是一个耗时的操作。

## <a name="remarks"></a>备注

Tabledef 是 [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md)类的对象。 对主要、次要和全部的引用指示类中的 [GetTableDefInfo](../../mfc/reference/cdaodatabase-class.md#gettabledefinfo) 成员函数返回信息的方式 `CDaoDatabase` 。

[CDaoDatabase：： GetTableDefInfo](../../mfc/reference/cdaodatabase-class.md#gettabledefinfo)成员函数检索的信息存储在 `CDaoTableDefInfo` 结构中。 调用 `GetTableDefInfo` `CDaoDatabase` TableDefs 集合中存储 tabledef 对象的对象的成员函数。 `CDaoTableDefInfo` 还定义了 `Dump` 调试版本中的成员函数。 可以使用 `Dump` 转储对象的内容 `CDaoTableDefInfo` 。

日期和时间设置派生自创建或上次更新基表的计算机。 在多用户环境中，用户应直接从文件服务器获取这些设置，以避免 DateCreated 和 LastUpdated 属性设置中的差异。

## <a name="requirements"></a>要求

**标头：** afxdao

## <a name="see-also"></a>请参阅

[结构、样式、回调和消息映射](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CDaoTableDef 类](../../mfc/reference/cdaotabledef-class.md)<br/>
[CDaoDatabase 类](../../mfc/reference/cdaodatabase-class.md)
