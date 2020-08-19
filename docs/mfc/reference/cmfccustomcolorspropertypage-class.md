---
title: CMFCCustomColorsPropertyPage 类
ms.date: 11/04/2016
f1_keywords:
- CMFCCustomColorsPropertyPage
- AFXCUSTOMCOLORSPROPERTYPAGE/CMFCCustomColorsPropertyPage
- AFXCUSTOMCOLORSPROPERTYPAGE/CMFCCustomColorsPropertyPage::Setup
helpviewer_keywords:
- CMFCCustomColorsPropertyPage [MFC], Setup
ms.assetid: 46a45ba2-1fda-440d-8018-d4dcd44f5816
ms.openlocfilehash: d4bdd1524f71bfba33e9090058fce26763a862bf
ms.sourcegitcommit: 1839405b97036891b6e4d37c99def044d6f37eff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/18/2020
ms.locfileid: "88561123"
---
# <a name="cmfccustomcolorspropertypage-class"></a>CMFCCustomColorsPropertyPage 类

表示可以在颜色对话框中选择自定义颜色的属性页。

## <a name="syntax"></a>语法

```
class CMFCCustomColorsPropertyPage : public CPropertyPage
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|||
|-|-|
|“属性”|说明|
|`CMFCCustomColorsPropertyPage::CMFCCustomColorsPropertyPage`|默认构造函数。|

### <a name="public-methods"></a>公共方法

|||
|-|-|
|“属性”|说明|
|`CMFCCustomColorsPropertyPage::CreateObject`|由框架用于创建此类类型的动态实例。|
|`CMFCCustomColorsPropertyPage::GetThisClass`|由框架用于获取指向与此类类型相关联的 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 对象的指针。|
|[CMFCCustomColorsPropertyPage：： Setup](#setup)|设置属性页的颜色部分。|

### <a name="remarks"></a>备注

`CMFCColorDialog`类使用此类来显示自定义颜色属性页。 有关的详细信息 `CMFCColorDialog` ，请参阅 [CMFCColorDialog 类](../../mfc/reference/cmfccolordialog-class.md)。

## <a name="example"></a>示例

下面的示例演示如何构造 `CMFCCustomColorsPropertyPage` 对象并设置属性页的颜色部分。

[!code-cpp[NVC_MFC_RibbonApp#35](../../mfc/reference/codesnippet/cpp/cmfccustomcolorspropertypage-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CPropertyPage](../../mfc/reference/cpropertypage-class.md)

[CMFCCustomColorsPropertyPage](../../mfc/reference/cmfccustomcolorspropertypage-class.md)

## <a name="requirements"></a>要求

**标头：** afxcustomcolorspropertypage

## <a name="cmfccustomcolorspropertypagesetup"></a><a name="setup"></a> CMFCCustomColorsPropertyPage：： Setup

设置属性页的颜色部分。

```cpp
void Setup(
    BYTE R,
    BYTE G,
    BYTE B);
```

### <a name="parameters"></a>参数

*迅驰*\
中RGB 值的红色部分。

*G*\
中RGB 值的绿色部分。

*B*\
中RGB 值的蓝色分量。

### <a name="remarks"></a>备注

此方法将更新当前的 RGB 和关联的 HLS (色调、亮度和饱和度) 属性页的颜色值。 当框架初始化 "颜色" 对话框或用户按下鼠标左键时， [CMFCColorDialog：： SetPageTwo](../../mfc/reference/cmfccolordialog-class.md#setpagetwo) 方法会调用此方法。 有关的详细信息 `CMFCColorDialog` ，请参阅 [CMFCColorDialog 类](../../mfc/reference/cmfccolordialog-class.md)。

## <a name="see-also"></a>另请参阅

[层次结构图](../../mfc/hierarchy-chart.md)<br/>
[类](../../mfc/reference/mfc-classes.md)<br/>
[CMFCColorDialog 类](../../mfc/reference/cmfccolordialog-class.md)<br/>
[CMFCStandardColorsPropertyPage 类](../../mfc/reference/cmfcstandardcolorspropertypage-class.md)
