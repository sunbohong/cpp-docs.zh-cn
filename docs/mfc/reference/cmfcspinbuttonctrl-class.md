---
description: 了解详细信息： CMFCSpinButtonCtrl 类
title: CMFCSpinButtonCtrl 类
ms.date: 11/04/2016
f1_keywords:
- CMFCSpinButtonCtrl
- AFXSPINBUTTONCTRL/CMFCSpinButtonCtrl
- AFXSPINBUTTONCTRL/CMFCSpinButtonCtrl::OnDraw
helpviewer_keywords:
- CMFCSpinButtonCtrl [MFC], OnDraw
ms.assetid: 8773f259-4d3f-4bca-a71c-09e0c71bc843
ms.openlocfilehash: 87e9abc94247416704ab801beeaa1953c4cceb46
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97339627"
---
# <a name="cmfcspinbuttonctrl-class"></a>CMFCSpinButtonCtrl 类

`CMFCSpinButtonCtrl`类支持绘制数值调节钮控件的可视管理器。

## <a name="syntax"></a>语法

```
class CMFCSpinButtonCtrl : public CSpinButtonCtrl
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|`CMFCSpinButtonCtrl::CMFCSpinButtonCtrl`|默认构造函数。|
|`CMFCSpinButtonCtrl::~CMFCSpinButtonCtrl`|析构函数。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CMFCSpinButtonCtrl：： OnDraw](#ondraw)|重新绘制当前数值调节钮控件。|

## <a name="remarks"></a>备注

若要在应用程序中使用视觉对象管理器来绘制数值调节钮控件，请将类的所有实例替换 `CSpinButtonCtrl` 为 `CMFCSpinButtonCtrl` 类。

## <a name="example"></a>示例

下面的示例演示如何创建类的对象 `CMFCSpinButtonCtrl` 并使用其 `Create` 方法。

[!code-cpp[NVC_MFC_RibbonApp#25](../../mfc/reference/codesnippet/cpp/cmfcspinbuttonctrl-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CSpinButtonCtrl](../../mfc/reference/cspinbuttonctrl-class.md)

[CMFCSpinButtonCtrl](../../mfc/reference/cmfcspinbuttonctrl-class.md)

## <a name="requirements"></a>要求

**标头：** afxspinbuttonctrl

## <a name="cmfcspinbuttonctrlondraw"></a><a name="ondraw"></a> CMFCSpinButtonCtrl：： OnDraw

重新绘制当前数值调节钮控件。

```
virtual void OnDraw(CDC* pDC);
```

### <a name="parameters"></a>parameters

*pDC*<br/>
中指向设备上下文的指针。

### <a name="remarks"></a>备注

框架调用 `CMFCSpinButtonCtrl::OnPaint` 方法来处理 [CWnd：： OnPaint](../../mfc/reference/cwnd-class.md#onpaint) 消息，而该方法又调用此 `CMFCSpinButtonCtrl::OnDraw` 方法。 重写此方法以自定义框架绘制数值调节钮控件的方式。

## <a name="see-also"></a>请参阅

[层次结构图](../../mfc/hierarchy-chart.md)<br/>
[Classes](../../mfc/reference/mfc-classes.md)<br/>
[CMFCVisualManager 类](../../mfc/reference/cmfcvisualmanager-class.md)
