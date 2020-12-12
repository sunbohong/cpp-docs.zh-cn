---
description: 了解更多： MFC 和 ATL 共享的类
title: MFC 和 ATL 共享的类
ms.date: 11/04/2016
helpviewer_keywords:
- shared classes, classes
ms.assetid: ca8b4b6b-744d-430b-b31f-d5b2f17bf210
ms.openlocfilehash: df196f92b7b16742545a7d82320ef4fe8da77fe2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97166780"
---
# <a name="classes-shared-by-mfc-and-atl"></a>MFC 和 ATL 共享的类

下表列出了 MFC 与 ATL 之间共享的类。

|类|描述|头文件|
|-----------|-----------------|-----------------|
|[CFileTime](../../atl-mfc-shared/reference/cfiletime-class.md)|提供用于管理与文件关联的日期和时间值的方法。|atltime|
|[CFileTimeSpan](../../atl-mfc-shared/reference/cfiletimespan-class.md)|提供用于管理与文件关联的相对日期和时间值的方法。|atltime|
|[CFixedStringT](../../atl-mfc-shared/reference/cfixedstringt-class.md)|表示具有固定字符缓冲区的字符串对象。|cstringt|
|[CImage](../../atl-mfc-shared/reference/cimage-class.md)|提供增强的位图支持，其中包括将图像加载并保存到 JPEG、GIF、BMP 和可移植网络图形 (PNG) 格式的功能。|atlimage|
|[COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md)|封装 OLE 自动化中使用的日期数据类型。|atlcomtime。h|
|[COleDateTimeSpan](../../atl-mfc-shared/reference/coledatetimespan-class.md)|表示一个相对时间，时间跨度。|atlcomtime。h|
|[CPoint](../../atl-mfc-shared/reference/cpoint-class.md)|类似于 Windows [点](/windows/win32/api/windef/ns-windef-point) 结构的类，该结构还包含用于操作和结构的成员函数 `CPoint` `POINT` 。|atltypes|
|[CRect](../../atl-mfc-shared/reference/crect-class.md)|类似于 Windows [RECT](/windows/win32/api/windef/ns-windef-rect) 结构的类，该结构还包含用于操作 `CRect` 对象和 Windows 结构的成员函数 `RECT` 。|atltypes|
|[CSimpleStringT](../../atl-mfc-shared/reference/csimplestringt-class.md)|表示 `CSimpleStringT` 对象。|atlsimpstr|
|[CSize](../../atl-mfc-shared/reference/csize-class.md)|类似于 Windows [SIZE](/windows/win32/api/windef/ns-windef-size) 结构的类，它实现一个相对坐标或位置。|atltypes|
|[CStrBufT](../../atl-mfc-shared/reference/cstrbuft-class.md)|为 `GetBuffer` 现有对象提供和调用的自动资源清理 `ReleaseBuffer` `CStringT` 。|atlsimpstr|
|[CStringData](../../atl-mfc-shared/reference/cstringdata-class.md)|表示字符串对象的数据。|atlsimpstr|
|[CStringT](../../atl-mfc-shared/reference/cstringt-class.md)|表示 `CStringT` 对象。|cstringt (MFC 依赖) atlstr.h (MFC 无关) |
|[CTime](../../atl-mfc-shared/reference/ctime-class.md)|表示绝对时间和日期。|atltime|
|[CTimeSpan](../../atl-mfc-shared/reference/ctimespan-class.md)|时间长度，在内部存储为时间跨度中的秒数。|atltime|
|[IAtlStringMgr](../../atl-mfc-shared/reference/iatlstringmgr-class.md)|表示 `CStringT` 内存管理器的接口。|atlsimpstr|

## <a name="see-also"></a>请参阅

[ATL/MFC 共享类](../../atl-mfc-shared/atl-mfc-shared-classes.md)
