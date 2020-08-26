---
title: CSession 类
ms.date: 11/04/2016
f1_keywords:
- CSession
- ATL::CSession
- ATL.CSession
- CSession.Abort
- CSession::Abort
- ATL.CSession.Abort
- ATL::CSession::Abort
- CSession::Close
- ATL.CSession.Close
- CSession.Close
- ATL::CSession::Close
- CSession.Commit
- ATL.CSession.Commit
- ATL::CSession::Commit
- CSession::Commit
- GetTransactionInfo
- CSession.GetTransactionInfo
- ATL.CSession.GetTransactionInfo
- CSession::GetTransactionInfo
- ATL::CSession::GetTransactionInfo
- ATL::CSession::Open
- CSession::Open
- CSession.Open
- ATL.CSession.Open
- CSession::StartTransaction
- StartTransaction
- ATL.CSession.StartTransaction
- CSession.StartTransaction
- ATL::CSession::StartTransaction
helpviewer_keywords:
- CSession class
- Abort method
- Close method
- Commit method
- GetTransactionInfo method
- Open method
- StartTransaction method
ms.assetid: 83cd798f-b45d-4f11-a23c-29183390450c
ms.openlocfilehash: 6858c26df5f5ee364717d089704117e650282278
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/25/2020
ms.locfileid: "88841098"
---
# <a name="csession-class"></a>CSession 类

表示单个数据库访问会话。

## <a name="syntax"></a>语法

```cpp
class CSession
```

## <a name="requirements"></a>要求

**标头:** atldbcli.h

## <a name="members"></a>成员

### <a name="methods"></a>方法

| 名称 | 说明 |
|-|-|
|[中断](#abort)|取消（终止）事务。|
|[关闭](#close)|关闭会话。|
|[提交](#commit)|提交事务。|
|[GetTransactionInfo](#gettransactioninfo)|返回有关事务的信息。|
|[打开](#open)|为数据源对象打开新会话。|
|[StartTransaction](#starttransaction)|开始此会话的新事务。|

## <a name="remarks"></a>注解

一个或多个会话可以与 (数据源) 的每个提供程序连接相关联，这由 [CDataSource](../../data/oledb/cdatasource-class.md) 对象表示。 若要为创建新 `CSession` 的 `CDataSource` ，请调用 [CSession：： Open](../../data/oledb/csession-open.md)。 为了开始数据库事务，`CSession` 提供了 `StartTransaction` 方法。 事务启动后，可以使用方法提交到该事务 `Commit` ，或使用方法取消该事务 `Abort` 。

## <a name="csessionabort"></a><a name="abort"></a> CSession：： Abort

终止事务。

### <a name="syntax"></a>语法

```cpp
HRESULT Abort(BOID* pboidReason = NULL,
   BOOL bRetaining = FALSE,
   BOOL bAsync = FALSE) const throw();
```

#### <a name="parameters"></a>参数

请参阅*OLE DB 程序员参考*中的[ITransaction：： Abort](/previous-versions/windows/desktop/ms709833(v=vs.85)) 。

### <a name="return-value"></a>返回值

标准的 HRESULT。

## <a name="csessionclose"></a><a name="close"></a> CSession：： Close

关闭已通过 [CSession：： Open](../../data/oledb/csession-open.md)打开的会话。

### <a name="syntax"></a>语法

```cpp
void Close() throw();
```

### <a name="remarks"></a>备注

释放 `m_spOpenRowset` 指针。

## <a name="csessioncommit"></a><a name="commit"></a> CSession：： Commit

提交事务。

### <a name="syntax"></a>语法

```cpp
HRESULT Commit(BOOL bRetaining = FALSE,
   DWORD grfTC = XACTTC_SYNC,
   DWORD grfRM = 0) const throw();
```

#### <a name="parameters"></a>参数

请参阅*OLE DB 程序员参考*中的[ITransaction：： Commit](/previous-versions/windows/desktop/ms713008(v=vs.85)) 。

### <a name="return-value"></a>返回值

标准的 HRESULT。

### <a name="remarks"></a>注解

有关详细信息，请参阅 [ITransaction：： Commit](/previous-versions/windows/desktop/ms713008(v=vs.85))。

## <a name="csessiongettransactioninfo"></a><a name="gettransactioninfo"></a> CSession：： GetTransactionInfo

返回有关事务的信息。

### <a name="syntax"></a>语法

```cpp
HRESULT GetTransactionInfo(XACTTRANSINFO* pInfo) const throw();
```

#### <a name="parameters"></a>参数

请参阅*OLE DB 程序员参考*中的[ITransaction：： GetTransactionInfo](/previous-versions/windows/desktop/ms714975(v=vs.85)) 。

### <a name="return-value"></a>返回值

标准的 HRESULT。

### <a name="remarks"></a>注解

有关详细信息，请参阅*OLE DB 程序员参考*中的[ITransaction：： GetTransactionInfo](/previous-versions/windows/desktop/ms714975(v=vs.85)) 。

## <a name="csessionopen"></a><a name="open"></a> CSession：： Open

为数据源对象打开新会话。

### <a name="syntax"></a>语法

```cpp
HRESULT Open(const CDataSource& ds,
   DBPROPSET *pPropSet = NULL,
   ULONG ulPropSets = 0) throw();
```

#### <a name="parameters"></a>参数

*ds*<br/>
中要为其打开会话的数据源。

*pPropSet*<br/>
中指向包含要设置的属性和值的 [DBPROPSET](/previous-versions/windows/desktop/ms714367(v=vs.85)) 结构的数组的指针。 请参阅 Windows SDK 中*OLE DB 程序员参考*中的[属性集和属性组](/previous-versions/windows/desktop/ms713696(v=vs.85))。

*ulPropSets*<br/>
中在*传入 ppropset*参数中传递的[DBPROPSET](/previous-versions/windows/desktop/ms714367(v=vs.85))结构的数目。

### <a name="return-value"></a>返回值

标准的 HRESULT。

### <a name="remarks"></a>注解

在将数据源对象传递到之前，必须使用 [CDataSource：： open](../../data/oledb/cdatasource-open.md) 打开该对象 `CSession::Open` 。

## <a name="csessionstarttransaction"></a><a name="starttransaction"></a> CSession：： StartTransaction

开始此会话的新事务。

### <a name="syntax"></a>语法

```cpp
HRESULT StartTransaction(ISOLEVEL isoLevel = ISOLATIONLEVEL_READCOMMITTED,
   ULONG isoFlags = 0,
   ITransactionOptions* pOtherOptions = NULL,
   ULONG* pulTransactionLevel = NULL) const throw();
```

#### <a name="parameters"></a>参数

请参阅*OLE DB 程序员参考*中的[ITransactionLocal：： StartTransaction](/previous-versions/windows/desktop/ms709786(v=vs.85)) 。

### <a name="return-value"></a>返回值

标准的 HRESULT。

### <a name="remarks"></a>注解

有关详细信息，请参阅*OLE DB 程序员参考*中的[ITransactionLocal：： StartTransaction](/previous-versions/windows/desktop/ms709786(v=vs.85)) 。

## <a name="see-also"></a>另请参阅

[CatDB](../../overview/visual-cpp-samples.md)<br/>
[OLE DB 使用者模板](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB 使用者模板参考](../../data/oledb/ole-db-consumer-templates-reference.md)
