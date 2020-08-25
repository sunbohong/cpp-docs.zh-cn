---
title: Windows 消息宏
ms.date: 11/04/2016
f1_keywords:
- atlbase/ATL::WM_FORWARDMSG
ms.assetid: 63abd22c-372d-4148-bb04-c605950ae64f
ms.openlocfilehash: b4cd3c2eea24449eb17050b147d9c59560d8358f
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/25/2020
ms.locfileid: "88834435"
---
# <a name="windows-messages-macros"></a>Windows 消息宏

此宏转发窗口消息。

|名称|说明|
|-|-|
|[WM_FORWARDMSG](#wm_forwardmsg)|使用将窗口接收的消息转发到另一个窗口进行处理。|

## <a name="requirements"></a>要求

**标头：** atlbase。h

## <a name="wm_forwardmsg"></a><a name="wm_forwardmsg"></a> WM_FORWARDMSG

此宏将窗口接收的消息转发到另一个窗口进行处理。

```
WM_FORWARDMSG
```

### <a name="return-value"></a>返回值

如果消息已处理，则为非零值。

### <a name="remarks"></a>注解

使用 WM_FORWARDMSG 将窗口接收的消息转发到另一个窗口进行处理。 LPARAM 和 WPARAM 参数的使用方式如下：

|参数|使用情况|
|---------------|-----------|
|WPARAM|用户定义的数据|
|LPARAM|指向 `MSG` 结构的指针，该结构包含有关消息的信息|

### <a name="example"></a>示例

在下面的示例中， `m_hWndOther` 表示接收此消息的另一个窗口。

[!code-cpp[NVC_ATL_Windowing#137](../../atl/codesnippet/cpp/windows-messages-macros_1.cpp)]

## <a name="see-also"></a>另请参阅

[宏](../../atl/reference/atl-macros.md)
