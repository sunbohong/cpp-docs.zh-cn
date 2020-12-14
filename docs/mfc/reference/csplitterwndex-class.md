---
description: 了解详细信息： CSplitterWndEx 类
title: CSplitterWndEx 类
ms.date: 11/04/2016
f1_keywords:
- CSplitterWndEx
- AFXSPLITTERWNDEX/CSplitterWndEx
- AFXSPLITTERWNDEX/CSplitterWndEx::OnDrawSplitter
helpviewer_keywords:
- CSplitterWndEx [MFC], OnDrawSplitter
ms.assetid: 33e5eef3-05e1-4a07-a968-bf9207ce8598
ms.openlocfilehash: 357f650551871cc9768c8e4e693bd62bb5e69bc4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97345090"
---
# <a name="csplitterwndex-class"></a>CSplitterWndEx 类

表示自定义拆分窗口。

## <a name="syntax"></a>语法

```
class CSplitterWndEx : public CSplitterWnd
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|`CSplitterWndEx::CSplitterWndEx`|默认构造函数。|
|`CSplitterWndEx::~CSplitterWndEx`|析构函数。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CSplitterWndEx::OnDrawSplitter](#ondrawsplitter)|由框架调用，用于绘制拆分窗口。  (重写 [CSplitterWnd：： OnDrawSplitter](csplitterwnd-class.md#ondrawsplitter)。 ) |

## <a name="remarks"></a>备注

重写 `OnDrawSplitter` 方法以自定义拆分器窗口的图形组件的外观。

`CSplitterWndEx`类与由可视化管理器实现的[OnDrawSplitterBorder](cmfcvisualmanager-class.md#ondrawsplitterborder)、 [OnDrawSplitterBox](cmfcvisualmanager-class.md#ondrawsplitterbox)和[OnFillSplitterBackground](cmfcvisualmanager-class.md#onfillsplitterbackground)方法一起使用。 若要使视觉对象管理器在你的应用程序中绘制拆分窗口，请将类的声明替换 `CSplitterWnd` 为 `CSplitterWndEx` 类。 对于框架窗口应用程序，将在位于 mainfrm.cpp 的 CMainFrame 类中声明拆分窗口类。 有关示例，请参阅示例 `OutlookDemo` 目录中的示例。

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](cobject-class.md)

[CCmdTarget](ccmdtarget-class.md)

[CWnd](cwnd-class.md)

[CSplitterWnd](csplitterwnd-class.md)

## <a name="requirements"></a>要求

**标头：** afxsplitterwndex

## <a name="csplitterwndexondrawsplitter"></a><a name="ondrawsplitter"></a> CSplitterWndEx::OnDrawSplitter

由框架调用，用于绘制拆分窗口。

```
virtual void OnDrawSplitter(
   CDC* pDC,
   ESplitType nType,
   const CRect& rect
);
```

### <a name="parameters"></a>parameters

*pDC*<br/>
中指向设备上下文的指针。 如果此参数为 NULL，则框架将重新绘制活动窗口。

nType<br/>
中 `CSplitterWnd::ESplitType` 枚举值之一，指定要绘制的拆分窗口元素。 有效值为 `splitBox`、`splitBar`、`splitIntersection` 和 `splitBorder`。

*rect*<br/>
中指定用于绘制指定拆分窗口元素的尺寸和位置的边框。

### <a name="remarks"></a>备注

## <a name="see-also"></a>请参阅

[层次结构图](../hierarchy-chart.md)<br/>
[Classes](mfc-classes.md)<br/>
[CSplitterWnd 类](csplitterwnd-class.md)<br/>
[CMFCVisualManager 类](cmfcvisualmanager-class.md)
