---
description: 了解详细信息： CMFCDragFrameImpl 类
title: CMFCDragFrameImpl 类
ms.date: 10/18/2018
f1_keywords:
- CMFCDragFrameImpl
helpviewer_keywords:
- CMFCDragFrameImpl class [MFC]
ms.assetid: 500cd824-8188-43c2-8754-b7bb46b5648a
ms.openlocfilehash: 9885b750ace86d11ca573f23c7ee1c03d8926921
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97294049"
---
# <a name="cmfcdragframeimpl-class"></a>CMFCDragFrameImpl 类

`CMFCDragFrameImpl`类绘制当用户在标准停靠模式下拖动窗格时显示的拖动矩形。
有关更多详细信息，请参阅位于 Visual Studio 安装的 **VC \\ atlmfc \\ src \\ mfc** 文件夹中的源代码。

## <a name="syntax"></a>语法

```
class CMFCDragFrameImpl
```

## <a name="remarks"></a>备注

此类的对象嵌入每个 [CPane 类](../../mfc/reference/cpane-class.md) 对象。 因此，使用方法的每个窗格 `CanFloat` 会在用户拖动矩形时显示拖动矩形。

您可以通过使用 [AFX_GLOBAL_DATA：： m_nDragFrameThicknessFloat](afx-global-data-structure.md#m_ndragframethicknessfloat) 和 [AFX_GLOBAL_DATA：： m_nDragFrameThicknessDock](afx-global-data-structure.md#m_ndragframethicknessdock)来控制拖动矩形的粗细。

## <a name="inheritance-hierarchy"></a>继承层次结构

[CMFCDragFrameImpl](../../mfc/reference/cmfcdragframeimpl-class.md)

## <a name="requirements"></a>要求

**标头：** afxdragframeimpl

## <a name="cmfcdragframeimplenddrawdragframe"></a><a name="enddrawdragframe"></a> CMFCDragFrameImpl::EndDrawDragFrame

```cpp
void EndDrawDragFrame(BOOL bClearInternalRects = TRUE);
```

### <a name="parameters"></a>parameters

中 *bClearInternalRects*<br/>

### <a name="remarks"></a>备注

## <a name="cmfcdragframeimplinit"></a><a name="init"></a> CMFCDragFrameImpl：： Init

```cpp
void Init(CWnd* pDraggedWnd);
```

### <a name="parameters"></a>parameters

中 *pDraggedWnd*<br/>

### <a name="remarks"></a>备注

## <a name="cmfcdragframeimplmovedragframe"></a><a name="movedragframe"></a> CMFCDragFrameImpl::MoveDragFrame

```cpp
void MoveDragFrame(BOOL bForceMove = FALSE);
```

### <a name="parameters"></a>parameters

中 *bForceMove*<br/>

### <a name="remarks"></a>备注

## <a name="cmfcdragframeimplplacetabpredocking"></a><a name="placetabpredocking"></a> CMFCDragFrameImpl：:P laceTabPreDocking

```cpp
void PlaceTabPreDocking(
    CBaseTabbedPane* pTabbedBar,
    BOOL bFirstTime);

void PlaceTabPreDocking(CWnd* pCBarToPlaceOn);
```

### <a name="parameters"></a>parameters

中 *pTabbedBar*<br/>

中 *bFirstTime*<br/>

中 *pCBarToPlaceOn*<br/>

### <a name="remarks"></a>备注

## <a name="cmfcdragframeimplremovetabpredocking"></a><a name="removetabpredocking"></a> CMFCDragFrameImpl::RemoveTabPreDocking

```cpp
void RemoveTabPreDocking(CDockablePane* pOldTargetBar = NULL);
```

### <a name="parameters"></a>parameters

中 *pOldTargetBar*<br/>

### <a name="remarks"></a>备注

## <a name="cmfcdragframeimplresetstate"></a><a name="resetstate"></a> CMFCDragFrameImpl：： ResetState

```cpp
void ResetState();
```

### <a name="remarks"></a>备注

## <a name="see-also"></a>请参阅

[层次结构图](../../mfc/hierarchy-chart.md)<br/>
[Classes](../../mfc/reference/mfc-classes.md)<br/>
[CPane 类](../../mfc/reference/cpane-class.md)
