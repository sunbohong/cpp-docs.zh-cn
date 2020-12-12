---
description: 了解详细信息： CMFCRibbonContextCaption 类
title: CMFCRibbonContextCaption 类
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonContextCaption
- AFXRIBBONBAR/CMFCRibbonContextCaption
- AFXRIBBONBAR/CMFCRibbonContextCaption::GetColor
- AFXRIBBONBAR/CMFCRibbonContextCaption::GetRightTabX
helpviewer_keywords:
- CMFCRibbonContextCaption [MFC], GetColor
- CMFCRibbonContextCaption [MFC], GetRightTabX
ms.assetid: cce2c0a2-8370-4266-997e-f8d0eeb3d616
ms.openlocfilehash: fa4134b89055274e4f44bef1150518207e06143e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97293620"
---
# <a name="cmfcribboncontextcaption-class"></a>CMFCRibbonContextCaption 类

实现显示在功能区类别或上下文类别顶部的彩色标题。

## <a name="syntax"></a>语法

```
class CMFCRibbonContextCaption : public CMFCRibbonButton
```

## <a name="members"></a>成员

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|`CMFCRibbonContextCaption::CreateObject`|由框架用于创建此类类型的动态实例。|
|[CMFCRibbonContextCaption：： GetColor](#getcolor)|返回标题栏的颜色。|
|[CMFCRibbonContextCaption::GetRightTabX](#getrighttabx)||
|`CMFCRibbonContextCaption::GetThisClass`|由框架用于获取指向与此类类型相关联的 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 对象的指针。|

## <a name="remarks"></a>备注

不能直接实例化此类。 [CMFCRibbonBar 类](../../mfc/reference/cmfcribbonbar-class.md)在内部使用此类向功能区类别添加颜色。

若要设置功能区类别的颜色，请调用 [CMFCRibbonCategory：： SetTabColor](../../mfc/reference/cmfcribboncategory-class.md#settabcolor)。 若要设置上下文类别的颜色，请调用 [CMFCRibbonBar：： AddContextCategory](../../mfc/reference/cmfcribbonbar-class.md#addcontextcategory)。

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)

[CMFCRibbonContextCaption](../../mfc/reference/cmfcribboncontextcaption-class.md)

## <a name="requirements"></a>要求

**标头：** afxribbonbar。h

## <a name="cmfcribboncontextcaptiongetcolor"></a><a name="getcolor"></a> CMFCRibbonContextCaption：： GetColor

返回标题的背景色。

```
AFX_RibbonCategoryColor GetColor() const;
```

### <a name="return-value"></a>返回值

返回的值可以是下列枚举值之一：

- `AFX_CategoryColor_None`

- `AFX_CategoryColor_Red`

- `AFX_CategoryColor_Orange`

- `AFX_CategoryColor_Yellow`

- `AFX_CategoryColor_Green`

- `AFX_CategoryColor_Blue`

- `AFX_CategoryColor_Indigo`

- `AFX_CategoryColor_Violet`

### <a name="remarks"></a>备注

可以通过调用 [CMFCRibbonCategory：： SetTabColor](../../mfc/reference/cmfcribboncategory-class.md#settabcolor) 或 [CMFCRibbonBar：： AddContextCategory](../../mfc/reference/cmfcribbonbar-class.md#addcontextcategory)来设置标题的颜色。

## <a name="cmfcribboncontextcaptiongetrighttabx"></a><a name="getrighttabx"></a> CMFCRibbonContextCaption::GetRightTabX

检索类别的功能区选项卡的右边缘的位置。

```
int GetRightTabX() const;
```

### <a name="return-value"></a>返回值

返回对象的功能区选项卡的封闭矩形的右 X 值 `CMFCRibbonCategory` ，如果该选项卡被截断，则返回值-1。

### <a name="remarks"></a>备注

## <a name="see-also"></a>请参阅

[层次结构图](../../mfc/hierarchy-chart.md)<br/>
[Classes](../../mfc/reference/mfc-classes.md)<br/>
[CMFCRibbonButton 类](../../mfc/reference/cmfcribbonbutton-class.md)<br/>
[CMFCRibbonCategory 类](../../mfc/reference/cmfcribboncategory-class.md)<br/>
[CMFCRibbonBar 类](../../mfc/reference/cmfcribbonbar-class.md)
