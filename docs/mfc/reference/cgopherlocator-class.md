---
description: 了解详细信息： CGopherLocator 类
title: CGopherLocator 类
ms.date: 11/04/2016
f1_keywords:
- CGopherLocator
- AFXINET/CGopherLocator
- AFXINET/CGopherLocator::CGopherLocator
- AFXINET/CGopherLocator::GetLocatorType
helpviewer_keywords:
- CGopherLocator [MFC], CGopherLocator
- CGopherLocator [MFC], GetLocatorType
ms.assetid: 6fcc015f-5ae6-4959-b936-858634c71019
ms.openlocfilehash: f615ce6fbda150d923f6664acff207fdebdbba3f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97184018"
---
# <a name="cgopherlocator-class"></a>CGopherLocator 类

从 gopher 服务器获取 gopher "定位器"，确定定位器的类型，并使定位器可用于 [CGopherFileFind](../../mfc/reference/cgopherfilefind-class.md)。

> [!NOTE]
> 类 `CGopherConnection` 、 `CGopherFile` 、 `CGopherFileFind` `CGopherLocator` 和其成员已被弃用，因为它们不能在 Windows XP 平台上运行，但它们将继续在早期的平台上工作。

## <a name="syntax"></a>语法

```
class CGopherLocator : public CObject
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CGopherLocator::CGopherLocator](#cgopherlocator)|构造 `CGopherLocator` 对象。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CGopherLocator::GetLocatorType](#getlocatortype)|分析 gopher 定位符并确定其属性。|

### <a name="public-operators"></a>公共运算符

|名称|描述|
|----------|-----------------|
|[CGopherLocator：： operator LPCTSTR](#operator_lpctstr)|直接访问存储在对象中的字符 `CGopherLocator` 作为 C 样式字符串。|

## <a name="remarks"></a>备注

应用程序必须先获取 gopher 服务器的定位器，然后才能从该服务器中检索信息。 一旦包含定位符，它就必须将定位符视为不透明标记。

每个 gopher 定位符都具有确定找到的文件或服务器的类型的属性。 有关 gopher 定位符类型的列表，请参阅 [GetLocatorType](#getlocatortype) 。

应用程序通常使用定位符对 [CGopherFileFind：： FindFile](../../mfc/reference/cgopherfilefind-class.md#findfile) 的调用来检索特定的信息片段。

若要了解有关如何 `CGopherLocator` 使用其他 MFC Internet 类的详细信息，请参阅文章 [使用 WinInet 进行 Internet 编程](../../mfc/win32-internet-extensions-wininet.md)。

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

`CGopherLocator`

## <a name="requirements"></a>要求

**标头：** afxinet。h

## <a name="cgopherlocatorcgopherlocator"></a><a name="cgopherlocator"></a> CGopherLocator::CGopherLocator

调用此成员函数来创建 `CGopherLocator` 对象。

```
CGopherLocator(const CGopherLocator& ref);
```

### <a name="parameters"></a>参数

*ref*<br/>
对常量对象的引用 `CGopherLocator` 。

### <a name="remarks"></a>备注

永远不会 `CGopherLocator` 直接创建对象。 改为调用 [CGopherConnection：： CreateLocator](../../mfc/reference/cgopherconnection-class.md#createlocator) 以创建并返回指向对象的指针 `CGopherLocator` 。

## <a name="cgopherlocatorgetlocatortype"></a><a name="getlocatortype"></a> CGopherLocator::GetLocatorType

调用此成员函数以获取定位符类型。

```
BOOL GetLocatorType(DWORD& dwRef) const;
```

### <a name="parameters"></a>parameters

*dwRef*<br/>
对将接收定位符类型的 DWORD 值的引用。 有关定位器类型的表，请参阅 " **备注** "。

### <a name="return-value"></a>返回值

如果成功，则不为 0；否则为 0。 如果调用失败，则可以调用 Win32 函数 [GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) 来确定错误的原因。

### <a name="remarks"></a>备注

可能的类型如下：

|值|含义|
|-----------|-------------|
|GOPHER_TYPE_TEXT_FILE|ASCII 文本文件。|
|GOPHER_TYPE_DIRECTORY|附加 Gopher 项的目录。|
|GOPHER_TYPE_CSO|CSO 电话薄服务器。|
|GOPHER_TYPE_ERROR|指示错误条件。|
|GOPHER_TYPE_MAC_BINHEX|采用 BINHEX 格式的 Macintosh 文件。|
|GOPHER_TYPE_DOS_ARCHIVE|DOS 存档文件。|
|GOPHER_TYPE_UNIX_UUENCODED|UUENCODE 文件。|
|GOPHER_TYPE_INDEX_SERVER|索引服务器。|
|GOPHER_TYPE_TELNET|Telnet 服务器。|
|GOPHER_TYPE_BINARY|二进制文件。|
|GOPHER_TYPE_REDUNDANT|重复的服务器。 中包含的信息是主服务器的副本。 主服务器是没有 GOPHER_TYPE_REDUNDANT 类型的最后一个目录条目。|
|GOPHER_TYPE_TN3270|TN3270 服务器。|
|GOPHER_TYPE_GIF|GIF 图形文件。|
|GOPHER_TYPE_IMAGE|映像文件。|
|GOPHER_TYPE_BITMAP|位图文件。|
|GOPHER_TYPE_MOVIE|电影文件。|
|GOPHER_TYPE_SOUND|声音文件。|
|GOPHER_TYPE_HTML|一个 HTML 文档。|
|GOPHER_TYPE_PDF|PDF 文件。|
|GOPHER_TYPE_CALENDAR|日历文件。|
|GOPHER_TYPE_INLINE|内联文件。|
|GOPHER_TYPE_UNKNOWN|项类型未知。|
|GOPHER_TYPE_ASK|Ask + 项。|
|GOPHER_TYPE_GOPHER_PLUS|Gopher + 项。|

## <a name="cgopherlocatoroperator-lpctstr"></a><a name="operator_lpctstr"></a> CGopherLocator：： operator LPCTSTR

此有用的转换运算符提供了一种有效的方法来访问对象中包含的以 null 结尾的 C 字符串 `CGopherLocator` 。

```
operator LPCTSTR () const;
```

### <a name="return-value"></a>返回值

指向字符串数据的字符指针。

### <a name="remarks"></a>备注

不复制任何字符;仅返回指针。

## <a name="see-also"></a>请参阅

[CObject 类](../../mfc/reference/cobject-class.md)<br/>
[层次结构图](../../mfc/hierarchy-chart.md)<br/>
[CGopherFileFind 类](../../mfc/reference/cgopherfilefind-class.md)
