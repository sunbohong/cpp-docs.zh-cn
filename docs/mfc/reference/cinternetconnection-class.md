---
description: 了解详细信息： CInternetConnection 类
title: CInternetConnection 类
ms.date: 11/04/2016
f1_keywords:
- CInternetConnection
- AFXINET/CInternetConnection
- AFXINET/CInternetConnection::CInternetConnection
- AFXINET/CInternetConnection::GetContext
- AFXINET/CInternetConnection::GetServerName
- AFXINET/CInternetConnection::GetSession
helpviewer_keywords:
- CInternetConnection [MFC], CInternetConnection
- CInternetConnection [MFC], GetContext
- CInternetConnection [MFC], GetServerName
- CInternetConnection [MFC], GetSession
ms.assetid: 62a5d1c3-8471-4e36-a064-48831829b2a7
ms.openlocfilehash: 2ae869e8cbf3bbfb3ce19e78088a465ae1d6aa65
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97143541"
---
# <a name="cinternetconnection-class"></a>CInternetConnection 类

管理与 Internet 服务器的连接。

## <a name="syntax"></a>语法

```
class CInternetConnection : public CObject
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CInternetConnection：： CInternetConnection](#cinternetconnection)|构造 `CInternetConnection` 对象。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CInternetConnection：： GetContext](#getcontext)|获取此连接对象的上下文 ID。|
|[CInternetConnection：： GetServerName](#getservername)|获取与连接关联的服务器的名称。|
|[CInternetConnection：： GetSession](#getsession)|获取一个指针，该指针指向与连接相关联的 [CInternetSession](../../mfc/reference/cinternetsession-class.md) 对象。|

### <a name="public-operators"></a>公共运算符

|名称|描述|
|----------|-----------------|
|[CInternetConnection：： operator HINTERNET](#operator_hinternet)|Internet 会话的句柄。|

## <a name="remarks"></a>备注

它是 MFC 类 [CFtpConnection](../../mfc/reference/cftpconnection-class.md)、 [CHttpConnection](../../mfc/reference/chttpconnection-class.md)和 [CGopherConnection](../../mfc/reference/cgopherconnection-class.md)的基类。 其中每个类都提供附加功能，用于与相应的 FTP、HTTP 或 gopher 服务器进行通信。

若要与 Internet 服务器直接通信，必须有一个 [CInternetSession](../../mfc/reference/cinternetsession-class.md) 对象和一个 `CInternetConnection` 对象。

若要详细了解 WinInet 类的工作方式，请参阅文章 [使用 WinInet 进行 Internet 编程](../../mfc/win32-internet-extensions-wininet.md)。

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

`CInternetConnection`

## <a name="requirements"></a>要求

**标头：** afxinet。h

## <a name="cinternetconnectioncinternetconnection"></a><a name="cinternetconnection"></a> CInternetConnection：： CInternetConnection

当创建对象时，将调用此成员函数 `CInternetConnection` 。

```
CInternetConnection(
    CInternetSession* pSession,
    LPCTSTR pstrServer,
    INTERNET_PORT nPort = INTERNET_INVALID_PORT_NUMBER,
    DWORD_PTR dwContext = 1);
```

### <a name="parameters"></a>parameters

*pSession*<br/>
指向 [CInternetSession](../../mfc/reference/cinternetsession-class.md) 对象的指针。

*pstrServer*<br/>
指向包含服务器名称的字符串的指针。

*nPort*<br/>
标识此连接的 Internet 端口的编号。

*dwContext*<br/>
对象的上下文标识符 `CInternetConnection` 。 有关 *dwContext* 的详细信息，请参阅 "**备注**"。

### <a name="remarks"></a>备注

永远不会 `CInternetConnection` 自行调用，而应为要建立的连接类型调用 [CInternetSession](../../mfc/reference/cinternetsession-class.md) 成员函数：

- [CInternetSession：： GetFtpConnection](../../mfc/reference/cinternetsession-class.md#getftpconnection)

- [CInternetSession：： GetHttpConnection](../../mfc/reference/cinternetsession-class.md#gethttpconnection)

- [CInternetSession：： GetGopherConnection](../../mfc/reference/cinternetsession-class.md#getgopherconnection)

*DwContext* 的默认值由 MFC 发送到 `CInternetConnection` 从创建 **InternetConnection** 派生对象的 [CInternetSession](../../mfc/reference/cinternetsession-class.md)对象派生的对象。 默认值设置为 1;但是，可以在连接的 [CInternetSession](../../mfc/reference/cinternetsession-class.md#cinternetsession) 构造函数中显式分配特定上下文标识符。 对象及其执行的所有工作都将与该上下文 ID 相关联。 上下文标识符返回到 [CInternetSession：： OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) ，以在标识它的对象上提供状态。 有关上下文标识符的详细信息，请参阅文章 [Internet 优先步骤： WinInet](../../mfc/wininet-basics.md) 。

## <a name="cinternetconnectiongetcontext"></a><a name="getcontext"></a> CInternetConnection：： GetContext

调用此成员函数以获取此会话的上下文 ID。

```
DWORD_PTR GetContext() const;
```

### <a name="return-value"></a>返回值

应用程序分配的上下文 ID。

### <a name="remarks"></a>备注

上下文 ID 最初在 [CInternetSession](../../mfc/reference/cinternetsession-class.md) 中指定，传播到 `CInternetConnection` 和 [CInternetFile](../../mfc/reference/cinternetfile-class.md)派生的类，除非在对打开连接的函数的调用中指定了不同的。 上下文 ID 与给定对象的任何操作相关联，并标识由 [CInternetSession：： OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback)返回的操作的状态信息。

有关如何 `GetContext` 与其他 WinInet 类结合使用来提供用户状态信息的详细信息，请参阅文章 [Internet 优先步骤： WinInet](../../mfc/wininet-basics.md) 了解有关上下文标识符的详细信息。

## <a name="cinternetconnectiongetservername"></a><a name="getservername"></a> CInternetConnection：： GetServerName

调用此成员函数可获取与此 Internet 连接关联的服务器的名称。

```
CString GetServerName() const;
```

### <a name="return-value"></a>返回值

此连接对象正在使用的服务器的名称。

## <a name="cinternetconnectiongetsession"></a><a name="getsession"></a> CInternetConnection：： GetSession

调用此成员函数以获取指向 `CInternetSession` 与此连接关联的对象的指针。

```
CInternetSession* GetSession() const;
```

### <a name="return-value"></a>返回值

指向与此 Internet 连接对象关联的 [CInternetSession](../../mfc/reference/cinternetsession-class.md) 对象的指针。

## <a name="cinternetconnectionoperator-hinternet"></a><a name="operator_hinternet"></a> CInternetConnection：： operator HINTERNET

使用此运算符可获取当前 Internet 会话的 API 级别句柄。

```
operator HINTERNET() const;
```

## <a name="see-also"></a>请参阅

[CObject 类](../../mfc/reference/cobject-class.md)<br/>
[层次结构图](../../mfc/hierarchy-chart.md)
