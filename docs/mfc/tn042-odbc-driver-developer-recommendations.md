---
description: 了解详细信息： TN042： ODBC 驱动程序开发人员建议
title: TN042：ODBC 驱动程序开发人员建议
ms.date: 11/04/2016
f1_keywords:
- vc.odbc
helpviewer_keywords:
- ODBC drivers [MFC], writing
- databases [MFC], ODBC
- TN042
ms.assetid: ecc6b5d9-f480-4582-9e22-8309fe561dad
ms.openlocfilehash: 896c99ffeba98f1ea38771676475c85abf13d983
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97215295"
---
# <a name="tn042-odbc-driver-developer-recommendations"></a>TN042：ODBC 驱动程序开发人员建议

> [!NOTE]
> 以下技术说明在首次包括在联机文档中后未更新。 因此，某些过程和主题可能已过时或不正确。 要获得最新信息，建议你在联机文档索引中搜索热点话题。

本说明介绍 ODBC 驱动程序编写器的准则。 它概述了 MFC 数据库类生成的 ODBC 功能的一般要求和假设，以及各种预期的语义详细信息。 介绍了支持三个 `CRecordset` 打开模式 (**forwardOnly**、 **snapshot** 和 **动态集**) 的必需驱动程序功能。

## <a name="odbcs-cursor-library"></a>ODBC 游标库

在许多情况下，MFC 数据库类向用户提供的功能超出了大多数级别 1 ODBC 驱动程序所提供的功能。 幸运的是，ODBC 的游标库将在数据库类和驱动程序之间进行分层，并将自动提供很多其他功能。

例如，大多数1.0 驱动程序不支持向后滚动。 游标库可以检测到这种情况，它将缓存来自驱动程序的行，并根据 FETCH_PREV 调用中的请求提供这些行 `SQLExtendedFetch` 。

游标库依赖关系的另一个重要示例是将更新定位。 大多数1.0 驱动程序也没有定位更新，但游标库将生成更新语句，该语句基于数据源当前缓存的数据值或缓存的时间戳值来标识数据源上的目标行。

类库决不会使用多个行集。 因此，这几个 `SQLSetPos` 语句始终应用于行集的第1行。

## <a name="cdatabases"></a>CDatabases

每个都 `CDatabase` 分配一个 **HDBC**。  (如果 `CDatabase` 使用了的 `ExecuteSQL` 函数，则会暂时分配一个 **HSTMT** 。 ) 因此，如果需要多个 `CDatabase` ，则必须支持多个 **HDBC** s **HENV** 。

数据库类需要游标库。 这会在 `SQLSetConnections` 调用 **SQL_ODBC_CURSORS** **SQL_CUR_USE_ODBC** 中反映出来。

`SQLDriverConnect`，使用 **SQL_DRIVER_COMPLETE** `CDatabase::Open` 来建立与数据源的连接。

驱动程序必须支持 `SQLGetInfo SQL_ODBC_API_CONFORMANCE`  >=  **SQL_OAC_LEVEL1**， `SQLGetInfo SQL_ODBC_SQL_CONFORMANCE`  >=  **SQL_OSC_MINIMUM**。

为了使事务支持 `CDatabase` 及其依赖记录集， `SQLGetInfo SQL_CURSOR_COMMIT_BEHAVIOR` **SQL_CURSOR_ROLLBACK_BEHAVIOR** 必须具有 **SQL_CR_PRESERVE**。 否则，将忽略执行事务控制的尝试。

`SQLGetInfo SQL_DATA_SOURCE_READ_ONLY` 必须受支持。 如果它返回 "Y"，则不会对数据源执行更新操作。

如果以 `CDatabase` 只读方式打开，将使用 SQL_MODE_READ_ONLY 设置数据源只读 `SQLSetConnectOption SQL_ACCESS_MODE` 。 

如果标识符需要引用引号，则应通过调用从驱动程序返回该信息 `SQLGetInfo SQL_IDENTIFIER_QUOTE_CHAR` 。

出于调试目的， `SQLGetInfo SQL_DBMS_VER` 从驱动程序检索 **SQL_DBMS_NAME** 。

`SQLSetStmtOption SQL_QUERY_TIMEOUT`可以在 HDBC 上调用和 SQL_ASYNC_ENABLE `CDatabase` 。 

`SQLError` 可在任何或所有参数为 NULL 的情况调用。

当然， `SQLAllocEnv` `SQLAllocConnect` `SQLDisconnect` 必须支持、和 `SQLFreeConnect` 。

## <a name="executesql"></a>ExecuteSQL

除了分配和释放临时 **HSTMT** 外，还会 `ExecuteSQL` 调用 `SQLExecDirect` 、 `SQLFetch` `SQLNumResultCol` 和 `SQLMoreResults` 。 `SQLCancel` 可在 **HSTMT** 上调用。

## <a name="getdatabasename"></a>GetDatabaseName

`SQLGetInfo SQL_DATABASE_NAME` 将被调用。

## <a name="begintrans-committrans-rollback"></a>BeginTrans、CommitTrans、Rollback

`SQLSetConnectOption SQL_AUTOCOMMIT``SQLTransact SQL_COMMIT`如果发出了事务请求，则将调用 **SQL_ROLLBACK** 和 **SQL_AUTOCOMMIT** 。

## <a name="crecordsets"></a>CRecordsets

`SQLAllocStmt``SQLPrepare` `SQLExecute` 对于 `Open` 和 `Requery`) ， `SQLExecDirect` 必须支持更新操作)  ( (`SQLFreeStmt` 。 `SQLNumResultCols``SQLDescribeCol`将在不同时间对结果集调用和。

`SQLSetParam` 广泛用于绑定参数数据和 **DATA_AT_EXEC** 功能。

`SQLBindCol` 广泛用于向 ODBC 注册输出列数据存储位置。

使用两个 `SQLGetData` 调用来检索 **SQL_LONG_VARCHAR** 和 **SQL_LONG_VARBINARY** 数据。 第一次调用将尝试通过 `SQLGetData` 使用 cbMaxValue （0）调用并使用有效的 pcbValue 来查找列值的总长度。 如果 pcbValue 保存 **SQL_NO_TOTAL**，则会引发异常。 否则，将分配 **HGLOBAL** ，并进行另一次 `SQLGetData` 调用以检索整个结果。

## <a name="updating"></a>更新

如果请求了悲观锁定， `SQLGetInfo SQL_LOCK_TYPES` 将会查询。 如果不支持 **SQL_LCK_EXCLUSIVE** ，则将引发异常。

尝试更新 `CRecordset` (**快照** 或 **动态集**) 将导致分配第二个 **HSTMT** 。 对于不支持第二个 **HSTMT** 的驱动程序，游标库将模拟此功能。 遗憾的是，这可能意味着在处理第二个 **HSTMT** 的请求之前，强制完成第一个 **HSTMT** 上的当前查询。

`SQLFreeStmt SQL_CLOSE` `SQLGetCursorName` 在更新操作过程中，将调用和 SQL_RESET_PARAMS 和。

如果 **outputColumns** 中有 **CLongBinarys** ，则必须支持 ODBC 的 **DATA_AT_EXEC** 功能。 这包括从 `SQLExecDirect` 、和返回 `SQLParamData` SQL_NEED_DATA `SQLPutData` 。

`SQLRowCount` 在执行后，将调用以验证是否只更新了1条记录 `SQLExecDirect` 。

## <a name="forwardonly-cursors"></a>ForwardOnly 游标

只有 `SQLFetch` 操作才需要 `Move` 。 请注意， **forwardOnly** 游标不支持更新。

## <a name="snapshot-cursors"></a>快照游标

快照功能需要 `SQLExtendedFetch` 支持。 如上所述，ODBC 游标库将检测驱动程序不支持的时间 `SQLExtendedFetch` ，并提供所需的支持。

`SQLGetInfo`**SQL_SCROLL_OPTIONS** 必须支持 **SQL_SO_STATIC**。

## <a name="dynaset-cursors"></a>动态集游标

下面是打开动态集中所需的最低支持：

`SQLGetInfo`， **SQL_ODBC_VER** 必须返回 > "01"。

`SQLGetInfo`**SQL_SCROLL_OPTIONS** 必须支持 **SQL_SO_KEYSET_DRIVEN**。

`SQLGetInfo`， **SQL_ROW_UPDATES** 必须返回 "Y"。

`SQLGetInfo`**SQL_POSITIONED_UPDATES** 必须支持 **SQL_PS_POSITIONED_DELETE** 和 **SQL_PS_POSITIONED_UPDATE**。

此外，如果请求了悲观锁定，则 `SQLSetPos` 将使用 irow 1、FREFRESH FALSE 和 fLock **SQL_LCK_EXCLUSIVE** 调用。

## <a name="see-also"></a>请参阅

[按编号的技术说明](../mfc/technical-notes-by-number.md)<br/>
[按类别列出的技术说明](../mfc/technical-notes-by-category.md)
