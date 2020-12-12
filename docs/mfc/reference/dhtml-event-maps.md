---
description: 了解详细信息： DHTML 事件映射
title: DHTML 事件映射
ms.date: 11/04/2016
f1_keywords:
- vc.macros.shared
helpviewer_keywords:
- event map macros [MFC]
- DHTML [MFC], event map macros
- macros [MFC], DHTML event map
- DHTML events [MFC], event map
- DHTML events [MFC]
ms.assetid: 9a2c8ae7-7216-4a5e-bc60-6b98695be0c6
ms.openlocfilehash: b9df8f1aa59472de033943efd28f5c688c61e706
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97220118"
---
# <a name="dhtml-event-maps"></a>DHTML 事件映射

以下宏可用于处理 DHTML 事件。

## <a name="dhtml-event-map-macros"></a>DHTML 事件映射宏

以下宏可用于处理 [CDHtmlDialog](../../mfc/reference/cdhtmldialog-class.md)派生类中的 DHTML 事件。

|名称|描述|
|-|-|
|[BEGIN_DHTML_EVENT_MAP](#begin_dhtml_event_map)|标记 DHTML 事件映射的开头。|
|[BEGIN_DHTML_EVENT_MAP_INLINE](#begin_dhtml_event_map_inline)|标记 DHTML 事件映射的开头。|
|[DECLARE_DHTML_EVENT_MAP](#declare_dhtml_event_map)|声明 DHTML 事件映射。|
|[DHTML_EVENT](#dhtml_event)|用于处理单个 HTML 元素的文档级事件。|
|[DHTML_EVENT_AXCONTROL](#dhtml_event_axcontrol)|用于处理由 ActiveX 控件引发的事件。|
|[DHTML_EVENT_CLASS](#dhtml_event_class)|用于在文档级别为具有特定 CSS 类的所有 HTML 元素处理事件。|
|[DHTML_EVENT_ELEMENT](#dhtml_event_element)|用于处理元素级别的事件。|
|[DHTML_EVENT_ONAFTERUPDATE](#dhtml_event_onafterupdate)|用于处理 `onafterupdate` HTML 元素中的事件。|
|[DHTML_EVENT_ONBEFOREUPDATE](#dhtml_event_onbeforeupdate)|用于处理 `onbeforeupdate` HTML 元素中的事件。|
|[DHTML_EVENT_ONBLUR](#dhtml_event_onblur)|用于处理 `onblur` HTML 元素中的事件。|
|[DHTML_EVENT_ONCHANGE](#dhtml_event_onchange)|用于处理 `onchange` HTML 元素中的事件。|
|[DHTML_EVENT_ONCLICK](#dhtml_event_onclick)|用于处理 `onclick` HTML 元素中的事件。|
|[DHTML_EVENT_ONDATAAVAILABLE](#dhtml_event_ondataavailable)|用于处理 `ondataavailable` HTML 元素中的事件。|
|[DHTML_EVENT_ONDATASETCHANGED](#dhtml_event_ondatasetchanged)|用于处理 `ondatasetchanged` HTML 元素中的事件。|
|[DHTML_EVENT_ONDATASETCOMPLETE](#dhtml_event_ondatasetcomplete)|用于处理 `ondatasetcomplete` HTML 元素中的事件。|
|[DHTML_EVENT_ONDBLCLICK](#dhtml_event_ondblclick)|用于处理 `ondblclick` HTML 元素中的事件。|
|[DHTML_EVENT_ONDRAGSTART](#dhtml_event_ondragstart)|用于处理 `ondragstart` HTML 元素中的事件。|
|[DHTML_EVENT_ONERRORUPDATE](#dhtml_event_onerrorupdate)|用于处理 `onerrorupdate` HTML 元素中的事件。|
|[DHTML_EVENT_ONFILTERCHANGE](#dhtml_event_onfilterchange)|用于处理 `onfilterchange` HTML 元素中的事件。|
|[DHTML_EVENT_ONFOCUS](#dhtml_event_onfocus)|用于处理 `onfocus` HTML 元素中的事件。|
|[DHTML_EVENT_ONHELP](#dhtml_event_onhelp)|用于处理 `onhelp` HTML 元素中的事件。|
|[DHTML_EVENT_ONKEYDOWN](#dhtml_event_onkeydown)|用于处理 `onkeydown` HTML 元素中的事件。|
|[DHTML_EVENT_ONKEYPRESS](#dhtml_event_onkeypress)|用于处理 `onkeypress` HTML 元素中的事件。|
|[DHTML_EVENT_ONKEYUP](#dhtml_event_onkeyup)|用于处理 `onkeyup` HTML 元素中的事件。|
|[DHTML_EVENT_ONMOUSEDOWN](#dhtml_event_onmousedown)|用于处理 `onmousedown` HTML 元素中的事件。|
|[DHTML_EVENT_ONMOUSEMOVE](#dhtml_event_onmousemove)|用于处理 `onmousemove` HTML 元素中的事件。|
|[DHTML_EVENT_ONMOUSEOUT](#dhtml_event_onmouseout)|用于处理 `onmouseout` HTML 元素中的事件。|
|[DHTML_EVENT_ONMOUSEOVER](#dhtml_event_onmouseover)|用于处理 `onmouseover` HTML 元素中的事件。|
|[DHTML_EVENT_ONMOUSEUP](#dhtml_event_onmouseup)|用于处理 `onmouseup` HTML 元素中的事件。|
|[DHTML_EVENT_ONRESIZE](#dhtml_event_onresize)|用于处理 `onresize` HTML 元素中的事件。|
|[DHTML_EVENT_ONROWENTER](#dhtml_event_onrowenter)|用于处理 `onrowenter` HTML 元素中的事件。|
|[DHTML_EVENT_ONROWEXIT](#dhtml_event_onrowexit)|用于处理 `onrowexit` HTML 元素中的事件。|
|[DHTML_EVENT_ONSELECTSTART](#dhtml_event_onselectstart)|用于处理 `onselectstart` HTML 元素中的事件。|
|[DHTML_EVENT_TAG](#dhtml_event_tag)|用于在文档级别处理具有特定 HTML 标记的所有元素的事件。|
|[END_DHTML_EVENT_MAP](#end_dhtml_event_map)|标记 DHTML 事件映射的结尾。|
|[END_DHTML_EVENT_MAP_INLINE](#end_dhtml_event_map_inline)|标记 DHTML 事件映射的结尾。 |

## <a name="url-event-map-macros"></a>URL 事件映射宏

以下宏可用于处理 [CMultiPageDHtmlDialog](../../mfc/reference/cmultipagedhtmldialog-class.md)派生类中的 DHTML 事件。

|名称|描述|
|-|-|
|[BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map)|标记多页 DHTML 和 URL 事件映射的开头。|
|[BEGIN_EMBED_DHTML_EVENT_MAP](#begin_embed_dhtml_event_map)|标记嵌入的 DHTML 事件映射的开头。|
|[BEGIN_URL_ENTRIES](#begin_url_entries)|标记 URL 事件项映射的开头。|
|[DECLARE_DHTML_URL_EVENT_MAP](#declare_dhtml_url_event_map)|声明多页 DHTML 和 URL 事件映射。|
|[END_DHTML_URL_EVENT_MAP](#end_dhtml_url_event_map)|标记多页 DHTML 和 URL 事件映射的结尾。|
|[END_EMBED_DHTML_EVENT_MAP](#end_embed_dhtml_event_map)|标记嵌入的 DHTML 事件映射的结尾。|
|[END_URL_ENTRIES](#end_url_entries)|标记 URL 事件项映射的结尾。|
|[URL_EVENT_ENTRY](#url_event_entry)|将 URL 或 HTML 资源映射到多页面对话框中的页面。|

### <a name="requirements"></a>要求

  **标头** afxdhtml

## <a name="begin_dhtml_event_map"></a><a name="begin_dhtml_event_map"></a> BEGIN_DHTML_EVENT_MAP

将 DHTML 事件映射的开头置于由标识的类的源文件中时标记 `className` 。

```cpp
BEGIN_DHTML_EVENT_MAP(className)
```

### <a name="parameters"></a>parameters

*className*<br/>
包含 DHTML 事件映射的类的名称。 此类应直接或间接从 [CDHtmlDialog](../../mfc/reference/cdhtmldialog-class.md) 派生，并在其类定义中包含 [DECLARE_DHTML_EVENT_MAP](#declare_dhtml_event_map) 宏。

### <a name="remarks"></a>备注

将 DHTML 事件映射添加到你的类，以提供可用于将网页 `CDHtmlDialog` 中的 HTML 元素或 ActiveX 控件引发的事件路由到你的类中的处理程序函数的信息。

将 BEGIN_DHTML_EVENT_MAP 宏放在类的实现 ( .cpp) 文件后跟类要处理的事件的 DHTML_EVENT 宏 (例如，DHTML_EVENT_ONMOUSEOVER 悬停事件) 。 使用 [END_DHTML_EVENT_MAP](#end_dhtml_event_map) 宏来标记事件映射的结尾。 这些宏实现以下功能：

`virtual const DHtmlEventMapEntry* GetDHtmlEventMap();`

### <a name="requirements"></a>要求

  **标头** afxdhtml

## <a name="begin_dhtml_event_map_inline"></a><a name="begin_dhtml_event_map_inline"></a> BEGIN_DHTML_EVENT_MAP_INLINE

在 *className* 的类定义内标记 DHTML 事件映射的开头。

```cpp
BEGIN_DHTML_EVENT_MAP_INLINE(className)
```

### <a name="parameters"></a>parameters

*className*<br/>
包含 DHTML 事件映射的类的名称。 此类应直接或间接从 [CDHtmlDialog](../../mfc/reference/cdhtmldialog-class.md) 派生，并在其类定义中包含 [DECLARE_DHTML_EVENT_MAP](#declare_dhtml_event_map) 宏。

### <a name="remarks"></a>备注

将 DHTML 事件映射添加到你的类，以提供可用于将网页 `CDHtmlDialog` 中的 HTML 元素或 ActiveX 控件引发的事件路由到你的类中的处理程序函数的信息。

将 BEGIN_DHTML_EVENT_MAP 宏放在类的定义 ( .h) 文件中，然后将 DHTML_EVENT 宏用于类要处理的事件 (例如，DHTML_EVENT_ONMOUSEOVER 悬停事件) 。 使用 [END_DHTML_EVENT_MAP_INLINE](#end_dhtml_event_map_inline) 宏来标记事件映射的结尾。 这些宏实现以下功能：

`virtual const DHtmlEventMapEntry* GetDHtmlEventMap();`

### <a name="requirements"></a>要求

  **标头** afxdhtml

## <a name="declare_dhtml_event_map"></a><a name="declare_dhtml_event_map"></a> DECLARE_DHTML_EVENT_MAP

在类定义中声明 DHTML 事件映射。

```cpp
DECLARE_DHTML_EVENT_MAP()
```

### <a name="remarks"></a>备注

此宏将在 [CDHtmlDialog](../../mfc/reference/cdhtmldialog-class.md)派生类的定义中使用。

使用 [BEGIN_DHTML_EVENT_MAP](#begin_dhtml_event_map) 或 [BEGIN_DHTML_EVENT_MAP_INLINE](#begin_dhtml_event_map_inline) 来实现映射。

[DECLARE_DHTML_EVENT_MAP](#declare_dhtml_event_map) 声明以下函数：

`virtual const DHtmlEventMapEntry* GetDHtmlEventMap( );`

### <a name="requirements"></a>要求

  **标头** afxdhtml

## <a name="dhtml_event"></a><a name="dhtml_event"></a> DHTML_EVENT

在文档级别处理 (，) 由 *dispid* 标识的事件源自 *ELEMNAME* 标识的 HTML 元素。

```cpp
DHTML_EVENT(dispid, elemName,  memberFxn)
```

### <a name="parameters"></a>parameters

*dispid*<br/>
要处理的事件的 DISPID。

*elemName*<br/>
一个 LPCWSTR，它保留了事件的源的 ID，或为 NULL 以处理文档事件。

*memberFxn*<br/>
事件的处理程序函数。

### <a name="remarks"></a>备注

使用此宏可将条目添加到类中的 [DHTML 事件映射](#begin_dhtml_event_map_inline) 。

### <a name="requirements"></a>要求

  **标头** afxdhtml

## <a name="dhtml_event_axcontrol"></a><a name="dhtml_event_axcontrol"></a> DHTML_EVENT_AXCONTROL

处理由 *controlName* 标识的 ActiveX 控件触发的 *dispid* 标识的事件。

```cpp
DHTML_EVENT_AXCONTROL(dispid, controlName,  memberFxn)
```

### <a name="parameters"></a>parameters

*dispid*<br/>
要处理的事件的调度 ID。

*controlName*<br/>
保存触发事件的控件的 HTML ID 的 LPCWSTR。

*memberFxn*<br/>
事件的处理程序函数。

### <a name="remarks"></a>备注

使用此宏可将条目添加到类中的 [DHTML 事件映射](#begin_dhtml_event_map_inline) 。

### <a name="requirements"></a>要求

  **标头** afxdhtml

## <a name="dhtml_event_class"></a><a name="dhtml_event_class"></a> DHTML_EVENT_CLASS

在文档级别处理 () 由 *dispid* 标识的事件，该事件由 *ELEMNAME* 标识的 CSS 类的任何 HTML 元素发起。

```cpp
DHTML_EVENT_CLASS(dispid, elemName,  memberFxn)
```

### <a name="parameters"></a>parameters

*dispid*<br/>
要处理的事件的调度 ID。

*elemName*<br/>
一个 LPCWSTR，它保存事件的 HTML 元素的 CSS 类。

*memberFxn*<br/>
事件的处理程序函数。

### <a name="remarks"></a>备注

使用此宏可将条目添加到类中的 [DHTML 事件映射](#begin_dhtml_event_map_inline) 。

### <a name="requirements"></a>要求

  **标头** afxdhtml

## <a name="dhtml_event_element"></a><a name="dhtml_event_element"></a> DHTML_EVENT_ELEMENT

处理由 *elemName* 标识的元素 () 由 *dispid* 标识的事件。

```cpp
DHTML_EVENT_ELEMENT(dispid, elemName,  memberFxn)
```

### <a name="parameters"></a>parameters

*dispid*<br/>
要处理的事件的调度 ID。

*elemName*<br/>
保存事件的 HTML 元素的 ID 的 LPCWSTR。

*memberFxn*<br/>
事件的处理程序函数。

### <a name="remarks"></a>备注

使用此宏可将条目添加到类中的 [DHTML 事件映射](#begin_dhtml_event_map_inline) 。

如果使用此宏处理 nonbubbling 事件，则事件源将是 *elemName* 标识的元素。

如果使用此宏处理冒泡事件，则 *elemName* 标识的元素可能不是事件的源 (源可以是 *elemName*) 包含的任何元素。

### <a name="requirements"></a>要求

  **标头** afxdhtml

## <a name="dhtml_event_onafterupdate"></a><a name="dhtml_event_onafterupdate"></a> DHTML_EVENT_ONAFTERUPDATE

在文档级别处理 () `onafterupdate` 事件源自 *elemName* 标识的 HTML 元素。

```cpp
DHTML_EVENT_ONAFTERUPDATE(elemName, memberFxn)
```

### <a name="parameters"></a>parameters

*elemName*<br/>
保存事件的 HTML 元素的 ID 的 LPCWSTR。

*memberFxn*<br/>
事件的处理程序函数。

### <a name="remarks"></a>备注

使用此宏可将条目添加到类中的 [DHTML 事件映射](#begin_dhtml_event_map_inline) 。

### <a name="requirements"></a>要求

  **标头** afxdhtml

## <a name="dhtml_event_onbeforeupdate"></a><a name="dhtml_event_onbeforeupdate"></a> DHTML_EVENT_ONBEFOREUPDATE

在文档级别处理 () `onbeforeupdate` 事件源自 *elemName* 标识的 HTML 元素。

```cpp
DHTML_EVENT_ONBEFOREUPDATE(elemName, memberFxn)
```

### <a name="parameters"></a>parameters

*elemName*<br/>
保存事件的 HTML 元素的 ID 的 LPCWSTR。

*memberFxn*<br/>
事件的处理程序函数。

### <a name="remarks"></a>备注

使用此宏可将条目添加到类中的 [DHTML 事件映射](#begin_dhtml_event_map_inline) 。

### <a name="requirements"></a>要求

  **标头** afxdhtml

## <a name="dhtml_event_onblur"></a><a name="dhtml_event_onblur"></a> DHTML_EVENT_ONBLUR

处理事件) 元素级别 (`onblur` 。 这是一个 nonbubbling 事件。

```cpp
DHTML_EVENT_ONBLUR(elemName, memberFxn)
```

### <a name="parameters"></a>parameters

*elemName*<br/>
保存事件的 HTML 元素的 ID 的 LPCWSTR。

*memberFxn*<br/>
事件的处理程序函数。

### <a name="remarks"></a>备注

使用此宏可将条目添加到类中的 [DHTML 事件映射](#begin_dhtml_event_map_inline) 。

### <a name="requirements"></a>要求

  **标头** afxdhtml

## <a name="dhtml_event_onchange"></a><a name="dhtml_event_onchange"></a> DHTML_EVENT_ONCHANGE

处理事件) 元素级别 (`onchange` 。 这是一个 nonbubbling 事件。

```cpp
DHTML_EVENT_ONCHANGE(elemName, memberFxn)
```

### <a name="parameters"></a>parameters

*elemName*<br/>
保存事件的 HTML 元素的 ID 的 LPCWSTR。

*memberFxn*<br/>
事件的处理程序函数。

### <a name="remarks"></a>备注

使用此宏可将条目添加到类中的 [DHTML 事件映射](#begin_dhtml_event_map_inline) 。

### <a name="requirements"></a>要求

  **标头** afxdhtml

## <a name="dhtml_event_onclick"></a><a name="dhtml_event_onclick"></a> DHTML_EVENT_ONCLICK

在文档级别处理 () `onclick` 事件源自 *elemName* 标识的 HTML 元素。

```cpp
DHTML_EVENT_ONCLICK(elemName, memberFxn)
```

### <a name="parameters"></a>parameters

*elemName*<br/>
保存事件的 HTML 元素的 ID 的 LPCWSTR。

*memberFxn*<br/>
事件的处理程序函数。

### <a name="remarks"></a>备注

使用此宏可将条目添加到类中的 [DHTML 事件映射](#begin_dhtml_event_map_inline) 。

### <a name="requirements"></a>要求

  **标头** afxdhtml

## <a name="dhtml_event_ondataavailable"></a><a name="dhtml_event_ondataavailable"></a> DHTML_EVENT_ONDATAAVAILABLE

在文档级别处理 () `ondataavailable` 事件源自 *elemName* 标识的 HTML 元素。

```cpp
DHTML_EVENT_ONDATAAVAILABLE(elemName, memberFxn)
```

### <a name="parameters"></a>parameters

*elemName*<br/>
保存事件的 HTML 元素的 ID 的 LPCWSTR。

*memberFxn*<br/>
事件的处理程序函数。

### <a name="remarks"></a>备注

使用此宏可将条目添加到类中的 [DHTML 事件映射](#begin_dhtml_event_map_inline) 。

### <a name="requirements"></a>要求

  **标头** afxdhtml

## <a name="dhtml_event_ondatasetchanged"></a><a name="dhtml_event_ondatasetchanged"></a> DHTML_EVENT_ONDATASETCHANGED

在文档级别处理 () `ondatasetchanged` 事件源自 *elemName* 标识的 HTML 元素。

```cpp
DHTML_EVENT_ONDATASETCHANGED(elemName, memberFxn)
```

### <a name="parameters"></a>parameters

*elemName*<br/>
保存事件的 HTML 元素的 ID 的 LPCWSTR。

*memberFxn*<br/>
事件的处理程序函数。

### <a name="remarks"></a>备注

使用此宏可将条目添加到类中的 [DHTML 事件映射](#begin_dhtml_event_map_inline) 。

### <a name="requirements"></a>要求

  **标头** afxdhtml

## <a name="dhtml_event_ondatasetcomplete"></a><a name="dhtml_event_ondatasetcomplete"></a> DHTML_EVENT_ONDATASETCOMPLETE

在文档级别处理 () `ondatasetcomplete` 事件源自由标识的 HTML 元素 `elemName` 。

```cpp
DHTML_EVENT_ONDATASETCOMPLETE(elemName, memberFxn)
```

### <a name="parameters"></a>parameters

*elemName*<br/>
保存事件的 HTML 元素的 ID 的 LPCWSTR。

*memberFxn*<br/>
事件的处理程序函数。

### <a name="remarks"></a>备注

使用此宏可将条目添加到类中的 [DHTML 事件映射](#begin_dhtml_event_map_inline) 。

### <a name="requirements"></a>要求

  **标头** afxdhtml

## <a name="dhtml_event_ondblclick"></a><a name="dhtml_event_ondblclick"></a> DHTML_EVENT_ONDBLCLICK

在文档级别处理 () `ondblclick` 事件源自 *elemName* 标识的 HTML 元素。

```cpp
DHTML_EVENT_ONDBLCLICK(elemName, memberFxn)
```

### <a name="parameters"></a>parameters

*elemName*<br/>
保存事件的 HTML 元素的 ID 的 LPCWSTR。

*memberFxn*<br/>
事件的处理程序函数。

### <a name="remarks"></a>备注

使用此宏可将条目添加到类中的 [DHTML 事件映射](#begin_dhtml_event_map_inline) 。

### <a name="requirements"></a>要求

  **标头** afxdhtml

## <a name="dhtml_event_ondragstart"></a><a name="dhtml_event_ondragstart"></a> DHTML_EVENT_ONDRAGSTART

在文档级别处理 () `ondragstart` 事件源自 *elemName* 标识的 HTML 元素。

```cpp
DHTML_EVENT_ONDRAGSTART(elemName, memberFxn)
```

### <a name="parameters"></a>parameters

*elemName*<br/>
保存事件的 HTML 元素的 ID 的 LPCWSTR。

*memberFxn*<br/>
事件的处理程序函数。

### <a name="remarks"></a>备注

使用此宏可将条目添加到类中的 [DHTML 事件映射](#begin_dhtml_event_map_inline) 。

### <a name="requirements"></a>要求

  **标头** afxdhtml

## <a name="dhtml_event_onerrorupdate"></a><a name="dhtml_event_onerrorupdate"></a> DHTML_EVENT_ONERRORUPDATE

在文档级别处理 () `onerrorupdate` 事件源自 *elemName* 标识的 HTML 元素。

```cpp
DHTML_EVENT_ONERRORUPDATE(elemName, memberFxn)
```

### <a name="parameters"></a>parameters

*elemName*<br/>
保存事件的 HTML 元素的 ID 的 LPCWSTR。

*memberFxn*<br/>
事件的处理程序函数。

### <a name="remarks"></a>备注

使用此宏可将条目添加到类中的 [DHTML 事件映射](#begin_dhtml_event_map_inline) 。

### <a name="requirements"></a>要求

  **标头** afxdhtml

## <a name="dhtml_event_onfilterchange"></a><a name="dhtml_event_onfilterchange"></a> DHTML_EVENT_ONFILTERCHANGE

在文档级别处理 () `onfilterchange` 事件源自 *elemName* 标识的 HTML 元素。

```cpp
DHTML_EVENT_ONFILTERCHANGE(elemName, memberFxn)
```

### <a name="parameters"></a>parameters

*elemName*<br/>
保存事件的 HTML 元素的 ID 的 LPCWSTR。

*memberFxn*<br/>
事件的处理程序函数。

### <a name="remarks"></a>备注

使用此宏可将条目添加到类中的 [DHTML 事件映射](#begin_dhtml_event_map_inline) 。

### <a name="requirements"></a>要求

  **标头** afxdhtml

## <a name="dhtml_event_onfocus"></a><a name="dhtml_event_onfocus"></a> DHTML_EVENT_ONFOCUS

处理事件) 元素级别 (`onfocus` 。 这是一个 nonbubbling 事件。

```cpp
DHTML_EVENT_ONFOCUS(elemName, memberFxn)
```

### <a name="parameters"></a>parameters

*elemName*<br/>
保存事件的 HTML 元素的 ID 的 LPCWSTR。

*memberFxn*<br/>
事件的处理程序函数。

### <a name="remarks"></a>备注

使用此宏可将条目添加到类中的 [DHTML 事件映射](#begin_dhtml_event_map_inline) 。

### <a name="requirements"></a>要求

  **标头** afxdhtml

## <a name="dhtml_event_onhelp"></a><a name="dhtml_event_onhelp"></a> DHTML_EVENT_ONHELP

在文档级别处理 () `onhelp` 事件源自 *elemName* 标识的 HTML 元素。

```cpp
DHTML_EVENT_ONHELP(elemName, memberFxn)
```

### <a name="parameters"></a>parameters

*elemName*<br/>
保存事件的 HTML 元素的 ID 的 LPCWSTR。

*memberFxn*<br/>
事件的处理程序函数。

### <a name="remarks"></a>备注

使用此宏可将条目添加到类中的 [DHTML 事件映射](#begin_dhtml_event_map_inline) 。

### <a name="requirements"></a>要求

  **标头** afxdhtml

## <a name="dhtml_event_onkeydown"></a><a name="dhtml_event_onkeydown"></a> DHTML_EVENT_ONKEYDOWN

在文档级别处理 () `onkeydown` 事件源自 *elemName* 标识的 HTML 元素。

```cpp
DHTML_EVENT_ONKEYDOWN(elemName, memberFxn)
```

### <a name="parameters"></a>parameters

*elemName*<br/>
保存事件的 HTML 元素的 ID 的 LPCWSTR。

*memberFxn*<br/>
事件的处理程序函数。

### <a name="remarks"></a>备注

使用此宏可将条目添加到类中的 [DHTML 事件映射](#begin_dhtml_event_map_inline) 。

### <a name="requirements"></a>要求

  **标头** afxdhtml

## <a name="dhtml_event_onkeypress"></a><a name="dhtml_event_onkeypress"></a> DHTML_EVENT_ONKEYPRESS

在文档级别处理 () `onkeypress` 事件源自 *elemName* 标识的 HTML 元素。

```cpp
DHTML_EVENT_ONKEYPRESS(elemName, memberFxn)
```

### <a name="parameters"></a>parameters

*elemName*<br/>
保存事件的 HTML 元素的 ID 的 LPCWSTR。

*memberFxn*<br/>
事件的处理程序函数。

### <a name="remarks"></a>备注

使用此宏可将条目添加到类中的 [DHTML 事件映射](#begin_dhtml_event_map_inline) 。

### <a name="requirements"></a>要求

  **标头** afxdhtml

## <a name="dhtml_event_onkeyup"></a><a name="dhtml_event_onkeyup"></a> DHTML_EVENT_ONKEYUP

在文档级别处理 () `onkeyup` 事件源自 *elemName* 标识的 HTML 元素。

```cpp
DHTML_EVENT_ONKEYUP(elemName, memberFxn)
```

### <a name="parameters"></a>parameters

*elemName*<br/>
保存事件的 HTML 元素的 ID 的 LPCWSTR。

*memberFxn*<br/>
事件的处理程序函数。

### <a name="remarks"></a>备注

使用此宏可将条目添加到类中的 [DHTML 事件映射](#begin_dhtml_event_map_inline) 。

### <a name="requirements"></a>要求

  **标头** afxdhtml

## <a name="dhtml_event_onmousedown"></a><a name="dhtml_event_onmousedown"></a> DHTML_EVENT_ONMOUSEDOWN

在文档级别处理 () `onmousedown` 事件源自 *elemName* 标识的 HTML 元素。

```cpp
DHTML_EVENT_ONMOUSEDOWN(elemName, memberFxn)
```

### <a name="parameters"></a>parameters

*elemName*<br/>
保存事件的 HTML 元素的 ID 的 LPCWSTR。

*memberFxn*<br/>
事件的处理程序函数。

### <a name="remarks"></a>备注

使用此宏可将条目添加到类中的 [DHTML 事件映射](#begin_dhtml_event_map_inline) 。

### <a name="requirements"></a>要求

  **标头** afxdhtml

## <a name="dhtml_event_onmousemove"></a><a name="dhtml_event_onmousemove"></a> DHTML_EVENT_ONMOUSEMOVE

在文档级别处理 () `onmousemove` 事件源自 *elemName* 标识的 HTML 元素。

```cpp
DHTML_EVENT_ONMOUSEMOVE(elemName, memberFxn)
```

### <a name="parameters"></a>parameters

*elemName*<br/>
保存事件的 HTML 元素的 ID 的 LPCWSTR。

*memberFxn*<br/>
事件的处理程序函数。

### <a name="remarks"></a>备注

使用此宏可将条目添加到类中的 [DHTML 事件映射](#begin_dhtml_event_map_inline) 。

### <a name="requirements"></a>要求

  **标头** afxdhtml

## <a name="dhtml_event_onmouseout"></a><a name="dhtml_event_onmouseout"></a> DHTML_EVENT_ONMOUSEOUT

在文档级别处理 () `onmouseout` 事件源自 *elemName* 标识的 HTML 元素。

```cpp
DHTML_EVENT_ONMOUSEOUT(elemName, memberFxn)
```

### <a name="parameters"></a>parameters

*elemName*<br/>
保存事件的 HTML 元素的 ID 的 LPCWSTR。

*memberFxn*<br/>
事件的处理程序函数。

### <a name="remarks"></a>备注

使用此宏可将条目添加到类中的 [DHTML 事件映射](#begin_dhtml_event_map_inline) 。

### <a name="requirements"></a>要求

  **标头** afxdhtml

## <a name="dhtml_event_onmouseover"></a><a name="dhtml_event_onmouseover"></a> DHTML_EVENT_ONMOUSEOVER

在文档级别处理 () `onmouseover` 事件源自 *elemName* 标识的 HTML 元素。

```cpp
DHTML_EVENT_ONMOUSEOVER(elemName, memberFxn)
```

### <a name="parameters"></a>parameters

*elemName*<br/>
保存事件的 HTML 元素的 ID 的 LPCWSTR。

*memberFxn*<br/>
事件的处理程序函数。

### <a name="remarks"></a>备注

使用此宏可将条目添加到类中的 [DHTML 事件映射](#begin_dhtml_event_map_inline) 。

### <a name="requirements"></a>要求

  **标头** afxdhtml

## <a name="dhtml_event_onmouseup"></a><a name="dhtml_event_onmouseup"></a> DHTML_EVENT_ONMOUSEUP

在文档级别处理 () `onmouseup` 事件源自 *elemName* 标识的 HTML 元素。

```cpp
DHTML_EVENT_ONMOUSEUP(elemName, memberFxn)
```

### <a name="parameters"></a>parameters

*elemName*<br/>
保存事件的 HTML 元素的 ID 的 LPCWSTR。

*memberFxn*<br/>
事件的处理程序函数。

### <a name="remarks"></a>备注

使用此宏可将条目添加到类中的 [DHTML 事件映射](#begin_dhtml_event_map_inline) 。

### <a name="requirements"></a>要求

  **标头** afxdhtml

## <a name="dhtml_event_onresize"></a><a name="dhtml_event_onresize"></a> DHTML_EVENT_ONRESIZE

处理事件) 元素级别 (`onresize` 。 这是一个 nonbubbling 事件。

```cpp
DHTML_EVENT_ONRESIZE(elemName, memberFxn)
```

### <a name="parameters"></a>parameters

*elemName*<br/>
保存事件的 HTML 元素的 ID 的 LPCWSTR。

*memberFxn*<br/>
事件的处理程序函数。

### <a name="remarks"></a>备注

使用此宏可将条目添加到类中的 [DHTML 事件映射](#begin_dhtml_event_map_inline) 。

### <a name="requirements"></a>要求

  **标头** afxdhtml

## <a name="dhtml_event_onrowenter"></a><a name="dhtml_event_onrowenter"></a> DHTML_EVENT_ONROWENTER

在文档级别处理 () `onrowenter` 事件源自 *elemName* 标识的 HTML 元素。

```cpp
DHTML_EVENT_ONROWENTER(elemName, memberFxn)
```

### <a name="parameters"></a>parameters

*elemName*<br/>
保存事件的 HTML 元素的 ID 的 LPCWSTR。

*memberFxn*<br/>
事件的处理程序函数。

### <a name="remarks"></a>备注

使用此宏可将条目添加到类中的 [DHTML 事件映射](#begin_dhtml_event_map_inline) 。

### <a name="requirements"></a>要求

  **标头** afxdhtml

## <a name="dhtml_event_onrowexit"></a><a name="dhtml_event_onrowexit"></a> DHTML_EVENT_ONROWEXIT

在文档级别处理 () `onrowexit` 事件源自 *elemName* 标识的 HTML 元素。

```cpp
DHTML_EVENT_ONROWEXIT(elemName, memberFxn)
```

### <a name="parameters"></a>parameters

*elemName*<br/>
保存事件的 HTML 元素的 ID 的 LPCWSTR。

*memberFxn*<br/>
事件的处理程序函数。

### <a name="remarks"></a>备注

使用此宏可将条目添加到类中的 [DHTML 事件映射](#begin_dhtml_event_map_inline) 。

### <a name="requirements"></a>要求

  **标头** afxdhtml

## <a name="dhtml_event_onselectstart"></a><a name="dhtml_event_onselectstart"></a> DHTML_EVENT_ONSELECTSTART

在文档级别处理 () `onselectstart` 事件源自 *elemName* 标识的 HTML 元素。

```cpp
DHTML_EVENT_ONSELECTSTART(elemName, memberFxn)
```

### <a name="parameters"></a>parameters

*elemName*<br/>
保存事件的 HTML 元素的 ID 的 LPCWSTR。

*memberFxn*<br/>
事件的处理程序函数。

### <a name="remarks"></a>备注

使用此宏可将条目添加到类中的 [DHTML 事件映射](#begin_dhtml_event_map_inline) 。

### <a name="requirements"></a>要求

  **标头** afxdhtml

## <a name="dhtml_event_tag"></a><a name="dhtml_event_tag"></a> DHTML_EVENT_TAG

在文档级别处理 (，) 通过由 `dispid` *elemName* 标识的 html 标记的任何 html 元素生成的事件。

```cpp
DHTML_EVENT_TAG(dispid, elemName,  memberFxn)
```

### <a name="parameters"></a>parameters

*dispid*<br/>
要处理的事件的调度 ID。

*elemName*<br/>
事件的 HTML 标记的 html 标记。

*memberFxn*<br/>
事件的处理程序函数。

### <a name="remarks"></a>备注

使用此宏可将条目添加到类中的 [DHTML 事件映射](#begin_dhtml_event_map_inline) 。

### <a name="requirements"></a>要求

  **标头** afxdhtml

## <a name="end_dhtml_event_map"></a><a name="end_dhtml_event_map"></a> END_DHTML_EVENT_MAP

标记 DHTML 事件映射的结尾。

```cpp
END_DHTML_EVENT_MAP()
```

### <a name="remarks"></a>备注

必须与 [BEGIN_DHTML_EVENT_MAP](#begin_dhtml_event_map)结合使用。

### <a name="requirements"></a>要求

  **标头** afxdhtml

## <a name="begin_dhtml_url_event_map"></a><a name="begin_dhtml_url_event_map"></a> BEGIN_DHTML_URL_EVENT_MAP

启动多页对话框中的 DHTML 和 URL 事件映射的定义。

```cpp
BEGIN_DHTML_URL_EVENT_MAP()
```

### <a name="remarks"></a>备注

将 BEGIN_DHTML_URL_EVENT_MAP 放置在 [CMultiPageDHtmlDialog](../../mfc/reference/cmultipagedhtmldialog-class.md)派生类的实现文件中。 跟随嵌入的 [DHTML 事件映射](#begin_embed_dhtml_event_map) 和 [URL 条目](#begin_url_entries)，然后将其与 [END_DHTML_URL_EVENT_MAP](#end_dhtml_url_event_map)关闭。 将 [DECLARE_DHTML_URL_EVENT_MAP](#declare_dhtml_url_event_map) 宏包含在类定义中。

### <a name="example"></a>示例

[!code-cpp[NVC_MFCDocView#196](../../mfc/codesnippet/cpp/dhtml-event-maps_1.cpp)]

### <a name="requirements"></a>要求

  **标头** afxdhtml

## <a name="begin_embed_dhtml_event_map"></a><a name="begin_embed_dhtml_event_map"></a> BEGIN_EMBED_DHTML_EVENT_MAP

在多页对话框中开始定义嵌入的 DHTML 事件映射。

```cpp
BEGIN_EMBED_DHTML_EVENT_MAP(className, mapName)
```

### <a name="parameters"></a>parameters

*className*<br/>
包含事件映射的类的名称。 此类应直接或间接从 [CMultiPageDHtmlDialog](../../mfc/reference/cmultipagedhtmldialog-class.md)派生。 嵌入的 DHTML 事件映射必须位于 [DHTML 和 URL 事件映射](#begin_dhtml_url_event_map)) 。

*mapName*<br/>
指定其事件映射的页面。 这与 [URL_EVENT_ENTRY](#url_event_entry)宏中的 *mapName* 匹配，实际定义 URL 或 HTML 资源。

### <a name="remarks"></a>备注

由于多页面 DHTML 对话框包含多个 HTML 页面，每个页面都可以引发 DHTML 事件，因此，嵌入的事件映射用于将事件映射到每页的处理程序。

DHTML 和 URL 事件映射中嵌入的事件映射包括一个 BEGIN_EMBED_DHTML_EVENT_MAP 宏，后面跟 [DHTML_EVENT](#dhtml_event) 宏和 [END_EMBED_DHTML_EVENT_MAP](#end_embed_dhtml_event_map) 宏。

每个嵌入的事件映射都需要相应的 [URL 事件条目](#url_event_entry) ，以将 BEGIN_EMBED_DHTML_EVENT_MAP) 中指定的 *mapName* (映射到 URL 或 HTML 资源。

### <a name="example"></a>示例

请参阅 [BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map)中的示例。

### <a name="requirements"></a>要求

  **标头** afxdhtml

## <a name="begin_url_entries"></a><a name="begin_url_entries"></a> BEGIN_URL_ENTRIES

在多页对话框中启动 URL 事件输入映射的定义。

```cpp
BEGIN_URL_ENTRIES(className)
```

### <a name="parameters"></a>parameters

*className*<br/>
包含 URL 事件映射的类的名称。 此类应直接或间接从 [CMultiPageDHtmlDialog](../../mfc/reference/cmultipagedhtmldialog-class.md)派生。 URL 事件项映射必须位于 [DHTML 和 url 事件映射](#begin_dhtml_url_event_map)) 。

### <a name="remarks"></a>备注

因为多页面 DHTML 对话框包含多个 HTML 页面，所以，URL 事件条目用于将 Url 或 HTML 资源映射到相应的 [嵌入 DHTML 事件映射](#begin_embed_dhtml_event_map)。 将 URL_EVENT_ENTRY 宏置于 BEGIN_URL_ENTRIES 和 [END_URL_ENTRIES](#end_url_entries) 宏之间。

### <a name="example"></a>示例

请参阅 [BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map)中的示例。

### <a name="requirements"></a>要求

  **标头** afxdhtml

## <a name="declare_dhtml_url_event_map"></a><a name="declare_dhtml_url_event_map"></a> DECLARE_DHTML_URL_EVENT_MAP

在类定义中声明 DHTML 和 URL 事件映射。

```cpp
DECLARE_DHTML_URL_EVENT_MAP()
```

### <a name="remarks"></a>备注

此宏将在 [CMultiPageDHtmlDialog](../../mfc/reference/cmultipagedhtmldialog-class.md)派生类的定义中使用。

DHTML 和 URL 事件映射包含 [嵌入的 dhtml 事件映射](#begin_embed_dhtml_event_map) 和 [url 事件项](#begin_url_entries) ，用于在每个页面上将 DHTML 事件映射到处理程序。 使用 [BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map) 实现映射。

### <a name="requirements"></a>要求

  **标头** afxdhtml

## <a name="end_dhtml_url_event_map"></a><a name="end_dhtml_url_event_map"></a> END_DHTML_URL_EVENT_MAP

标记 DHTML 和 URL 事件映射的结尾。

```cpp
END_DHTML_URL_EVENT_MAP(className)
```

### <a name="parameters"></a>parameters

*className*<br/>
包含事件映射的类的名称。 此类应直接或间接从 [CMultiPageDHtmlDialog](../../mfc/reference/cmultipagedhtmldialog-class.md)派生。 这应与对应 [BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map)宏中的 *类* 匹配。

### <a name="example"></a>示例

请参阅 [BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map)中的示例。

### <a name="requirements"></a>要求

  **标头** afxdhtml

## <a name="end_embed_dhtml_event_map"></a><a name="end_embed_dhtml_event_map"></a> END_EMBED_DHTML_EVENT_MAP

标记嵌入的 DHTML 事件映射的结尾。

```cpp
END_EMBED_DHTML_EVENT_MAP()
```

### <a name="example"></a>示例

请参阅 [BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map)中的示例。

### <a name="requirements"></a>要求

  **标头** afxdhtml

## <a name="end_url_entries"></a><a name="end_url_entries"></a> END_URL_ENTRIES

标记 URL 事件项映射的结尾。

```cpp
END_URL_ENTRIES()
```

### <a name="example"></a>示例

请参阅 [BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map)中的示例。

### <a name="requirements"></a>要求

  **标头** afxdhtml

## <a name="url_event_entry"></a><a name="url_event_entry"></a> URL_EVENT_ENTRY

将 URL 或 HTML 资源映射到多页面对话框中的页面。

```cpp
URL_EVENT_ENTRY(className, url,  mapName)
```

### <a name="parameters"></a>parameters

*className*<br/>
包含 URL 事件映射的类的名称。 此类应直接或间接从 [CMultiPageDHtmlDialog](../../mfc/reference/cmultipagedhtmldialog-class.md)派生。 URL 事件项映射必须位于 [DHTML 和 url 事件映射](#begin_dhtml_url_event_map)) 。

*url*<br/>
页面的 URL 或 HTML 资源。

*mapName*<br/>
指定其 URL 为 *url* 的页。 这与在此页中映射事件 [BEGIN_EMBED_DHTML_EVENT_MAP](#begin_embed_dhtml_event_map)宏中的 *mapName* 匹配。

### <a name="remarks"></a>备注

如果该页是 HTML 资源，则 *url* 必须是资源 ID 号的字符串表示形式， (为 "123"，而不是123或 ID_HTMLRES1) 。

页标识符 *mapName* 是一个任意符号，用于将嵌入的 DHTML 事件映射链接到 URL 事件项映射。 它在 DHTML 和 URL 事件映射范围内受到限制。

### <a name="example"></a>示例

请参阅 [BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map)中的示例。

### <a name="requirements"></a>要求

  **标头** afxdhtml

## <a name="end_dhtml_event_map_inline"></a><a name="end_dhtml_event_map_inline"></a> END_DHTML_EVENT_MAP_INLINE

标记 DHTML 事件映射的结尾。

### <a name="syntax"></a>语法

```cpp
END_DHTML_EVENT_MAP_INLINE( )
```

### <a name="remarks"></a>备注

必须与 [BEGIN_DHTML_EVENT_MAP_INLINE](#begin_dhtml_event_map_inline)结合使用。

### <a name="requirements"></a>要求

**标头：** afxdhtml

## <a name="see-also"></a>请参阅

[MFC 宏和全局函数](mfc-macros-and-globals.md)
