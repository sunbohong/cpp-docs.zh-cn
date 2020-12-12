---
description: 了解详细信息： CMFCImageEditorDialog 类
title: CMFCImageEditorDialog 类
ms.date: 11/19/2018
f1_keywords:
- CMFCImageEditorDialog
- AFXIMAGEEDITORDIALOG/CMFCImageEditorDialog
- AFXIMAGEEDITORDIALOG/CMFCImageEditorDialog::CMFCImageEditorDialog
helpviewer_keywords:
- CMFCImageEditorDialog [MFC], CMFCImageEditorDialog
ms.assetid: 6a7d08f3-1ec2-4062-9b79-a0c2776b58d1
ms.openlocfilehash: 6c25cf4a1a8d0cc5852049a06c3a140cbb00a118
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97265384"
---
# <a name="cmfcimageeditordialog-class"></a>CMFCImageEditorDialog 类

`CMFCImageEditorDialog`类支持图像编辑器对话框。

## <a name="syntax"></a>语法

```
class CMFCImageEditorDialog : public CDialogEx
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CMFCImageEditorDialog：： CMFCImageEditorDialog](#cmfcimageeditordialog)|构造 `CMFCImageEditorDialog` 对象。|

## <a name="remarks"></a>备注

`CMFCImageEditorDialog`类提供一个对话框，其中包含：

- 用于修改图像中的单个像素的图像区域。

- 用于修改图片区域中像素的绘图工具。

- 用于指定绘图工具使用的颜色的调色板。

- 显示编辑效果的预览区域。

下图显示了 "图像编辑器" 对话框。

![CMFCImageEditorDialog 对话框](../../mfc/reference/media/imageedit.png "CMFCImageEditorDialog 对话框")

使用对象的一种方法 `CMFCImageEditorDialog` 是向其传递 `CBitmap` 要编辑的图像。 请勿创建大图像，因为图像编辑区域的大小有限，并调整了逻辑像素大小以适应区域。 调用 `DoModal` 方法以启动模式对话框。

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CDialogEx](../../mfc/reference/cdialogex-class.md)

[CMFCImageEditorDialog](../../mfc/reference/cmfcimageeditordialog-class.md)

## <a name="requirements"></a>要求

**标头：** afximageeditordialog

## <a name="cmfcimageeditordialogcmfcimageeditordialog"></a><a name="cmfcimageeditordialog"></a> CMFCImageEditorDialog：： CMFCImageEditorDialog

构造 `CMFCImageEditorDialog` 对象。

```
CMFCImageEditorDialog(
    CBitmap* pBitmap,
    CWnd* pParent=NULL,
    int nBitsPixel=-1);
```

### <a name="parameters"></a>parameters

*pBitmap*<br/>
指向图像的指针。

*pParent*<br/>
指向当前图像编辑器对话框的父窗口的指针。

*nBitsPixel*<br/>
用于表示单个像素的颜色的位数，也称为颜色深度。  如果 *nBitsPixel* 参数为-1，则颜色深度将派生自 *pBitmap* 参数指定的图像。 默认值为 -1。

### <a name="return-value"></a>返回值

若要修改图像，请将图像指针传递到 `CMFCImageEditorDialog` 构造函数。 然后调用 `DoModal` 方法以打开模式对话框。 当该 `DoModal` 方法返回时，位图包含新图像。

### <a name="remarks"></a>备注

### <a name="example"></a>示例

下面的示例演示如何构造类的对象 `CMFCImageEditorDialog` 。 此示例是 [新控件示例](../../overview/visual-cpp-samples.md)的一部分。

[!code-cpp[NVC_MFC_NewControls#8](../../mfc/reference/codesnippet/cpp/cmfcimageeditordialog-class_1.cpp)]
[!code-cpp[NVC_MFC_NewControls#40](../../mfc/reference/codesnippet/cpp/cmfcimageeditordialog-class_2.cpp)]

## <a name="see-also"></a>请参阅

[层次结构图](../../mfc/hierarchy-chart.md)<br/>
[Classes](../../mfc/reference/mfc-classes.md)<br/>
[CMFCToolBar 类](../../mfc/reference/cmfctoolbar-class.md)
