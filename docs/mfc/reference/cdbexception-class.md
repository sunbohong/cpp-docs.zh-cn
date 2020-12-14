---
description: 了解详细信息： CDBException 类
title: CDBException 类
ms.date: 11/04/2016
f1_keywords:
- CDBException
- AFXDB/CDBException
- AFXDB/CDBException::m_nRetCode
- AFXDB/CDBException::m_strError
- AFXDB/CDBException::m_strStateNativeOrigin
helpviewer_keywords:
- CDBException [MFC], m_nRetCode
- CDBException [MFC], m_strError
- CDBException [MFC], m_strStateNativeOrigin
ms.assetid: eb9e1119-89f5-49a7-b9d4-b91cee1ccc82
ms.openlocfilehash: 8e337cc0f66a4a281de07ba3839895096e8021d0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97222120"
---
# <a name="cdbexception-class"></a>CDBException 类

表示由数据库类引起的异常条件。

## <a name="syntax"></a>语法

```
class CDBException : public CException
```

## <a name="members"></a>成员

### <a name="public-data-members"></a>公共数据成员

|名称|描述|
|----------|-----------------|
|[CDBException：： m_nRetCode](#m_nretcode)|包含 RETCODE 类型的开放式数据库连接 (ODBC) 返回代码。|
|[CDBException：： m_strError](#m_strerror)|包含一个字符串，该字符串描述了字母数字术语中的错误。|
|[CDBException：： m_strStateNativeOrigin](#m_strstatenativeorigin)|包含一个字符串，该字符串描述 ODBC 返回的错误代码的错误。|

## <a name="remarks"></a>备注

类包含两个公共数据成员，您可以使用它们来确定异常的原因或显示描述该异常的文本消息。 `CDBException` 对象由数据库类的成员函数构造和引发。

> [!NOTE]
> 此类是 MFC 的开放式数据库连接 (ODBC) 类之一。 如果使用的是新的数据访问对象 (DAO) 类，请改用 [CDaoException](../../mfc/reference/cdaoexception-class.md) 。 所有 DAO 类名称都将 "CDao" 作为前缀。 有关详细信息，请参阅文章 [概述：数据库编程](../../data/data-access-programming-mfc-atl.md)。

异常是涉及程序控件之外的条件（如数据源或网络 i/o 错误）的异常执行情况。 通常，在执行程序的过程中，您可能希望看到的错误通常不被视为例外。

您可以在 **CATCH** 表达式的作用域内访问这些对象。 还可以 `CDBException` 通过全局函数从自己的代码中引发对象 `AfxThrowDBException` 。

有关一般情况下的异常处理或关于对象的详细信息， `CDBException` 请参阅文章 [异常处理 (MFC) ](../../mfc/exception-handling-in-mfc.md) 和 [异常：数据库异常](../../mfc/exceptions-database-exceptions.md)。

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

`CDBException`

## <a name="requirements"></a>要求

**标头：** afxdb

## <a name="cdbexceptionm_nretcode"></a><a name="m_nretcode"></a> CDBException：： m_nRetCode

包含 ODBC 应用程序编程接口 (API) 函数返回的类型为 RETCODE 的 ODBC 错误代码。

### <a name="remarks"></a>备注

此类型包含由 ODBC 定义的 SQL 前缀代码和由数据库类定义 AFX_SQL 前缀的代码。 对于 `CDBException` ，此成员将包含以下值之一：

- AFX_SQL_ERROR_API_CONFORMANCE 的驱动程序 `CDatabase::OpenEx` 或 `CDatabase::Open` 调用不符合所需的 ODBC API 一致性级别 1 ( SQL_OAC_LEVEL1) 。

- AFX_SQL_ERROR_CONNECT_FAIL 连接到数据源失败。 您向您的 `CDatabase` 记录集构造函数传递了一个空指针，并且基于的后续尝试创建连接 `GetDefaultConnect` 失败。

- AFX_SQL_ERROR_DATA_TRUNCATED 你请求的数据超过为提供存储的数据。 有关增加为或数据类型提供的数据存储的信息 `CString` `CByteArray` ，请参阅 `nMaxLength` "宏和全局" 下面的 [RFX_Text](record-field-exchange-functions.md#rfx_text) 和 [RFX_Binary](record-field-exchange-functions.md#rfx_binary) 的参数。

- AFX_SQL_ERROR_DYNASET_NOT_SUPPORTED 调用 `CRecordset::Open` 请求动态集中失败。 驱动程序不支持动态集。

- AFX_SQL_ERROR_EMPTY_COLUMN_LIST 您尝试打开一个表 (或您所赋予的内容无法识别为过程调用或 **SELECT** 语句) 但在重写中，在记录字段交换 (RFX) 函数调用中找不到这些列 `DoFieldExchange` 。

- AFX_SQL_ERROR_FIELD_SCHEMA_MISMATCH 重写中 RFX 函数的类型 `DoFieldExchange` 与记录集中的列数据类型不兼容。

- 在之前调用 AFX_SQL_ERROR_ILLEGAL_MODE， `CRecordset::Update` 而不调用 `CRecordset::AddNew` 或 `CRecordset::Edit` 。

- AFX_SQL_ERROR_LOCK_MODE_NOT_SUPPORTED 由于 ODBC 驱动程序不支持锁定，无法满足为更新锁定记录的请求。

- `CRecordset::Update` `Delete` 为没有唯一键并更改了多个记录的表调用或 AFX_SQL_ERROR_MULTIPLE_ROWS_AFFECTED。

- AFX_SQL_ERROR_NO_CURRENT_RECORD 您尝试编辑或删除以前删除的记录。 删除后必须滚动到新的当前记录。

- AFX_SQL_ERROR_NO_POSITIONED_UPDATES 无法满足动态集的请求，因为 ODBC 驱动程序不支持定位更新。

- AFX_SQL_ERROR_NO_ROWS_AFFECTED 您调用 `CRecordset::Update` `Delete` 了或，但在操作开始后，将无法再找到该记录。

- AFX_SQL_ERROR_ODBC_LOAD_FAILED 尝试加载 ODBC.DLL 失败;Windows 找不到或无法加载此 DLL。 此错误是致命错误。

- AFX_SQL_ERROR_ODBC_V2_REQUIRED 无法满足对动态集的请求，因为需要与级别2兼容的 ODBC 驱动程序。

- AFX_SQL_ERROR_RECORDSET_FORWARD_ONLY 尝试滚动失败，因为数据源不支持向后滚动。

- AFX_SQL_ERROR_SNAPSHOT_NOT_SUPPORTED 调用 `CRecordset::Open` 请求快照失败。 驱动程序不支持快照。  (仅当 ODBC 游标库 ODBCCURS.DLL 不存在时才会发生这种情况。 ) 

- AFX_SQL_ERROR_SQL_CONFORMANCE 的驱动程序， `CDatabase::OpenEx` 或 `CDatabase::Open` 调用不符合 "最小" (SQL_OSC_MINIMUM) 所需的 ODBC SQL 一致性级别。

- AFX_SQL_ERROR_SQL_NO_TOTAL ODBC 驱动程序无法指定数据值的总大小 `CLongBinary` 。 操作可能失败，因为无法预分配全局内存块。

- AFX_SQL_ERROR_RECORDSET_READONLY 您尝试更新只读记录集，或者数据源为只读。 不能对记录集或与之关联的对象执行任何更新操作 `CDatabase` 。

- SQL_ERROR 函数失败。 ODBC 函数返回的错误消息 `SQLError` 存储在 `m_strError` 数据成员中。

- SQL_INVALID_HANDLE 函数失败，因为环境句柄、连接句柄或语句句柄无效。 这表明编程错误。 ODBC 函数不提供其他信息 `SQLError` 。

SQL 前缀代码由 ODBC 定义。 AFX 前缀代码在 AFXDB 中定义。H，在 MFC\INCLUDE. 中找到

## <a name="cdbexceptionm_strerror"></a><a name="m_strerror"></a> CDBException：： m_strError

包含一个字符串，该字符串描述导致了异常的错误。

### <a name="remarks"></a>备注

字符串描述了字母数字术语中的错误。 有关更多详细信息和示例，请参阅 `m_strStateNativeOrigin` 。

## <a name="cdbexceptionm_strstatenativeorigin"></a><a name="m_strstatenativeorigin"></a> CDBException：： m_strStateNativeOrigin

包含一个字符串，该字符串描述导致了异常的错误。

### <a name="remarks"></a>备注

此字符串的格式为 "State：% s，Native：% ld，原点：% s"，其中格式代码按顺序替换为以下值：

- SQLSTATE，以 null 结尾的字符串，其中包含在 ODBC 函数的 *szSqlState* 参数中返回的五个字符的错误代码 `SQLError` 。 SQLSTATE 值在 *Odbc 程序员参考* 中的附录 A： [odbc 错误代码](/sql/odbc/reference/appendixes/appendix-a-odbc-error-codes)中列出。 例如： "S0022"。

- 特定于数据源的本机错误代码，在函数的 *pfNativeError* 参数中返回 `SQLError` 。 例如：207。

- 在函数的 *szErrorMsg* 参数中返回的错误消息文本 `SQLError` 。 此消息包含若干个用括号括起来的名称。 当向用户传递错误时，每个 ODBC 组件 (数据源、驱动程序管理器) 会附加其自己的名称。 此信息可帮助确定错误的来源。 示例： [Microsoft] [ODBC SQL Server Driver] [SQL Server]

框架解释错误字符串并将其组件放入 `m_strStateNativeOrigin` ; 如果 `m_strStateNativeOrigin` 包含多个错误的信息，错误将由换行符分隔。 框架将字母数字错误文本放入中 `m_strError` 。

有关用于构成此字符串的代码的其他信息，请参阅 *ODBC 程序员参考* 中的 [SQLError](/sql/odbc/reference/syntax/sqlerror-function)函数。

### <a name="example"></a>示例

From ODBC： "State： S0022，Native：207，原点： \[ Microsoft] \[ ODBC SQL Server Driver] \[ SQL Server] 列名" ColName "无效

In `m_strStateNativeOrigin` ： "State： S0022，Native：207，原点： \[ Microsoft] \[ ODBC SQL Server Driver] \[ SQL Server]"

In `m_strError` ： "列名称 ' ColName ' 无效"

## <a name="see-also"></a>请参阅

[CException 类](../../mfc/reference/cexception-class.md)<br/>
[层次结构图](../../mfc/hierarchy-chart.md)<br/>
[CDatabase 类](../../mfc/reference/cdatabase-class.md)<br/>
[CRecordset 类](../../mfc/reference/crecordset-class.md)<br/>
[CFieldExchange 类](../../mfc/reference/cfieldexchange-class.md)<br/>
[CRecordset：： Update](../../mfc/reference/crecordset-class.md#update)<br/>
[CRecordset：:D e) ](../../mfc/reference/crecordset-class.md#delete)<br/>
[CException 类](../../mfc/reference/cexception-class.md)
