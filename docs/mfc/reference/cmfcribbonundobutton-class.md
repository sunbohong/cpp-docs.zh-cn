---
description: 了解详细信息： CMFCRibbonUndoButton 类
title: CMFCRibbonUndoButton 类
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonUndoButton
- AFXRIBBONUNDOBUTTON/CMFCRibbonUndoButton
- AFXRIBBONUNDOBUTTON/CMFCRibbonUndoButton::CMFCRibbonUndoButton
- AFXRIBBONUNDOBUTTON/CMFCRibbonUndoButton::AddUndoAction
- AFXRIBBONUNDOBUTTON/CMFCRibbonUndoButton::CleanUpUndoList
- AFXRIBBONUNDOBUTTON/CMFCRibbonUndoButton::GetActionNumber
- AFXRIBBONUNDOBUTTON/CMFCRibbonUndoButton::HasMenu
helpviewer_keywords:
- CMFCRibbonUndoButton [MFC], CMFCRibbonUndoButton
- CMFCRibbonUndoButton [MFC], AddUndoAction
- CMFCRibbonUndoButton [MFC], CleanUpUndoList
- CMFCRibbonUndoButton [MFC], GetActionNumber
- CMFCRibbonUndoButton [MFC], HasMenu
ms.assetid: 5c42adf7-871d-4239-901e-47ae7fb816fc
ms.openlocfilehash: 8bfc02b61160a5f11a6913736c5dc784c4d00ce4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97264929"
---
# <a name="cmfcribbonundobutton-class"></a>CMFCRibbonUndoButton 类

`CMFCRibbonUndoButton`类实现包含最新用户命令的下拉列表按钮。 用户可以从下拉列表中选择一个或多个最新命令以进行重做或撤消。

## <a name="syntax"></a>语法

```
class CMFCRibbonUndoButton : public CMFCRibbonGallery
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CMFCRibbonUndoButton::CMFCRibbonUndoButton](#cmfcribbonundobutton)|`CMFCRibbonUndoButton`使用指定的命令 ID、父对象的图像列表中的文本标签和图像构造新的对象。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CMFCRibbonUndoButton::AddUndoAction](#addundoaction)|向操作列表中添加新操作。|
|[CMFCRibbonUndoButton::CleanUpUndoList](#cleanupundolist)|清除操作列表，即下拉列表。|
|[CMFCRibbonUndoButton::GetActionNumber](#getactionnumber)|确定用户从下拉列表中选择的项的数目。|
|[CMFCRibbonUndoButton::HasMenu](#hasmenu)|指示对象是否包含菜单。|

## <a name="remarks"></a>备注

`CMFCRibbonUndoButton`类使用堆栈来表示下拉列表。

## <a name="example"></a>示例

下面的示例演示如何构造类的对象 `CMFCRibbonUndoButton` ，并向操作列表中添加新操作。 此代码片段是 [功能区小工具示例](../../overview/visual-cpp-samples.md)的一部分。

[!code-cpp[NVC_MFC_RibbonGadgets#2](../../mfc/reference/codesnippet/cpp/cmfcribbonundobutton-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)

[CMFCRibbonGallery](../../mfc/reference/cmfcribbongallery-class.md)

[CMFCRibbonUndoButton](../../mfc/reference/cmfcribbonundobutton-class.md)

## <a name="requirements"></a>要求

**标头：** afxribbonundobutton

## <a name="cmfcribbonundobuttonaddundoaction"></a><a name="addundoaction"></a> CMFCRibbonUndoButton::AddUndoAction

向操作列表中添加新操作。

```cpp
void AddUndoAction(LPCTSTR lpszLabel);
```

### <a name="parameters"></a>parameters

*lpszLabel*<br/>
中将在下拉列表中显示的操作标签。

## <a name="cmfcribbonundobuttoncleanupundolist"></a><a name="cleanupundolist"></a> CMFCRibbonUndoButton::CleanUpUndoList

清除操作列表，即下拉列表。

```cpp
void CleanUpUndoList();
```

## <a name="cmfcribbonundobuttoncmfcribbonundobutton"></a><a name="cmfcribbonundobutton"></a> CMFCRibbonUndoButton::CMFCRibbonUndoButton

`CMFCRibbonUndoButton`使用指定的命令 ID、父对象的图像列表中的文本标签和图像构造新的对象。

```
CMFCRibbonUndoButton(
    UINT nID,
    LPCTSTR lpszText,
    int nSmallImageIndex=-1,
    int nLargeImageIndex=-1);

CMFCRibbonUndoButton(
    UINT nID,
    LPCTSTR lpszText,
    HICON hIcon);
```

### <a name="parameters"></a>parameters

*nID*<br/>
中指定命令标识符。

*lpszText*<br/>
中指定按钮的文本标签。

*nSmallImageIndex*<br/>
中按钮的小图像的父对象的图像列表中从零开始的索引。

*nLargeImageIndex*<br/>
中按钮的大图像的父对象的图像列表中从零开始的索引。

*hIcon*<br/>
中可用作按钮图像的图标的句柄。

## <a name="cmfcribbonundobuttongetactionnumber"></a><a name="getactionnumber"></a> CMFCRibbonUndoButton::GetActionNumber

确定用户从下拉列表中选择的项的数目。

```
int GetActionNumber() const;
```

### <a name="return-value"></a>返回值

用户选择的项数。

## <a name="cmfcribbonundobuttonhasmenu"></a><a name="hasmenu"></a> CMFCRibbonUndoButton::HasMenu

指示对象是否包含菜单。

```
virtual BOOL HasMenu() const;
```

### <a name="return-value"></a>返回值

始终返回 TRUE。

### <a name="remarks"></a>备注

## <a name="see-also"></a>请参阅

[层次结构图](../../mfc/hierarchy-chart.md)<br/>
[Classes](../../mfc/reference/mfc-classes.md)<br/>
[CMFCRibbonGallery 类](../../mfc/reference/cmfcribbongallery-class.md)<br/>
[CMFCRibbonButton 类](../../mfc/reference/cmfcribbonbutton-class.md)
