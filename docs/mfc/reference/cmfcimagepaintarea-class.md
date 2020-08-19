---
title: CMFCImagePaintArea 类
ms.date: 11/04/2016
f1_keywords:
- CMFCImagePaintArea
- AFXIMAGEPAINTAREA/CMFCImagePaintArea
- AFXIMAGEPAINTAREA/CMFCImagePaintArea::CMFCImagePaintArea
- AFXIMAGEPAINTAREA/CMFCImagePaintArea::GetMode
- AFXIMAGEPAINTAREA/CMFCImagePaintArea::SetBitmap
- AFXIMAGEPAINTAREA/CMFCImagePaintArea::SetColor
- AFXIMAGEPAINTAREA/CMFCImagePaintArea::SetMode
helpviewer_keywords:
- CMFCImagePaintArea [MFC], CMFCImagePaintArea
- CMFCImagePaintArea [MFC], GetMode
- CMFCImagePaintArea [MFC], SetBitmap
- CMFCImagePaintArea [MFC], SetColor
- CMFCImagePaintArea [MFC], SetMode
ms.assetid: c59eec22-f15a-4e58-8c4d-4a18a41f4452
ms.openlocfilehash: 3d8bfc40c3c9e937ad5acd7228e49877af65204a
ms.sourcegitcommit: 1839405b97036891b6e4d37c99def044d6f37eff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/18/2020
ms.locfileid: "88562150"
---
# <a name="cmfcimagepaintarea-class"></a>CMFCImagePaintArea 类

提供用于在 "图像编辑器" 对话框中修改图像的图片区域。

## <a name="syntax"></a>语法

```
class CMFCImagePaintArea : public CButton
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|||
|-|-|
|“属性”|说明|
|[CMFCImagePaintArea：： CMFCImagePaintArea](#cmfcimagepaintarea)|构造 `CMFCImagePaintArea` 对象。|
|`CMFCImagePaintArea::~CMFCImagePaintArea`|析构函数。|

### <a name="public-methods"></a>公共方法

|||
|-|-|
|“属性”|说明|
|[CMFCImagePaintArea：： GetMode](#getmode)|检索当前的绘制模式。|
|[CMFCImagePaintArea：： SetBitmap](#setbitmap)|设置图片区域的位图图像。|
|[CMFCImagePaintArea：： SetColor](#setcolor)|设置当前绘图颜色。|
|[CMFCImagePaintArea：： SetMode](#setmode)|设置当前的绘制模式。|

### <a name="remarks"></a>备注

此类不适于在您的代码中直接使用。

框架使用此类在 "图像编辑器" 对话框中显示图片区域。 有关 "图像编辑器" 对话框的详细信息，请参阅 [CMFCImageEditorDialog 类](../../mfc/reference/cmfcimageeditordialog-class.md)。

## <a name="example"></a>示例

下面的示例演示如何构造类的对象 `CMFCImagePaintArea` 、设置当前绘图颜色、设置当前绘制模式，以及设置图片区域的位图图像。

[!code-cpp[NVC_MFC_RibbonApp#37](../../mfc/reference/codesnippet/cpp/cmfcimagepaintarea-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CButton](../../mfc/reference/cbutton-class.md)

[CMFCImagePaintArea](../../mfc/reference/cmfcimagepaintarea-class.md)

## <a name="requirements"></a>要求

**标头：** afximagepaintarea

## <a name="cmfcimagepaintareacmfcimagepaintarea"></a><a name="cmfcimagepaintarea"></a> CMFCImagePaintArea：： CMFCImagePaintArea

构造 `CMFCImagePaintArea` 对象。

```
CMFCImagePaintArea(CMFCImageEditorDialog* pParentDlg);
```

### <a name="parameters"></a>参数

*pParentDlg*\
中指向对话框的指针，该对话框是图像编辑器的父级。

## <a name="cmfcimagepaintareagetmode"></a><a name="getmode"></a> CMFCImagePaintArea：： GetMode

检索当前的绘制模式。

```
IMAGE_EDIT_MODE GetMode() const;
```

### <a name="return-value"></a>返回值

指定当前绘制模式的 [IMAGE_EDIT_MODE](cmfcimagepaintarea-image-edit-mode-enumeration.md) 值。

## <a name="cmfcimagepaintareasetbitmap"></a><a name="setbitmap"></a> CMFCImagePaintArea：： SetBitmap

设置图片区域的位图图像。

```cpp
void SetBitmap(CBitmap* pBitmap);
```

### <a name="parameters"></a>参数

*pBitmap*\
中要显示的新位图图像。

### <a name="remarks"></a>备注

如果 *pBitmap* 为 NULL，则此方法将可修改的绘制区域的大小设置为零。 否则，它会将可修改的绘制区域的大小设置为所提供的位图图像的大小。

## <a name="cmfcimagepaintareasetcolor"></a><a name="setcolor"></a> CMFCImagePaintArea：： SetColor

设置当前绘图颜色。

```cpp
void SetColor(COLORREF color);
```

### <a name="parameters"></a>参数

*颜色*\
中新的绘图颜色。

### <a name="remarks"></a>备注

从 "图像编辑器" 调色板栏或颜色选取器中选择颜色时，框架会调用此方法以更新当前绘图颜色。 初始绘图颜色为黑色 (COLORREF 值为 0) 。

除 IMAGE_EDIT_MODE_COLOR 之外，所有绘制模式的 "图像编辑器" 对话框都使用绘图颜色。 有关绘制模式的详细信息，请参阅 [CMFCImagePaintArea：： IMAGE_EDIT_MODE 枚举](cmfcimagepaintarea-image-edit-mode-enumeration.md)。

## <a name="cmfcimagepaintareasetmode"></a><a name="setmode"></a> CMFCImagePaintArea：： SetMode

设置当前的绘制模式。

```cpp
void SetMode(IMAGE_EDIT_MODE mode);
```

### <a name="parameters"></a>参数

*众*\
中指定当前绘制模式的 [IMAGE_EDIT_MODE](cmfcimagepaintarea-image-edit-mode-enumeration.md) 值。

## <a name="see-also"></a>另请参阅

[层次结构图](../../mfc/hierarchy-chart.md)<br/>
[类](../../mfc/reference/mfc-classes.md)<br/>
[CMFCImageEditorDialog 类](../../mfc/reference/cmfcimageeditordialog-class.md)
