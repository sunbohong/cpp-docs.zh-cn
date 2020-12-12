---
description: 了解详细信息： CD2DBrushProperties 类
title: CD2DBrushProperties 类
ms.date: 11/04/2016
f1_keywords:
- CD2DBrushProperties
- AFXRENDERTARGET/CD2DBrushProperties
- AFXRENDERTARGET/CD2DBrushProperties::CD2DBrushProperties
- AFXRENDERTARGET/CD2DBrushProperties::CommonInit
helpviewer_keywords:
- CD2DBrushProperties [MFC], CD2DBrushProperties
- CD2DBrushProperties [MFC], CommonInit
ms.assetid: c77d717f-0a16-4d74-b2ce-0ae1766ed6f9
ms.openlocfilehash: d16d08041b5096c8a5ad188201c6a06e21681849
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97227554"
---
# <a name="cd2dbrushproperties-class"></a>CD2DBrushProperties 类

`D2D1_BRUSH_PROPERTIES`的包装器。

## <a name="syntax"></a>语法

```
class CD2DBrushProperties : public D2D1_BRUSH_PROPERTIES;
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CD2DBrushProperties：： CD2DBrushProperties](#cd2dbrushproperties)|已重载。 创建 `CD2D_BRUSH_PROPERTIES` 结构|

### <a name="protected-methods"></a>受保护的方法

|名称|描述|
|----------|-----------------|
|[CD2DBrushProperties：： CommonInit](#commoninit)|初始化对象|

## <a name="inheritance-hierarchy"></a>继承层次结构

`D2D1_BRUSH_PROPERTIES`

`CD2DBrushProperties`

## <a name="requirements"></a>要求

**标头：** afxrendertarget

## <a name="cd2dbrushpropertiescd2dbrushproperties"></a><a name="cd2dbrushproperties"></a> CD2DBrushProperties：： CD2DBrushProperties

创建 CD2D_BRUSH_PROPERTIES 结构

```
CD2DBrushProperties();
CD2DBrushProperties(FLOAT _opacity);

CD2DBrushProperties(
    D2D1_MATRIX_3X2_F _transform,
    FLOAT _opacity = 1.);
```

### <a name="parameters"></a>parameters

*_opacity*<br/>
画笔的基本不透明度。 默认值为 1.0。

*_transform*<br/>
要应用于画笔的转换

## <a name="cd2dbrushpropertiescommoninit"></a><a name="commoninit"></a> CD2DBrushProperties：： CommonInit

初始化对象

```cpp
void CommonInit();
```

## <a name="see-also"></a>请参阅

[类](../../mfc/reference/mfc-classes.md)
