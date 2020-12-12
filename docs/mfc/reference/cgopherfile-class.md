---
description: 了解详细信息： CGopherFile 类
title: CGopherFile 类
ms.date: 11/04/2016
f1_keywords:
- CGopherFile
- AFXINET/CGopherFile
- AFXINET/CGopherFile::CGopherFile
helpviewer_keywords:
- CGopherFile [MFC], CGopherFile
ms.assetid: 3ca9898f-8cdb-4495-bbde-46d40100feda
ms.openlocfilehash: 8f511bdaf3ae6417972ea19465c0392832a2b408
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97184070"
---
# <a name="cgopherfile-class"></a>CGopherFile 类

提供查找和读取 Gopher 服务器上文件的功能。

> [!NOTE]
> 类 `CGopherConnection` 、 `CGopherFile` 、 `CGopherFileFind` `CGopherLocator` 和其成员已被弃用，因为它们不能在 Windows XP 平台上运行，但它们将继续在早期的平台上工作。

## <a name="syntax"></a>语法

```
class CGopherFile : public CInternetFile
```

## <a name="members"></a>成员

### <a name="protected-constructors"></a>受保护的构造函数

|名称|描述|
|----------|-----------------|
|[CGopherFile：： CGopherFile](#cgopherfile)|构造 `CGopherFile` 对象。|

## <a name="remarks"></a>备注

Gopher 服务不允许用户将数据写入 gopher 文件，因为此服务主要用作用于查找信息的菜单驱动接口。 `CGopherFile`成员函数 `Write` 、 `WriteString` 和 `Flush` 不是针对实现的 `CGopherFile` 。 在对象上调用这些函数 `CGopherFile` 将返回 [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md)。

若要了解有关如何 `CGopherFile` 使用其他 MFC Internet 类的详细信息，请参阅文章 [使用 WinInet 进行 Internet 编程](../../mfc/win32-internet-extensions-wininet.md)。

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

[CFile](../../mfc/reference/cfile-class.md)

[CStdioFile](../../mfc/reference/cstdiofile-class.md)

[CInternetFile](../../mfc/reference/cinternetfile-class.md)

`CGopherFile`

## <a name="requirements"></a>要求

**标头：** afxinet。h

## <a name="cgopherfilecgopherfile"></a><a name="cgopherfile"></a> CGopherFile：： CGopherFile

调用此成员函数来构造 `CGopherFile` 对象。

```
CGopherFile(
    HINTERNET hFile,
    CGopherLocator& refLocator,
    CGopherConnection* pConnection);

CGopherFile(
    HINTERNET hFile,
    HINTERNET hSession,
    LPCTSTR pstrLocator,
    DWORD dwLocLen,
    DWORD_PTR dwContext);
```

### <a name="parameters"></a>parameters

*hFile*<br/>
HINTERNET 文件的句柄。

*refLocator*<br/>
对 [CGopherLocator](../../mfc/reference/cgopherlocator-class.md) 对象的引用。

*pConnection*<br/>
指向 [CGopherConnection](../../mfc/reference/cgopherconnection-class.md) 对象的指针。

*hSession*<br/>
当前 Internet 会话的句柄。

*pstrLocator*<br/>
指向用于定位 gopher 服务器的字符串的指针。 有关 gopher 定位符的详细信息，请参阅 [Gopher 会话](cgopherlocator-class.md) 。

*dwLocLen*<br/>
包含 *pstrLocator* 中的字节数的 DWORD。

*dwContext*<br/>
指向正在打开的文件的上下文标识符的指针。

### <a name="remarks"></a>备注

在 `CGopherFile` Gopher Internet 会话过程中，需要对象从文件中读取。

永远不会 `CGopherFile` 直接创建对象。 请改为调用 [CGopherConnection：： OpenFile](../../mfc/reference/cgopherconnection-class.md#openfile) 以打开 gopher 服务器上的文件。

## <a name="see-also"></a>请参阅

[CInternetFile 类](../../mfc/reference/cinternetfile-class.md)<br/>
[层次结构图](../../mfc/hierarchy-chart.md)<br/>
[CInternetFile 类](../../mfc/reference/cinternetfile-class.md)<br/>
[CGopherLocator 类](../../mfc/reference/cgopherlocator-class.md)<br/>
[CGopherFileFind 类](../../mfc/reference/cgopherfilefind-class.md)<br/>
[CGopherConnection 类](../../mfc/reference/cgopherconnection-class.md)
