---
description: 了解详细信息：在日期和时间选取器控件中使用自定义格式字符串
title: 在日期和时间选取器控件中使用自定义格式字符串
ms.date: 11/04/2016
helpviewer_keywords:
- CDateTimeCtrl class [MFC], display styles
- DateTimePicker control [MFC], display styles
- DateTimePicker control [MFC]
ms.assetid: 7d577f03-6ca0-4597-9093-50b78f304719
ms.openlocfilehash: 91add199ffd852a107588617d47a2fd51136596d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97154547"
---
# <a name="using-custom-format-strings-in-a-date-and-time-picker-control"></a>在日期和时间选取器控件中使用自定义格式字符串

默认情况下，日期和时间选取器控件提供了 3 种格式（每种格式对应于一个唯一样式）来显示当前日期或时间：

- **DTS_LONGDATEFORMAT** 以长格式显示日期，生成类似于 "星期三，2000年1月3日的输出"。

- **DTS_SHORTDATEFORMAT** 以短格式显示日期，生成类似于 "1/3/00" 的输出。

- **DTS_TIMEFORMAT** 以长格式显示时间，生成类似于 "5:31:42 PM" 的输出。

但是，您可通过使用自定义格式字符串来自定义日期或时间的外观。 此自定义字符串组成现有格式字符、无格式字符或二者的组合。 生成自定义字符串后，调用 [CDateTimeCtrl：： SetFormat](../mfc/reference/cdatetimectrl-class.md#setformat) 并传入自定义字符串。 日期和时间选取器控件之后将使用您的自定义格式字符串显示当前值。

下面的示例代码 (，其中 *m_dtPicker* 是 `CDateTimeCtrl` 对象) 演示了一个可能的解决方案：

[!code-cpp[NVC_MFCControlLadenDialog#7](../mfc/codesnippet/cpp/using-custom-format-strings-in-a-date-and-time-picker-control_1.cpp)]

除了自定义格式字符串以外，日期和时间选取器控件还支持 [回调字段](../mfc/using-callback-fields-in-a-date-and-time-picker-control.md)。

## <a name="see-also"></a>请参阅

[使用 CDateTimeCtrl](../mfc/using-cdatetimectrl.md)<br/>
[控件](../mfc/controls-mfc.md)
