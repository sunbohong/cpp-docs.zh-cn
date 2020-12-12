---
description: 了解详细信息：日期和时间
title: 日期和时间
ms.date: 08/13/2019
helpviewer_keywords:
- time, MFC programming
- time
- MFC, date and time
- dates, MFC
ms.assetid: ecf56dc5-d418-4603-ad3e-af7e205a6403
ms.openlocfilehash: 4a8f2d5c9537f07c5d410361e79bf14a12778bc8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97167027"
---
# <a name="date-and-time"></a>日期和时间

MFC 支持多种不同的日期和时间处理方式：

- 支持自动化 [日期数据类型](../atl-mfc-shared/date-type.md)。 日期支持日期、时间和日期/时间值。 [COleDateTime](../atl-mfc-shared/reference/coledatetime-class.md)和[COleDateTimeSpan](../atl-mfc-shared/reference/coledatetimespan-class.md)类封装了此功能。 它们使用自动化支持处理 [COleVariant](../mfc/reference/colevariant-class.md) 类。

- 通用时间类。 [CTime](../atl-mfc-shared/reference/ctime-class.md)和[CTimeSpan](../atl-mfc-shared/reference/ctimespan-class.md)类封装了与 ANSI 标准时间库相关联的大部分功能，后者在时间 .h 中声明。

- 对系统时钟的支持。 对于 MFC 版本3.0，为 `CTime` Win32 `SYSTEMTIME` 和数据类型添加了对的支持 `FILETIME` 。

## <a name="date-and-time-automation-support"></a>日期和时间：自动化支持

[COleDateTime](../atl-mfc-shared/reference/coledatetime-class.md)类提供了一种方法来表示日期和时间信息。 它提供更精细的粒度和比 [CTime](../atl-mfc-shared/reference/ctime-class.md) 类更大的范围。 [COleDateTimeSpan](../atl-mfc-shared/reference/coledatetimespan-class.md)类表示运行时间，如两个对象之间的差异 `COleDateTime` 。

`COleDateTime`和 `COleDateTimeSpan` 类旨在与类一起使用 `COleVariant` 。 `COleDateTime` 和 `COleDateTimeSpan` 在 MFC 数据库编程中也很有用，但只要您想要处理日期和时间值，就可以使用这些值。 尽管 `COleDateTime` 类的值范围比类更大，但其取值范围比类更精确 `CTime` ，但它需要每个对象的存储空间超过 `CTime` 。 使用基础日期类型时，还需要注意一些特殊事项。 有关日期实现的详细信息，请参阅 [日期类型](../atl-mfc-shared/date-type.md)。

`COleDateTime` 对象可用于表示100年1月1日到9999年12月31日之间的日期。 `COleDateTime` 对象是浮点值，近似分辨率为1毫秒。 `COleDateTime` 基于日期数据类型，该数据类型在 MFC 文档中的 [COleDateTime：： OPERATOR DATE](../atl-mfc-shared/reference/coledatetime-class.md#operator_date)下定义。 日期的实际实现超出了这些界限。 `COleDateTime`实现需要使用这些界限来更轻松地使用类。

`COleDateTime` 不支持儒略历日期。 假定公历时间向后扩展到100年1月1日。

`COleDateTime` 忽略夏令时 (DST) 。 下面的代码示例比较两个计算时间跨度的方法，这些方法用于计算与 DST 切换日期相同的时间跨度：一个使用 CRT，另一个使用 `COleDateTime` 。

第一种方法 `CTime` 使用标准 C 类型结构和将两个对象 *time1* 和 *Time2* 分别设置为4月5日和4月6日 `tm` `time_t` 。 此代码显示 *time1* 和 *time2* 以及它们之间的时间跨度。

第二个方法创建两个 `COleDateTime` 对象， `oletime1` 并 `oletime2` 将它们设置为 *time1* 和 *time2* 的相同日期。 它显示 `oletime1` 和 `oletime2` 和它们之间的时间跨度。

CRT 正确计算23小时的差异。 `COleDateTimeSpan` 计算24小时的差异。

[!code-cpp[NVC_ATLMFC_Utilities#176](../atl-mfc-shared/codesnippet/cpp/date-and-time-automation-support_1.cpp)]

### <a name="get-the-current-time"></a>获取当前时间

下面的过程演示如何创建 `COleDateTime` 对象并使用当前时间对其进行初始化。

#### <a name="to-get-the-current-time"></a>获取当前时间

1. 创建 `COleDateTime` 对象。

1. 调用 `GetCurrentTime`。

   [!code-cpp[NVC_ATLMFC_Utilities#177](../atl-mfc-shared/codesnippet/cpp/current-time-automation-classes_1.cpp)]

### <a name="calculate-elapsed-time"></a>计算运行时间

此过程说明如何计算两个对象之间的差异 `COleDateTime` 并获得 `COleDateTimeSpan` 结果。

#### <a name="to-calculate-elapsed-time"></a>计算运行时间

1. 创建两个 `COleDateTime` 对象。

1. 将其中一个 `COleDateTime` 对象设置为当前时间。

1. 执行一些耗时的任务。

1. 将另一个 `COleDateTime` 对象设置为当前时间。

1. 采用两个时间之间的差异。

   [!code-cpp[NVC_ATLMFC_Utilities#178](../atl-mfc-shared/codesnippet/cpp/elapsed-time-automation-classes_1.cpp)]

### <a name="format-a-time"></a>格式化时间

#### <a name="to-format-a-time"></a>格式化时间

使用 `Format` [COleDateTime](../atl-mfc-shared/reference/coledatetime-class.md) 或 [COleDateTimeSpan](../atl-mfc-shared/reference/coledatetimespan-class.md) 的成员函数创建表示时间或运行时间的字符串。

   [!code-cpp[NVC_ATLMFC_Utilities#179](../atl-mfc-shared/codesnippet/cpp/formatting-time-automation-classes_1.cpp)]

有关详细信息，请参阅类 [COleVariant](../mfc/reference/colevariant-class.md)。

## <a name="date-and-time-database-support"></a>日期和时间：数据库支持

从4.0 版开始，MFC 数据库编程使用 [COleDateTime](../atl-mfc-shared/reference/coledatetime-class.md) 和 [COleDateTimeSpan](../atl-mfc-shared/reference/coledatetimespan-class.md) 类来表示日期和时间数据。 这些类（也在自动化中使用）派生自类 [COleVariant](../mfc/reference/colevariant-class.md)。 它们为管理日期和时间数据提供比完成 [CTime](../atl-mfc-shared/reference/ctime-class.md) 和 [CTimeSpan](../atl-mfc-shared/reference/ctimespan-class.md)更好的支持。

## <a name="date-and-time-systemtime-support"></a>日期和时间：SYSTEMTIME 支持

[COleDateTime](../atl-mfc-shared/reference/coledatetime-class.md)类具有接受来自 Win32 的系统和文件时间的构造函数。

Win32 `FILETIME` 结构将时间表示为64位值。 这种格式比结构更方便 `SYSTEMTIME` ，而 Win32 使用的格式表示创建文件的时间。 有关 SYSTEMTIME 结构的信息，请参阅 [SYSTEMTIME](/windows/desktop/api/minwinbase/ns-minwinbase-systemtime)。 有关 FILETIME 结构的信息，请参阅 [filetime](/windows/desktop/api/minwinbase/ns-minwinbase-filetime)。

## <a name="see-also"></a>请参阅

[之上](../mfc/mfc-concepts.md)\
[常规 MFC 主题](../mfc/general-mfc-topics.md)
