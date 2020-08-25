---
title: CMFCImagePaintArea::IMAGE_EDIT_MODE 枚举
ms.date: 11/04/2016
f1_keywords:
- IMAGE_EDIT_MODE Enumeration
helpviewer_keywords:
- IMAGE_EDIT_MODE Enumeration method [MFC]
ms.assetid: e51db66a-fa1c-4766-9dac-a25b595f871a
ms.openlocfilehash: 37c877cc8562a9479535d9c6132e49e7c9b7e82f
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/25/2020
ms.locfileid: "88831133"
---
# <a name="cmfcimagepaintareaimage_edit_mode-enumeration"></a>CMFCImagePaintArea::IMAGE_EDIT_MODE 枚举

指定用于在 "图像编辑器" 对话框中修改图像的绘制模式。

## <a name="syntax"></a>语法

```
enum IMAGE_EDIT_MODE
{
    IMAGE_EDIT_MODE_PEN = 0,
    IMAGE_EDIT_MODE_FILL,
    IMAGE_EDIT_MODE_LINE,
    IMAGE_EDIT_MODE_RECT,
    IMAGE_EDIT_MODE_ELLIPSE,
    IMAGE_EDIT_MODE_COLOR
};
```

## <a name="members"></a>成员

|名称|说明|
|-|-|
|IMAGE_EDIT_MODE_PEN|用于绘制单独的像素。|
|IMAGE_EDIT_MODE_FILL|用于填充当前光标位置包含颜色的所有相邻区域。|
|IMAGE_EDIT_MODE_LINE|用于绘制线条。|
|IMAGE_EDIT_MODE_RECT|用于绘制矩形。|
|IMAGE_EDIT_MODE_ELLIPSE|用于绘制椭圆。|
|IMAGE_EDIT_MODE_COLOR|用于将当前颜色设置为当前光标位置处的颜色。|

### <a name="remarks"></a>注解

`CMFCImagePaintArea`和 `CMFCImageEditorDialog` 类使用此枚举来设置当前的绘制模式。 绘制模式和当前颜色用于在 "图像编辑器" 对话框中修改图片区域。 有关和的详细 `CMFCImagePaintArea` 信息 `CMFCImageEditorDialog` ，请参阅 [CMFCImagePaintArea 类](../../mfc/reference/cmfcimagepaintarea-class.md) 和 [CMFCImageEditorDialog 类](../../mfc/reference/cmfcimageeditordialog-class.md)。

使用 "IMAGE_EDIT_MODE_COLOR 绘制" 模式从图像中选择颜色时，框架会将当前绘制模式设置为 "IMAGE_EDIT_MODE_PEN"。

## <a name="requirements"></a>要求

**标头：** afximagepaintarea

## <a name="see-also"></a>另请参阅

[MFC 宏和全局函数](../../mfc/reference/mfc-macros-and-globals.md)<br/>
[层次结构图](../../mfc/hierarchy-chart.md)<br/>
[类](../../mfc/reference/mfc-classes.md)<br/>
[CMFCImagePaintArea 类](../../mfc/reference/cmfcimagepaintarea-class.md)<br/>
[CMFCImageEditorDialog 类](../../mfc/reference/cmfcimageeditordialog-class.md)
