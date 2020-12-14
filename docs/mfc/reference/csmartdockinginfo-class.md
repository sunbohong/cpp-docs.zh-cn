---
description: 了解详细信息： CSmartDockingInfo 类
title: CSmartDockingInfo 类
ms.date: 11/19/2018
f1_keywords:
- CSmartDockingInfo
- AFXDOCKINGMANAGER/CSmartDockingInfo
- AFXDOCKINGMANAGER/CSmartDockingInfo::CopyTo
- AFXDOCKINGMANAGER/CSmartDockingInfo::m_bUseThemeColorInShading
- AFXDOCKINGMANAGER/CSmartDockingInfo::m_clrBaseBackground
- AFXDOCKINGMANAGER/CSmartDockingInfo::m_clrToneDest
- AFXDOCKINGMANAGER/CSmartDockingInfo::m_clrToneSrc
- AFXDOCKINGMANAGER/CSmartDockingInfo::m_clrTransparent
- AFXDOCKINGMANAGER/CSmartDockingInfo::m_nCentralGroupOffset
- AFXDOCKINGMANAGER/CSmartDockingInfo::m_sizeTotal
- AFXDOCKINGMANAGER/CSmartDockingInfo::m_uiMarkerBmpResID
- AFXDOCKINGMANAGER/CSmartDockingInfo::m_uiMarkerLightBmpResID
helpviewer_keywords:
- CSmartDockingInfo [MFC], CopyTo
- CSmartDockingInfo [MFC], m_bUseThemeColorInShading
- CSmartDockingInfo [MFC], m_clrBaseBackground
- CSmartDockingInfo [MFC], m_clrToneDest
- CSmartDockingInfo [MFC], m_clrToneSrc
- CSmartDockingInfo [MFC], m_clrTransparent
- CSmartDockingInfo [MFC], m_nCentralGroupOffset
- CSmartDockingInfo [MFC], m_sizeTotal
- CSmartDockingInfo [MFC], m_uiMarkerBmpResID
- CSmartDockingInfo [MFC], m_uiMarkerLightBmpResID
ms.assetid: cab04f38-4bc1-4378-9337-c56fc87fbd68
ms.openlocfilehash: 290f9eef208ceed425739ab26e7811c04309e057
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97345129"
---
# <a name="csmartdockinginfo-class"></a>CSmartDockingInfo 类

定义智能停靠标记的外观。

## <a name="syntax"></a>语法

```
class CSmartDockingInfo : public CObject
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|`CSmartDockingInfo::CSmartDockingInfo`|默认构造函数。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CSmartDockingInfo：： CopyTo](#copyto)|将当前智能停靠信息参数复制到提供的 [CSmartDockingInfo](../../mfc/reference/csmartdockinginfo-class.md) 对象中。|

### <a name="data-members"></a>数据成员

|名称|描述|
|----------|-----------------|
|[CSmartDockingInfo：： m_bUseThemeColorInShading](#m_busethemecolorinshading)|指定在框架显示智能停靠标记时是否使用当前主题颜色。|
|[CSmartDockingInfo：： m_clrBaseBackground](#m_clrbasebackground)|指定智能停靠标记的基本背景色。|
|[CSmartDockingInfo：： m_clrToneDest](#m_clrtonedest)|指定 `m_clrToneSrc` 在智能停靠标记位图中替换的颜色。|
|[CSmartDockingInfo：： m_clrToneSrc](#m_clrtonesrc)|指定智能停靠标记位图的颜色。|
|[CSmartDockingInfo：： m_clrTransparent](#m_clrtransparent)|指定在其透明时智能停靠标记位图的颜色。|
|[CSmartDockingInfo：： m_nCentralGroupOffset](#m_ncentralgroupoffset)|指定智能停靠标记的中心组相对于中心组矩形边界的偏移量。|
|[CSmartDockingInfo：： m_sizeTotal](#m_sizetotal)|指定组中所有智能停靠标记的总大小。|
|[CSmartDockingInfo：： m_uiMarkerBmpResID](#m_uimarkerbmpresid)|定义框架用于未突出显示的智能停靠标记的位图的资源 Id。|
|[CSmartDockingInfo：： m_uiMarkerLightBmpResID](#m_uimarkerlightbmpresid)|定义框架为突出显示的智能停靠标记使用的位图的资源 Id。|

## <a name="remarks"></a>备注

框架在内部处理智能停靠标记。 下图显示了标准的智能停靠标记：

![标准智能停靠标记](../../mfc/reference/media/nextsdmarkers.png "标准智能停靠标记")

在此图中，左侧的图像显示未启用到选项卡的中心组智能停靠标记。 中间的图像显示了一个右边缘智能停靠标记。 右图显示了一个已启用选项卡停靠的中心组智能停靠标记。 中央组智能停靠标记具有主位图和五个智能停靠标记位图。

您可以自定义智能停靠标记的下列参数：

- 颜色。 例如，可以将图形中标记的蓝色颜色替换为任何用户定义的颜色。

- 透明度颜色。

- 中心组中来自边框边框的智能停靠标记的偏移量。

- 表示中心组的主位图。

- 表示常规和突出显示的智能停靠标记的位图。

下图显示了已自定义的智能停靠标记的示例：

![自定义智能停靠标记](../../mfc/reference/media/nextsdmarkerscustom.png "自定义智能停靠标记")

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

[CSmartDockingInfo](../../mfc/reference/csmartdockinginfo-class.md)

## <a name="requirements"></a>要求

**标头：** afxDockingManager

## <a name="csmartdockinginfocopyto"></a><a name="copyto"></a> CSmartDockingInfo：： CopyTo

将当前智能停靠参数复制到提供的 [CSmartDockingInfo](../../mfc/reference/csmartdockinginfo-class.md) 对象中。

```cpp
void CopyTo(CSmartDockingInfo& params);
```

### <a name="parameters"></a>parameters

*params*<br/>
弄 `CSmartDockingInfo` 使用当前智能停靠参数填充的类型的对象。

## <a name="csmartdockinginfom_busethemecolorinshading"></a><a name="m_busethemecolorinshading"></a> CSmartDockingInfo：： m_bUseThemeColorInShading

指定在框架显示智能停靠标记时是否使用当前主题颜色。

```
BOOL m_bUseThemeColorInShading;
```

### <a name="remarks"></a>备注

如果为 TRUE，则使用当前主题颜色绘制标记;否则，将用浅蓝色绘制标记。

默认值是 FALSE。

## <a name="csmartdockinginfom_clrbasebackground"></a><a name="m_clrbasebackground"></a> CSmartDockingInfo：： m_clrBaseBackground

指定智能停靠标记的基本背景色。

```
COLORREF m_clrBaseBackground;
```

## <a name="csmartdockinginfom_clrtonedest"></a><a name="m_clrtonedest"></a> CSmartDockingInfo：： m_clrToneDest

指定将 `m_clrToneSrc` 在智能停靠标记位图中替换的颜色。

```
COLORREF m_clrToneDest;
```

### <a name="remarks"></a>备注

将此值设置为以编程方式更改标记位图的颜色。 例如，如果要更改随框架提供的标准标记的颜色，请将此值设置为所需的颜色。 默认情况下， [CSmartDockingInfo：： m_clrToneSrc](#m_clrtonesrc) 设置为 RGB (61、123、241)  (bluish 颜色) 。

若要更改自定义标记的颜色，必须同时指定 `m_clrToneDest` 和 `m_clrToneSrc` 。

## <a name="csmartdockinginfom_clrtonesrc"></a><a name="m_clrtonesrc"></a> CSmartDockingInfo：： m_clrToneSrc

指定智能停靠标记位图的颜色。

```
COLORREF m_clrToneSrc;
```

### <a name="remarks"></a>备注

仅当想要将自定义位图的颜色替换为另一种颜色时，才设置此值。 如果要更改) 标记中提供的标准 (框架的颜色，则无需设置此值。

用于 `(COLORREF)-1` 使智能停靠组的成员保持为空。

## <a name="csmartdockinginfom_clrtransparent"></a><a name="m_clrtransparent"></a> CSmartDockingInfo：： m_clrTransparent

指定在其透明时智能停靠标记位图的颜色。

```
COLORREF m_clrTransparent;
```

### <a name="remarks"></a>备注

在停靠组中显示自定义标记和自定义位图时，必须设置此值。

## <a name="csmartdockinginfom_ncentralgroupoffset"></a><a name="m_ncentralgroupoffset"></a> CSmartDockingInfo：： m_nCentralGroupOffset

指定智能停靠标记的中心组和中心组矩形边界之间的偏移量。

```
int m_nCentralGroupOffset;
```

### <a name="remarks"></a>备注

如果要更改自定义标记与智能停靠标记的中心组边界之间的默认偏移量，请指定此值。 默认偏移量为5像素。

## <a name="csmartdockinginfom_sizetotal"></a><a name="m_sizetotal"></a> CSmartDockingInfo：： m_sizeTotal

指定包含中央组中所有智能停靠标记的边框的总大小。

```
CSize m_sizeTotal;
```

### <a name="remarks"></a>备注

设置 `m_sizeTotal` 为中心组标记的边框的大小。 如果要将自定义位图用于标记，则需要指定此值。

## <a name="csmartdockinginfom_uimarkerbmpresid"></a><a name="m_uimarkerbmpresid"></a> CSmartDockingInfo：： m_uiMarkerBmpResID

定义用于未突出显示的自定义智能停靠标记的位图的资源 Id。

```
UINT m_uiMarkerBmpResID[AFX_SD_MARKERS_NUM];
```

### <a name="remarks"></a>备注

用表示智能停靠标记的位图的资源 Id 填充此数组。 AFX_SD_MARKERS_NUM 当前定义为5。 填充数组的方式如下：

```cpp
params.m_uiMarkerBmpResID[0] = IDB_MARKER_LEFT;
params.m_uiMarkerBmpResID[1] = IDB_MARKER_RIGHT;
params.m_uiMarkerBmpResID[2] = IDB_MARKER_TOP;
params.m_uiMarkerBmpResID[3] = IDB_MARKER_BOTTOM;
params.m_uiMarkerBmpResID[4] = IDB_MARKER_CENTER;
```

## <a name="csmartdockinginfom_uimarkerlightbmpresid"></a><a name="m_uimarkerlightbmpresid"></a> CSmartDockingInfo：： m_uiMarkerLightBmpResID

定义用于突出显示的自定义智能停靠标记的位图的资源 Id。

```
UINT m_uiMarkerLightBmpResID[AFX_SD_MARKERS_NUM];
```

### <a name="remarks"></a>备注

用表示突出显示的智能停靠标记的位图的资源 Id 填充此数组。 AFX_SD_MARKERS_NUM 当前定义为5。 填充数组的方式如下：

```cpp
params.m_uiMarkerLightBmpResID[0] = IDB_MARKER_LEFT_LIGHT;
params.m_uiMarkerLightBmpResID[1] = IDB_MARKER_RIGHT_LIGHT;
params.m_uiMarkerLightBmpResID[2] = IDB_MARKER_TOP_LIGHT;
params.m_uiMarkerLightBmpResID[3] = IDB_MARKER_BOTTOM_LIGHT;
params.m_uiMarkerLightBmpResID[4] = IDB_MARKER_CENTER_LIGHT;
```

## <a name="see-also"></a>请参阅

[层次结构图](../../mfc/hierarchy-chart.md)<br/>
[Classes](../../mfc/reference/mfc-classes.md)<br/>
[CObject 类](../../mfc/reference/cobject-class.md)
