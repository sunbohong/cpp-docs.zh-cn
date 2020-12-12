---
description: 了解详细信息： CMFCImagePaintArea：： IMAGE_EDIT_MODE 枚举
title: CMFCImagePaintArea::IMAGE_EDIT_MODE 枚举
ms.date: 11/04/2016
f1_keywords:
- IMAGE_EDIT_MODE Enumeration
helpviewer_keywords:
- IMAGE_EDIT_MODE Enumeration method [MFC]
ms.assetid: e51db66a-fa1c-4766-9dac-a25b595f871a
ms.openlocfilehash: f28880d108be8fb4f2b14ede1a3cbd3c7dac9f2e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97265319"
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

|名称|描述|
|-|-|
|IMAGE_EDIT_MODE_PEN|用于绘制单独的像素。|
|IMAGE_EDIT_MODE_FILL|用于填充当前光标位置包含颜色的所有相邻区域。|
|IMAGE_EDIT_MODE_LINE|用于绘制线条。|
|IMAGE_EDIT_MODE_RECT|用于绘制矩形。|
|IMAGE_EDIT_MODE_ELLIPSE|用于绘制椭圆。|
|IMAGE_EDIT_MODE_COLOR|用于将当前颜色设置为当前光标位置处的颜色。|

### <a name="remarks"></a>备注

`CMFCImagePaintArea`和 `CMFCImageEditorDialog` 类使用此枚举来设置当前的绘制模式。 绘制模式和当前颜色用于在 "图像编辑器" 对话框中修改图片区域。 有关和的详细 `CMFCImagePaintArea` 信息 `CMFCImageEditorDialog` ，请参阅 [CMFCImagePaintArea 类](../../mfc/reference/cmfcimagepaintarea-class.md) 和 [CMFCImageEditorDialog 类](../../mfc/reference/cmfcimageeditordialog-class.md)。

使用 "IMAGE_EDIT_MODE_COLOR 绘制" 模式从图像中选择颜色时，框架会将当前绘制模式设置为 "IMAGE_EDIT_MODE_PEN"。

## <a name="requirements"></a>要求

**标头：** afximagepaintarea

## <a name="see-also"></a>请参阅

[MFC 宏和全局函数](../../mfc/reference/mfc-macros-and-globals.md)<br/>
[层次结构图](../../mfc/hierarchy-chart.md)<br/>
[Classes](../../mfc/reference/mfc-classes.md)<br/>
[CMFCImagePaintArea 类](../../mfc/reference/cmfcimagepaintarea-class.md)<br/>
[CMFCImageEditorDialog 类](../../mfc/reference/cmfcimageeditordialog-class.md)
