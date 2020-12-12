---
description: 了解详细信息：变量参数类型常量
title: 变量参数类型常量
ms.date: 11/04/2016
f1_keywords:
- VTS_YPOS_HIMETRIC
- VTS_PICTURE
- VTS_FONT
- VTS_XPOS_HIMETRIC
- VTS_XPOS_PIXELS
- VTS_XSIZE_HIMETRIC
- VTS_YPOS_PIXELS
- VTS_TRISTATE
- VTS_HANDLE
- VTS_YSIZE_HIMETRIC
- VTS_COLOR
- VTS_OPTEXCLUSIVE
- VTS_YSIZE_PIXELS
- VTS_XSIZE_PIXELS
helpviewer_keywords:
- VTS_XPOS_HIMETRIC constant [MFC]
- VTS_FONT constant [MFC]
- VTS_XPOS_PIXELS constant [MFC]
- VTS_COLOR constant [MFC]
- Variants [MFC]
- VTS_YPOS_PIXELS constant [MFC]
- VTS_YSIZE_HIMETRIC constant [MFC]
- VTS_YPOS_HIMETRIC constant [MFC]
- Variants, parameter type constants
- Variant data constants [MFC]
- VTS_PICTURE constant [MFC]
- VTS_TRISTATE constant [MFC]
- VTS_XSIZE_HIMETRIC constant [MFC]
- VTS_HANDLE constant [MFC]
- VTS_XSIZE_PIXELS constant [MFC]
- VTS_OPTEXCLUSIVE constant [MFC]
- VTS_YSIZE_PIXELS constant [MFC]
ms.assetid: de99c7a9-7aae-4dc4-b723-40c6380543ab
ms.openlocfilehash: 5bc3dcc8a0a888b21b88700db99b05c0f12a4c5e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97218493"
---
# <a name="variant-parameter-type-constants"></a>变量参数类型常量

本主题列出了一些新的常量，这些常量指示用于 Microsoft 基础类库的 OLE 控件类的变量类型。

下面是类常量的列表：

## <a name="variant-data-constants"></a><a name="_mfc_variant_data_constants"></a> 变量数据常量

- VTS_COLOR 一个32位整数，用于表示 RGB 颜色值。

- VTS_FONT 指向 `IFontDisp` OLE 字体对象的接口的指针。

- VTS_HANDLE Windows 句柄值。

- VTS_PICTURE 指向 `IPictureDisp` OLE 图片对象的接口的指针。

- VTS_OPTEXCLUSIVE 一个用于控件的16位值，该控件旨在用于一组控件，如单选按钮。 此类型通知容器如果组中的一个控件具有 TRUE 值，则所有其他控件必须为 FALSE。

- VTS_TRISTATE 一个16位带符号整数，这些属性可具有三个可能值之一 (选中、已清除、不可用) ，例如复选框。

- VTS_XPOS_HIMETRIC 一个32位无符号整数，该整数用于在 HIMETRIC 单元中沿 x 轴表示位置。

- VTS_YPOS_HIMETRIC 一个32位无符号整数，该整数用于以 HIMETRIC 单位表示沿 y 轴的位置。

- VTS_XPOS_PIXELS 一个32位无符号整数，该整数用于表示沿 x 轴的位置（以像素为单位）。

- VTS_YPOS_PIXELS 一个32位无符号整数，该整数用于表示沿 y 轴的位置（以像素为单位）。

- VTS_XSIZE_PIXELS 一个32位无符号整数，用于表示屏幕对象的宽度（以像素为单位）。

- VTS_YSIZE_PIXELS 一个32位无符号整数，用于表示屏幕对象的高度（以像素为单位）。

- VTS_XSIZE_HIMETRIC 一个32位无符号整数，用于表示 HIMETRIC 单元中的屏幕对象的宽度。

- VTS_YSIZE_HIMETRIC 一个32位无符号整数，用于表示 HIMETRIC 单位的屏幕对象的高度。

    > [!NOTE]
    >  已为所有变体类型定义了其他变体常量（VTS_FONT 和 VTS_PICTURE 除外），它们提供指向变量数据常量的指针。 这些常量是使用 VTS_P 约定命名的 `constantname` 。 例如，VTS_PCOLOR 是指向 VTS_COLOR 常量的指针。

## <a name="requirements"></a>要求

**标头：** afxdisp.h

## <a name="see-also"></a>请参阅

[MFC 宏和全局函数](../../mfc/reference/mfc-macros-and-globals.md)
