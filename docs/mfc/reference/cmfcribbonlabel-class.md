---
description: 了解详细信息： CMFCRibbonLabel 类
title: CMFCRibbonLabel 类
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonLabel
- AFXRIBBONLABEL/CMFCRibbonLabel
- AFXRIBBONLABEL/CMFCRibbonLabel::CMFCRibbonLabel
- AFXRIBBONLABEL/CMFCRibbonLabel::SetACCData
helpviewer_keywords:
- CMFCRibbonLabel [MFC], CMFCRibbonLabel
- CMFCRibbonLabel [MFC], SetACCData
ms.assetid: 0346c891-83bf-4f20-b8a1-c84cf2aadced
ms.openlocfilehash: 0699e76dfe90b87cd813d18d076adf23f8512bee
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97321821"
---
# <a name="cmfcribbonlabel-class"></a>CMFCRibbonLabel 类

实现功能区的不可单击文本标签。

## <a name="syntax"></a>语法

```
class CMFCRibbonLabel : public CMFCRibbonButton
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CMFCRibbonLabel::CMFCRibbonLabel](#cmfcribbonlabel)|`CMFCRibbonLabel`使用指定的文本字符串构造并初始化一个对象。|
|`CMFCRibbonLabel::~CMFCRibbonLabel`|析构函数。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|`CMFCRibbonLabel::CreateObject`|由框架用于创建此类类型的动态实例。|
|`CMFCRibbonLabel::GetThisClass`|由框架用于获取指向与此类类型相关联的 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 对象的指针。|
|[CMFCRibbonLabel：： SetACCData](#setaccdata)|确定当前功能区标签元素的辅助功能数据。  (重写 [CMFCRibbonButton：： SetACCData](../../mfc/reference/cmfcribbonbutton-class.md#setaccdata)。 ) |

### <a name="remarks"></a>备注

创建功能区标签之后，通过调用 [CMFCRibbonPanel：： add](../../mfc/reference/cmfcribbonpanel-class.md#add)将其添加到面板。

不能将功能区标签添加到快速访问工具栏。

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)

[CMFCRibbonLabel](../../mfc/reference/cmfcribbonlabel-class.md)

## <a name="requirements"></a>要求

**标头：** afxRibbonLabel

## <a name="cmfcribbonlabelcmfcribbonlabel"></a><a name="cmfcribbonlabel"></a> CMFCRibbonLabel::CMFCRibbonLabel

构造并初始化一个 [CMFCRibbonLabel](../../mfc/reference/cmfcribbonlabel-class.md) 对象，该对象显示指定的文本字符串。

```
CMFCRibbonLabel(
    LPCTSTR lpszText,
    BOOL bIsMultiLine = FALSE);
```

### <a name="parameters"></a>parameters

*lpszText*<br/>
中要在标签中显示的文本。

*bIsMultiLine*<br/>
中如果指定标签为多行标签，则为 TRUE; 否则为。否则为 FALSE。

## <a name="cmfcribbonlabelsetaccdata"></a><a name="setaccdata"></a> CMFCRibbonLabel：： SetACCData

确定当前功能区标签元素的辅助功能数据。

```
virtual BOOL SetACCData(
    CWnd* pParent,
    CAccessibilityData& data);
```

### <a name="parameters"></a>parameters

*pParent*<br/>
中表示当前功能区标签的父窗口。

*data*<br/>
弄一个类型为的对象，该对象 `CAccessibilityData` 用当前功能区标签的可访问性数据填充。

### <a name="return-value"></a>返回值

如果已成功用当前功能区标签的可访问性数据填充 *数据* 参数，则为 TRUE;否则为 FALSE。

## <a name="see-also"></a>请参阅

[层次结构图](../../mfc/hierarchy-chart.md)<br/>
[Classes](../../mfc/reference/mfc-classes.md)<br/>
[CMFCRibbonButton 类](../../mfc/reference/cmfcribbonbutton-class.md)
