---
description: 了解详细信息：异常类
title: 异常类
ms.date: 11/04/2016
f1_keywords:
- vc.classes.exception
helpviewer_keywords:
- exception classes [MFC]
- exception handling [MFC], exception classes
- MFC, exceptions
ms.assetid: 1a2caf12-b3e9-4189-86d2-bf7a595bf025
ms.openlocfilehash: c07bd93a0abf95dc7d5f46c710faaad2dcad08c0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97290760"
---
# <a name="exception-classes"></a>异常类

类库提供基于类 `CException` 的异常处理机制。 应用程序框架将在其代码中使用异常；你也可在你自己的代码中使用异常。 有关详细信息，请参阅文章 [异常](exception-handling-in-mfc.md)。 您可从 `CException` 派生自己的异常类型。

MFC 提供了您可从其派生自己的异常的异常类以及其支持的所有异常的异常类。

[CException](reference/cexception-class.md)<br/>
异常的基类。

[CArchiveException](reference/carchiveexception-class.md)<br/>
存档异常。

[CDaoException](reference/cdaoexception-class.md)<br/>
DAO 数据库操作失败导致的异常。

[CDBException](reference/cdbexception-class.md)<br/>
ODBC 数据库处理失败导致的异常。

[CFileException](reference/cfileexception-class.md)<br/>
面向文件的异常。

[CMemoryException](reference/cmemoryexception-class.md)<br/>
内存不足异常。

[CNotSupportedException](reference/cnotsupportedexception-class.md)<br/>
使用不支持的功能导致的异常。

[COleException](reference/coleexception-class.md)<br/>
OLE 处理失败导致的异常。 此类将由容器和服务器使用。

[COleDispatchException](reference/coledispatchexception-class.md)<br/>
自动化期间出错导致的异常。 自动化异常由自动化服务器引发，由自动化客户端捕获。

[CResourceException](reference/cresourceexception-class.md)<br/>
Windows 资源加载失败导致的异常。

[CUserException](reference/cuserexception-class.md)<br/>
用于停止用户启动的操作的异常。 通常，用户在此异常引发前已收到有关问题的通知。

## <a name="see-also"></a>请参阅

[类概述](class-library-overview.md)
