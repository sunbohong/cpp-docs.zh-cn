---
title: CMFCStandardColorsPropertyPage 类
ms.date: 11/04/2016
helpviewer_keywords:
- CMFCStandardColorsPropertyPage class [MFC]
ms.assetid: b84b7cfb-bb24-4c65-804a-5b642cb64400
ms.openlocfilehash: c57715171816e83cd1e04872d88b452b51b39388
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/25/2020
ms.locfileid: "88843945"
---
# <a name="cmfcstandardcolorspropertypage-class"></a>CMFCStandardColorsPropertyPage 类

表示一个属性页，用户可以使用该属性页选择颜色对话框中的标准颜色。

## <a name="syntax"></a>语法

```
class CMFCStandardColorsPropertyPage : public CPropertyPage
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|说明|
|-|-|
|`CMFCStandardColorsPropertyPage::CMFCStandardColorsPropertyPage`|默认构造函数。|

### <a name="public-methods"></a>公共方法

|“属性”|说明|
|-|-|
|`CMFCStandardColorsPropertyPage::CreateObject`|由框架用于创建此类类型的动态实例。|
|`CMFCStandardColorsPropertyPage::GetThisClass`|由框架用于获取指向与此类类型相关联的 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 对象的指针。|

### <a name="remarks"></a>注解

`CMFCColorDialog`类使用此类来显示标准颜色属性页。 有关的详细信息 `CMFCColorDialog` ，请参阅 [CMFCColorDialog 类](../../mfc/reference/cmfccolordialog-class.md)。

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CPropertyPage](../../mfc/reference/cpropertypage-class.md)

[CMFCStandardColorsPropertyPage](../../mfc/reference/cmfcstandardcolorspropertypage-class.md)

## <a name="requirements"></a>要求

**标头：** afxstandardcolorspropertypage

## <a name="see-also"></a>另请参阅

[层次结构图](../../mfc/hierarchy-chart.md)<br/>
[类](../../mfc/reference/mfc-classes.md)<br/>
[CMFCColorDialog 类](../../mfc/reference/cmfccolordialog-class.md)<br/>
[CMFCCustomColorsPropertyPage 类](../../mfc/reference/cmfccustomcolorspropertypage-class.md)
