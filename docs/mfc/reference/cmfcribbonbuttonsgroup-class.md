---
description: 了解详细信息： CMFCRibbonButtonsGroup 类
title: CMFCRibbonButtonsGroup 类
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonButtonsGroup
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::CMFCRibbonButtonsGroup
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::AddButton
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::AddButtons
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::GetButton
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::GetCount
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::GetImageSize
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::GetRegularSize
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::HasImages
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::OnDrawImage
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::RemoveAll
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::SetImages
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::SetParentCategory
helpviewer_keywords:
- CMFCRibbonButtonsGroup [MFC], CMFCRibbonButtonsGroup
- CMFCRibbonButtonsGroup [MFC], AddButton
- CMFCRibbonButtonsGroup [MFC], AddButtons
- CMFCRibbonButtonsGroup [MFC], GetButton
- CMFCRibbonButtonsGroup [MFC], GetCount
- CMFCRibbonButtonsGroup [MFC], GetImageSize
- CMFCRibbonButtonsGroup [MFC], GetRegularSize
- CMFCRibbonButtonsGroup [MFC], HasImages
- CMFCRibbonButtonsGroup [MFC], OnDrawImage
- CMFCRibbonButtonsGroup [MFC], RemoveAll
- CMFCRibbonButtonsGroup [MFC], SetImages
- CMFCRibbonButtonsGroup [MFC], SetParentCategory
ms.assetid: b993d93e-fc1a-472f-a87f-1d7b7b499845
ms.openlocfilehash: 0b86ce6ff21bd36daaac9d68ce511ae395141170
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97293817"
---
# <a name="cmfcribbonbuttonsgroup-class"></a>CMFCRibbonButtonsGroup 类

`CMFCRibbonButtonsGroup`通过类，可以将一组功能区按钮组织到组中。 组中的所有按钮在水平位置上直接彼此相邻并位于边框中。

## <a name="syntax"></a>语法

```
class CMFCRibbonButtonsGroup : public CMFCRibbonBaseElement
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CMFCRibbonButtonsGroup::CMFCRibbonButtonsGroup](#cmfcribbonbuttonsgroup)|构造 `CMFCRibbonButtonsGroup` 对象。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CMFCRibbonButtonsGroup：： AddButton](#addbutton)|向组中添加一个按钮。|
|[CMFCRibbonButtonsGroup：： AddButtons](#addbuttons)|向组中添加按钮的列表。|
|[CMFCRibbonButtonsGroup：： GetButton](#getbutton)|返回指向位于指定索引处的按钮的指针。|
|[CMFCRibbonButtonsGroup：： GetCount](#getcount)|返回组中的按钮数。|
|[CMFCRibbonButtonsGroup::GetImageSize](#getimagesize)|返回功能区组中普通图像的图像大小 (重写 [CMFCRibbonBaseElement：： GetImageSize](../../mfc/reference/cmfcribbonbaseelement-class.md#getimagesize)。 ) |
|[CMFCRibbonButtonsGroup::GetRegularSize](#getregularsize)|返回功能区元素的常规大小 (重写 [CMFCRibbonBaseElement：： GetRegularSize](../../mfc/reference/cmfcribbonbaseelement-class.md#getregularsize)。 ) |
|[CMFCRibbonButtonsGroup::HasImages](#hasimages)|报告对象是否 `CMFCRibbonButtonsGroup` 包含工具栏图像。|
|[CMFCRibbonButtonsGroup::OnDrawImage](#ondrawimage)|根据按钮是正常、突出显示还是已禁用，绘制指定按钮的相应图像。|
|[CMFCRibbonButtonsGroup::RemoveAll](#removeall)|从对象中删除所有按钮 `CMFCRibbonButtonsGroup` 。|
|[CMFCRibbonButtonsGroup：： SetImages](#setimages)|将映像分配给组。|
|[CMFCRibbonButtonsGroup::SetParentCategory](#setparentcategory)|设置对象的父 `CMFCRibbonCategory` `CMFCRibbonButtonsGroup` 对象及其内的所有按钮 (重写 [CMFCRibbonBaseElement：： SetParentCategory](../../mfc/reference/cmfcribbonbaseelement-class.md#setparentcategory)。 ) |

## <a name="remarks"></a>备注

该组派生自 [CMFCBaseRibbonElement](../../mfc/reference/cmfcribbonbaseelement-class.md) ，可以作为单个实体进行操作。 可以在任何面板或弹出菜单上放置组。

## <a name="example"></a>示例

下面的示例演示了如何使用 `CMFCRibbonButtonsGroup` 类中的各种方法。 该示例演示如何构造 `CMFCRibbonButtonsGroup` 对象、将图像分配给功能区按钮组，以及向功能区按钮组添加一个按钮。 此代码片段属于 [Draw Client 示例](../../overview/visual-cpp-samples.md)。

[!code-cpp[NVC_MFC_DrawClient#2](../../mfc/reference/codesnippet/cpp/cmfcribbonbuttonsgroup-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonButtonsGroup](../../mfc/reference/cmfcribbonbuttonsgroup-class.md)

## <a name="requirements"></a>要求

**标头：** afxribbonbuttonsgroup

## <a name="cmfcribbonbuttonsgroupaddbutton"></a><a name="addbutton"></a> CMFCRibbonButtonsGroup：： AddButton

向组中添加一个按钮。

```cpp
void AddButton(CMFCRibbonBaseElement* pButton);
```

### <a name="parameters"></a>parameters

*pButton*<br/>
中指向要添加的按钮的指针。

## <a name="cmfcribbonbuttonsgroupaddbuttons"></a><a name="addbuttons"></a> CMFCRibbonButtonsGroup：： AddButtons

向组中添加按钮的列表。

```cpp
void AddButtons(
    const CList<CMFCRibbonBaseElement*,CMFCRibbonBaseElement*>& lstButtons);
```

### <a name="parameters"></a>parameters

*lstButtons*<br/>
中指向您要添加的按钮的指针的列表。

## <a name="cmfcribbonbuttonsgroupcmfcribbonbuttonsgroup"></a><a name="cmfcribbonbuttonsgroup"></a> CMFCRibbonButtonsGroup：： CMFCRibbonButtonsGroup

构造 `CMFCRibbonButtonsGroup` 对象。

```
CMFCRibbonButtonsGroup();
CMFCRibbonButtonsGroup(CMFCRibbonBaseElement* pButton);
```

### <a name="parameters"></a>parameters

*pButton*<br/>
中指定一个按钮以添加到新创建的 `CMFCRibbonButtonsGroup` 对象。

### <a name="return-value"></a>返回值

### <a name="remarks"></a>备注

## <a name="cmfcribbonbuttonsgroupgetbutton"></a><a name="getbutton"></a> CMFCRibbonButtonsGroup：： GetButton

返回指向位于指定索引处的按钮的指针。

```
CMFCRibbonBaseElement* GetButton(int i) const;
```

### <a name="parameters"></a>参数

*i*<br/>
中要返回的按钮的从零开始的索引。

### <a name="return-value"></a>返回值

指向位于指定索引处的按钮的指针。 如果指定的索引超出范围，则为 NULL。

### <a name="remarks"></a>备注

## <a name="cmfcribbonbuttonsgroupgetcount"></a><a name="getcount"></a> CMFCRibbonButtonsGroup：： GetCount

返回组中的按钮数。

```
int GetCount() const;
```

### <a name="return-value"></a>返回值

组中的按钮数。

## <a name="cmfcribbonbuttonsgroupgetimagesize"></a><a name="getimagesize"></a> CMFCRibbonButtonsGroup：： GetImageSize

检索受保护成员的源图像大小 `CMFCToolBarImages` `m_Images` 。

```
const CSize GetImageSize() const;
```

### <a name="return-value"></a>返回值

返回工具栏图像的源图像大小（如果有），或者如果不存在，则返回 `CSize` 零。

### <a name="remarks"></a>备注

## <a name="cmfcribbonbuttonsgroupgetregularsize"></a><a name="getregularsize"></a> CMFCRibbonButtonsGroup：： GetRegularSize

检索功能区组元素的最大可能大小。

```
virtual CSize GetRegularSize(CDC* pDC);
```

### <a name="parameters"></a>parameters

*pDC*<br/>
中指向功能区组的设备上下文的指针。

### <a name="return-value"></a>返回值

### <a name="remarks"></a>备注

## <a name="cmfcribbonbuttonsgrouphasimages"></a><a name="hasimages"></a> CMFCRibbonButtonsGroup：： HasImages

报告对象是否 `CMFCRibbonButtonsGroup` 包含工具栏图像。

```
BOOL HasImages() const;
```

### <a name="return-value"></a>返回值

如果受保护的 `CMFCToolBarImages` 成员 `m_Images` 包含任何图像，则返回 TRUE; 否则返回 FALSE。

### <a name="remarks"></a>备注

## <a name="cmfcribbonbuttonsgroupondrawimage"></a><a name="ondrawimage"></a> CMFCRibbonButtonsGroup：： OnDrawImage

根据按钮是正常、突出显示还是已禁用，绘制指定按钮的相应图像。

```
virtual void OnDrawImage(
    CDC* pDC,
    CRect rectImage,
    CMFCRibbonBaseElement* pButton,
    int nImageIndex);
```

### <a name="parameters"></a>parameters

*pDC*<br/>
中指向对象的设备上下文的指针 `CMFCRibbonButtonsGroup` 。

*rectImage*<br/>
中要在其中绘制图像的矩形。

*pButton*<br/>
中要为其绘制图像的按钮。

*nImageIndex*<br/>
中要在按钮上绘制的图像的索引 (在 "正常"、"突出显示" 或 "禁用" 按钮) 的三个图像数组之一中。

### <a name="remarks"></a>备注

## <a name="cmfcribbonbuttonsgroupremoveall"></a><a name="removeall"></a> CMFCRibbonButtonsGroup：： RemoveAll

从对象中删除所有按钮 `CMFCRibbonButtonsGroup` 。

```cpp
void RemoveAll();
```

### <a name="remarks"></a>备注

## <a name="cmfcribbonbuttonsgroupsetimages"></a><a name="setimages"></a> CMFCRibbonButtonsGroup：： SetImages

向功能区按钮组分配图像。

```cpp
void SetImages(
    CMFCToolBarImages* pImages,
    CMFCToolBarImages* pHotImages,
    CMFCToolBarImages* pDisabledImages);
```

### <a name="parameters"></a>parameters

*pImages*<br/>
中常规映像。

*pHotImages*<br/>
中热映像。

*pDisabledImages*<br/>
中已禁用映像。

### <a name="remarks"></a>备注

在 `SetImages` 将按钮添加到组之前调用。 映像数必须大于或等于要添加到组的按钮数。

> [!NOTE]
> 热映像是在用户将鼠标悬停在按钮上时显示的图像。 禁用的图像是在禁用按钮时显示的图像。

## <a name="cmfcribbonbuttonsgroupsetparentcategory"></a><a name="setparentcategory"></a> CMFCRibbonButtonsGroup：： SetParentCategory

设置对象的父 `CMFCRibbonCategory` `CMFCRibbonButtonsGroup` 对象及其内的所有按钮。

```
virtual void SetParentCategory(CMFCRibbonCategory* pCategory);
```

### <a name="parameters"></a>parameters

*pCategory*<br/>
中指向父类别的指针，用于设置功能区控件中的选项卡式组 () 的类别。

### <a name="remarks"></a>备注

## <a name="see-also"></a>请参阅

[层次结构图](../../mfc/hierarchy-chart.md)<br/>
[类](../../mfc/reference/mfc-classes.md)
