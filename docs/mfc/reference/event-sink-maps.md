---
description: 了解详细信息：事件接收器映射
title: 事件接收器映射
ms.date: 11/04/2016
helpviewer_keywords:
- event sink maps [MFC]
ms.assetid: a9757eb2-5f4a-45ec-a2cd-ce5eec85b16f
ms.openlocfilehash: df18cdbba849ff0c8d7be5b038f997b6cc5df849
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97219832"
---
# <a name="event-sink-maps"></a>事件接收器映射

当嵌入 OLE 控件触发事件时，控件的容器将使用 MFC 提供的名为“事件接收器映射”的机制接收事件。 此事件接收器映射为每个特定事件指定处理程序函数，以及这些事件的参数。 有关事件接收器映射的详细信息，请参阅文章 [ActiveX 控件容器](../../mfc/activex-control-containers.md)。

### <a name="event-sink-maps"></a>事件接收器映射

|名称|描述|
|-|-|
|[BEGIN_EVENTSINK_MAP](#begin_eventsink_map)|启动事件接收器映射的定义。|
|[DECLARE_EVENTSINK_MAP](#declare_eventsink_map)|声明事件接收器映射。|
|[END_EVENTSINK_MAP](#end_eventsink_map)|结束事件接收器映射的定义。|
|[ON_EVENT](#on_event)|为特定事件定义事件处理程序。|
|[ON_EVENT_RANGE](#on_event_range)|为一组 OLE 控件触发的特定事件定义事件处理程序。|
|[ON_EVENT_REFLECT](#on_event_reflect)|在控件的容器处理控件触发的事件之前接收这些事件。|
|[ON_PROPNOTIFY](#on_propnotify)|定义处理程序来处理来自 OLE 控件的属性通知。|
|[ON_PROPNOTIFY_RANGE](#on_propnotify_range)|定义处理程序来处理来自一组 OLE 控件的属性通知。|
|[ON_PROPNOTIFY_REFLECT](#on_propnotify_reflect)|在控件的容器处理控件发送的属性通知之前接收这些通知。|

## <a name="begin_eventsink_map"></a><a name="begin_eventsink_map"></a> BEGIN_EVENTSINK_MAP

开始事件接收器映射的定义。

```
BEGIN_EVENTSINK_MAP(theClass, baseClass)
```

### <a name="parameters"></a>parameters

*类*<br/>
指定其事件接收器映射的控件类的名称。

*baseClass*<br/>
指定 *类* 的基类的名称。

### <a name="remarks"></a>备注

在实现 ( 为类定义成员函数) 文件中，用 BEGIN_EVENTSINK_MAP 宏启动事件接收器映射，然后为要通知的每个事件添加宏条目，并通过 END_EVENTSINK_MAP 宏完成事件接收器映射。

有关事件接收器映射和 OLE 控件容器的详细信息，请参阅文章 [ActiveX 控件容器](../../mfc/activex-control-containers.md)。

### <a name="requirements"></a>要求

  **标头** afxdisp.h&gt

## <a name="declare_eventsink_map"></a><a name="declare_eventsink_map"></a> DECLARE_EVENTSINK_MAP

OLE 容器可提供事件接收器映射来指定通知容器的事件。

```
DECLARE_EVENTSINK_MAP()
```

### <a name="remarks"></a>备注

在类声明的末尾使用 DECLARE_EVENTSINK_MAP 宏。 然后，在中。CPP 文件，用于定义类的成员函数，使用 BEGIN_EVENTSINK_MAP 宏，为要通知的每个事件使用宏项，并使用 END_EVENTSINK_MAP 宏来声明事件接收器列表的末尾。

有关事件接收器映射的详细信息，请参阅文章 [ActiveX 控件容器](../../mfc/activex-control-containers.md)。

### <a name="requirements"></a>要求

  **标头** afxwin。h

## <a name="end_eventsink_map"></a><a name="end_eventsink_map"></a> END_EVENTSINK_MAP

结束事件接收器映射的定义。

```
END_EVENTSINK_MAP()
```

### <a name="requirements"></a>要求

  **标头** afxdisp.h&gt

## <a name="on_event"></a><a name="on_event"></a> ON_EVENT

使用 ON_EVENT 宏为 OLE 控件触发的事件定义事件处理程序函数。

```
ON_EVENT(theClass, id, dispid, pfnHandler,  vtsParams)
```

### <a name="parameters"></a>parameters

*类*<br/>
此事件接收器映射所属的类。

*id*<br/>
OLE 控件的控件 ID。

*dispid*<br/>
控件触发的事件的调度 ID。

*pfnHandler*<br/>
指向处理事件的成员函数的指针。 此函数应具有 BOOL 返回类型，并且与事件的参数匹配的参数类型 (参阅 *vtsParams*) 。 函数应返回 TRUE 以指示事件已处理;否则为 FALSE。

*vtsParams*<br/>
指定事件的参数类型的 **VTS_** 常数的序列。 它们与调度映射项（如 DISP_FUNCTION）中使用的常量相同。

### <a name="remarks"></a>备注

*VtsParams* 参数是一个空格分隔列表，其中列出了 **VTS_** 常量中的值。 这些值中的一个或多个用空格分隔 (不能使用逗号) 指定函数的参数列表。 例如：

[!code-cpp[NVC_MFCAutomation#11](../../mfc/codesnippet/cpp/event-sink-maps_1.cpp)]

指定一个列表，其中包含一个短整型后跟一个 BOOL。

有关 **VTS_** 常量的列表，请参阅 [EVENT_CUSTOM](event-maps.md#event_custom)。

### <a name="requirements"></a>要求

  **标头** afxdisp.h&gt

## <a name="on_event_range"></a><a name="on_event_range"></a> ON_EVENT_RANGE

使用 ON_EVENT_RANGE 宏为某个事件定义事件处理程序函数，该事件由在连续 Id 范围内具有控件 ID 的任何 OLE 控件引发。

```
ON_EVENT_RANGE(theClass, idFirst, idLast, dispid, pfnHandler,  vtsParams)
```

### <a name="parameters"></a>parameters

*类*<br/>
此事件接收器映射所属的类。

*idFirst*<br/>
范围中第一个 OLE 控件的控件 ID。

*idLast*<br/>
范围中最后一个 OLE 控件的控件 ID。

*dispid*<br/>
控件触发的事件的调度 ID。

*pfnHandler*<br/>
指向处理事件的成员函数的指针。 此函数应具有 BOOL 返回类型、 (的控件 ID) 的 UINT 类型的第一个参数和与事件的参数匹配的其他参数类型 (参阅 *vtsParams*) 。 函数应返回 TRUE 以指示事件已处理;否则为 FALSE。

*vtsParams*<br/>
指定事件的参数类型的 **VTS_** 常数的序列。 对于控件 ID，第一个常量应为 VTS_I4 类型。 它们与调度映射项（如 DISP_FUNCTION）中使用的常量相同。

### <a name="remarks"></a>备注

*VtsParams* 参数是一个空格分隔列表，其中列出了 **VTS_** 常量中的值。 这些值中的一个或多个用空格分隔 (不能使用逗号) 指定函数的参数列表。 例如：

[!code-cpp[NVC_MFCAutomation#11](../../mfc/codesnippet/cpp/event-sink-maps_1.cpp)]

指定一个列表，其中包含一个短整型后跟一个 BOOL。

有关 **VTS_** 常量的列表，请参阅 [EVENT_CUSTOM](event-maps.md#event_custom)。

### <a name="example"></a>示例

下面的示例演示了对 IDC_MYCTRL1 通过 IDC_MYCTRL3)  ( 的三个控件实现的事件处理程序。 事件处理程序函数 `OnRangeMouseDown` 在对话框类的标头文件中声明 ( `CMyDlg`) 为：

[!code-cpp[NVC_MFCAutomation#12](../../mfc/codesnippet/cpp/event-sink-maps_2.h)]

下面的代码在对话框类的实现文件中定义。

[!code-cpp[NVC_MFCAutomation#13](../../mfc/codesnippet/cpp/event-sink-maps_3.cpp)]

### <a name="requirements"></a>要求

  **标头** afxdisp.h&gt

## <a name="on_event_reflect"></a><a name="on_event_reflect"></a> ON_EVENT_REFLECT

当在 OLE 控件的包装器类的事件接收器映射中使用时，ON_EVENT_REFLECT 宏会接收由控件的容器处理的事件。

```
ON_EVENT_REFLECT(theClass,  dispid, pfnHandler,  vtsParams)
```

### <a name="parameters"></a>parameters

*类*<br/>
此事件接收器映射所属的类。

*dispid*<br/>
控件触发的事件的调度 ID。

*pfnHandler*<br/>
指向处理事件的成员函数的指针。 此函数应具有与事件的参数匹配的 BOOL 返回类型和参数类型 (请参阅 *vtsParams*) 。 函数应返回 TRUE 以指示事件已处理;否则为 FALSE。

*vtsParams*<br/>
指定事件的参数类型的 **VTS_** 常数的序列。 它们与调度映射项（如 DISP_FUNCTION）中使用的常量相同。

### <a name="remarks"></a>备注

*VtsParams* 参数是一个空格分隔列表，其中列出了 **VTS_** 常量中的值。

这些值中的一个或多个用空格分隔 (不能使用逗号) 指定函数的参数列表。 例如：

[!code-cpp[NVC_MFCAutomation#11](../../mfc/codesnippet/cpp/event-sink-maps_1.cpp)]

指定一个列表，其中包含一个短整型后跟一个 BOOL。

有关 **VTS_** 常量的列表，请参阅 [EVENT_CUSTOM](event-maps.md#event_custom)。

### <a name="requirements"></a>要求

  **标头** afxdisp.h&gt

## <a name="on_propnotify"></a><a name="on_propnotify"></a> ON_PROPNOTIFY

使用 ON_PROPNOTIFY 宏可定义事件接收器映射项，用于处理来自 OLE 控件的属性通知。

```
ON_PROPNOTIFY(theClass, id, dispid, pfnRequest, pfnChanged)
```

### <a name="parameters"></a>parameters

*类*<br/>
此事件接收器映射所属的类。

*id*<br/>
OLE 控件的控件 ID。

*dispid*<br/>
通知中涉及的属性的调度 ID。

*pfnRequest*<br/>
指向成员函数的指针，该成员函数用于处理 `OnRequestEdit` 此属性的通知。 此函数应具有 BOOL 返回类型和 **布尔** <strong>\*</strong> 参数。 此函数应将参数设置为 TRUE，以允许属性更改，并将 FALSE 设置为禁止。 函数应返回 TRUE 以指示已处理通知;否则为 FALSE。

*pfnChanged*<br/>
指向成员函数的指针，该成员函数用于处理 `OnChanged` 此属性的通知。 函数应具有 BOOL 返回类型和 UINT 参数。 函数应返回 TRUE 以指示已处理通知;否则为 FALSE。

### <a name="remarks"></a>备注

*VtsParams* 参数是一个空格分隔列表，其中列出了 **VTS_** 常量中的值。 这些值中的一个或多个用空格分隔 (不能使用逗号) 指定函数的参数列表。 例如：

[!code-cpp[NVC_MFCAutomation#11](../../mfc/codesnippet/cpp/event-sink-maps_1.cpp)]

指定一个列表，其中包含一个短整型后跟一个 BOOL。

有关 **VTS_** 常量的列表，请参阅 [EVENT_CUSTOM](event-maps.md#event_custom)。

## <a name="on_propnotify_range"></a><a name="on_propnotify_range"></a> ON_PROPNOTIFY_RANGE

使用 ON_PROPNOTIFY_RANGE 宏可定义事件接收器映射项，用于处理来自具有连续 Id 范围内的控件 ID 的任何 OLE 控件的属性通知。

```

ON_PROPNOTIFY_RANGE(theClass, idFirst, idLast, dispid, pfnRequest, pfnChanged)
```

### <a name="parameters"></a>parameters

*类*<br/>
此事件接收器映射所属的类。

*idFirst*<br/>
范围中第一个 OLE 控件的控件 ID。

*idLast*<br/>
范围中最后一个 OLE 控件的控件 ID。

*dispid*<br/>
通知中涉及的属性的调度 ID。

*pfnRequest*<br/>
指向成员函数的指针，该成员函数用于处理 `OnRequestEdit` 此属性的通知。 此函数应具有 `BOOL` 返回类型和 `UINT` 和 `BOOL*` 参数。 函数应将参数设置为 TRUE，以允许属性更改，并将 FALSE 设置为禁止。 函数应返回 TRUE 以指示已处理通知;否则为 FALSE。

*pfnChanged*<br/>
指向成员函数的指针，该成员函数用于处理 `OnChanged` 此属性的通知。 函数应具有 `BOOL` 返回类型和 `UINT` 参数。 函数应返回 TRUE 以指示已处理通知;否则为 FALSE。

### <a name="requirements"></a>要求

  **标头** afxdisp.h&gt

## <a name="on_propnotify_reflect"></a><a name="on_propnotify_reflect"></a> ON_PROPNOTIFY_REFLECT

当在 OLE 控件的包装器类的事件接收器映射中使用时，ON_PROPNOTIFY_REFLECT 宏会接收由控件的容器处理控件之前发送的属性通知。

```

ON_PROPNOTIFY_REFLECT(theClass, dispid, pfnRequest, pfnChanged)
```

### <a name="parameters"></a>parameters

*类*<br/>
此事件接收器映射所属的类。

*dispid*<br/>
通知中涉及的属性的调度 ID。

*pfnRequest*<br/>
指向成员函数的指针，该成员函数用于处理 `OnRequestEdit` 此属性的通知。 此函数应具有 BOOL 返回类型和 **布尔** <strong>\*</strong> 参数。 此函数应将参数设置为 TRUE，以允许属性更改，并将 FALSE 设置为禁止。 函数应返回 TRUE 以指示已处理通知;否则为 FALSE。

*pfnChanged*<br/>
指向成员函数的指针，该成员函数用于处理 `OnChanged` 此属性的通知。 函数应具有 BOOL 返回类型，并且不包含任何参数。 函数应返回 TRUE 以指示已处理通知;否则为 FALSE。

### <a name="requirements"></a>要求

  **标头** afxdisp.h&gt

## <a name="see-also"></a>请参阅

[MFC 宏和全局函数](../../mfc/reference/mfc-macros-and-globals.md)
