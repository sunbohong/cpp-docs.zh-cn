---
title: 数据库宏和全局函数
ms.date: 11/04/2016
f1_keywords:
- AFXDB/AFX_ODBC_CALL
- AFXDB/AFX_SQL_ASYNC
- AFXDB/AFX_SQL_SYNC
- AFXDB/AfxGetHENV
helpviewer_keywords:
- global database functions [MFC]
- database macros [MFC]
- database globals [MFC]
- global functions [MFC], database functions
- macros [MFC], MFC database
ms.assetid: 5b9b9e61-1cf9-4345-9f29-3807dd466488
ms.openlocfilehash: 0dc53bce8b43677e7fe0aa1787d1adcc16a560c4
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/25/2020
ms.locfileid: "88837522"
---
# <a name="database-macros-and-globals"></a>数据库宏和全局函数

下面所列的宏和全局适用于基于 ODBC 的数据库应用程序。 它们不适用于基于 DAO 的应用程序。

在 MFC 4.2 版之前，宏 `AFX_SQL_ASYNC` 和 `AFX_SQL_SYNC` 为异步操作提供了为其他进程让出时间的机会。 从 MFC 4.2 开始，这些宏的实现已改变，因为 MFC ODBC 类仅使用同步操作。 宏 `AFX_ODBC_CALL` 是 MFC 4.2 中新增的。

### <a name="database-macros"></a>数据库宏

|名称|说明|
|-|-|
|[AFX_ODBC_CALL](#afx_odbc_call)|调用返回 `SQL_STILL_EXECUTING` 的 ODBC API 函数。 `AFX_ODBC_CALL` 将反复调用该函数，直到不再返回 `SQL_STILL_EXECUTING`。|
|[AFX_SQL_ASYNC](#afx_sql_async)|调用 `AFX_ODBC_CALL`。|
|[AFX_SQL_SYNC](#afx_sql_sync)|调用不返回 `SQL_STILL_EXECUTING` 的 ODBC API 函数。|

### <a name="database-globals"></a>数据库全局

|名称|说明|
|-|-|
|[AfxDbInitModule](#afxdbinitmodule)|为动态链接到 MFC 的常规 MFC DLL 添加数据库支持。|
|[AfxGetHENV](#afxgethenv)|检索 MFC 当前正在使用的 ODBC 环境的句柄。 您可以在直接 ODBC 调用中使用此句柄。|

## <a name="afxdbinitmodule"></a><a name="afxdbinitmodule"></a> AfxDbInitModule

对于 MFC 数据库 (或 DAO) 从动态链接到 MFC 的规则 MFC DLL 的支持，请在常规 MFC DLL 的函数中添加对此函数的调用， `CWinApp::InitInstance` 以初始化 MFC 数据库 dll。

### <a name="syntax"></a>语法

```cpp
void AFXAPI AfxDbInitModule( );
```

### <a name="remarks"></a>备注

请确保此调用发生在任何基类调用或访问 MFC 数据库 DLL 的任何已添加代码之前。 MFC 数据库 DLL 是 MFC 扩展 DLL;为了使 MFC 扩展 DLL 能够连接到 `CDynLinkLibrary` 链，它必须 `CDynLinkLibrary` 在将使用它的每个模块的上下文中创建一个对象。 `AfxDbInitModule``CDynLinkLibrary`在您的常规 MFC dll 的上下文中创建对象，使其连接到 `CDynLinkLibrary` 常规 mfc dll 的对象链。

### <a name="requirements"></a>要求

**标头：**\<afxdll_.h>

## <a name="afx_odbc_call"></a><a name="afx_odbc_call"></a> AFX_ODBC_CALL

使用此宏可以调用任何可能返回的 ODBC API 函数 `SQL_STILL_EXECUTING` 。

```
AFX_ODBC_CALL(SQLFunc)
```

### <a name="parameters"></a>参数

*SQLFunc*<br/>
ODBC API 函数。 有关 ODBC API 函数的详细信息，请参阅 Windows SDK。

### <a name="remarks"></a>注解

`AFX_ODBC_CALL` 重复调用函数，直到它不再返回 `SQL_STILL_EXECUTING` 。

在调用之前 `AFX_ODBC_CALL` ，必须声明一个 `nRetCode` 类型为 RETCODE 的变量。

请注意，MFC ODBC 类现在仅使用同步处理。 若要执行异步操作，必须调用 ODBC API 函数 `SQLSetConnectOption` 。 有关详细信息，请参阅 Windows SDK 中的 "异步执行函数" 主题。

### <a name="example"></a>示例

此示例使用 `AFX_ODBC_CALL` 调用 `SQLColumns` ODBC API 函数，该函数返回名为的表中的列的列表 `strTableName` 。 请注意声明 `nRetCode` 和使用记录集数据成员将参数传递给函数。 该示例还说明了如何使用 `Check` （类的成员函数）检查调用结果 `CRecordset` 。 变量 `prs` 是指向对象的指针 `CRecordset` ，在其他位置声明。

[!code-cpp[NVC_MFCDatabase#39](../../mfc/codesnippet/cpp/database-macros-and-globals_1.cpp)]

### <a name="requirements"></a>要求

**标头：** afxdb

## <a name="afx_sql_async"></a><a name="afx_sql_async"></a> AFX_SQL_ASYNC

此宏的实现在 MFC 4.2 中发生更改。

```
AFX_SQL_ASYNC(prs, SQLFunc)
```

### <a name="parameters"></a>参数

*pr*<br/>
指向 `CRecordset` 对象或 `CDatabase` 对象的指针。 从 MFC 4.2 开始，将忽略此参数值。

*SQLFunc*<br/>
ODBC API 函数。 有关 ODBC API 函数的详细信息，请参阅 Windows SDK。

### <a name="remarks"></a>注解

`AFX_SQL_ASYNC` 只需调用宏 [AFX_ODBC_CALL](#afx_odbc_call) 并忽略 *pr* 参数。 在 4.2 之前的 MFC 版本中，`AFX_SQL_ASYNC` 用于调用可能返回 `SQL_STILL_EXECUTING` 的 ODBC API 函数。 如果 ODBC API 函数返回 `SQL_STILL_EXECUTING`，则 `AFX_SQL_ASYNC` 将调用 `prs->OnWaitForDataSource`。

> [!NOTE]
> MFC ODBC 类现在只能使用同步处理。 若要执行异步操作，必须调用 ODBC API 函数 `SQLSetConnectOption` 。 有关详细信息，请参阅 Windows SDK 中的 "异步执行函数" 主题。

### <a name="requirements"></a>要求

  **标头** afxdb

## <a name="afx_sql_sync"></a><a name="afx_sql_sync"></a> AFX_SQL_SYNC

`AFX_SQL_SYNC`宏只调用函数 `SQLFunc` 。

```
AFX_SQL_SYNC(SQLFunc)
```

### <a name="parameters"></a>参数

*SQLFunc*<br/>
ODBC API 函数。 有关这些函数的详细信息，请参阅 Windows SDK。

### <a name="remarks"></a>注解

使用此宏调用将不返回的 ODBC API 函数 `SQL_STILL_EXECUTING` 。

在调用之前 `AFX_SQL_SYNC` ，必须声明一个 `nRetCode` 类型为 RETCODE 的变量。 可以在 `nRetCode` 宏调用后检查的值。

请注意， `AFX_SQL_SYNC` MFC 4.2 中已更改的实现。 由于不再需要检查服务器状态，因此 `AFX_SQL_SYNC` 只需将一个值分配给 `nRetCode` 。 例如，而不是进行调用

[!code-cpp[NVC_MFCDatabase#40](../../mfc/codesnippet/cpp/database-macros-and-globals_2.cpp)]

只需进行赋值即可

[!code-cpp[NVC_MFCDatabase#41](../../mfc/codesnippet/cpp/database-macros-and-globals_3.cpp)]

### <a name="requirements"></a>要求

  **标头** afxdb

## <a name="afxgethenv"></a><a name="afxgethenv"></a> AfxGetHENV

可以在直接 ODBC 调用中使用返回的句柄，但不能关闭句柄，也不能假定该句柄仍有效并且在销毁任何现有 `CDatabase` 或 `CRecordset` 派生对象之后可用。

```
HENV AFXAPI AfxGetHENV();
```

### <a name="return-value"></a>返回值

MFC 当前正在使用的 ODBC 环境的句柄。 如果没有 `SQL_HENV_NULL` [CDatabase](../../mfc/reference/cdatabase-class.md) 对象，且未使用 [CRecordset](../../mfc/reference/crecordset-class.md) 对象，则可以为。

### <a name="requirements"></a>要求

  **标头** afxdb

## <a name="see-also"></a>另请参阅

[MFC 宏和全局函数](../../mfc/reference/mfc-macros-and-globals.md)
