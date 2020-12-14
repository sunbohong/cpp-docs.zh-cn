---
description: 了解详细信息： CD2DTextLayout 类
title: CD2DTextLayout 类
ms.date: 03/27/2019
f1_keywords:
- CD2DTextLayout
- AFXRENDERTARGET/CD2DTextLayout
- AFXRENDERTARGET/CD2DTextLayout::CD2DTextLayout
- AFXRENDERTARGET/CD2DTextLayout::Create
- AFXRENDERTARGET/CD2DTextLayout::Destroy
- AFXRENDERTARGET/CD2DTextLayout::Get
- AFXRENDERTARGET/CD2DTextLayout::GetFontFamilyName
- AFXRENDERTARGET/CD2DTextLayout::GetLocaleName
- AFXRENDERTARGET/CD2DTextLayout::IsValid
- AFXRENDERTARGET/CD2DTextLayout::ReCreate
- AFXRENDERTARGET/CD2DTextLayout::SetFontFamilyName
- AFXRENDERTARGET/CD2DTextLayout::SetLocaleName
- AFXRENDERTARGET/CD2DTextLayout::m_pTextLayout
helpviewer_keywords:
- CD2DTextLayout [MFC], CD2DTextLayout
- CD2DTextLayout [MFC], Create
- CD2DTextLayout [MFC], Destroy
- CD2DTextLayout [MFC], Get
- CD2DTextLayout [MFC], GetFontFamilyName
- CD2DTextLayout [MFC], GetLocaleName
- CD2DTextLayout [MFC], IsValid
- CD2DTextLayout [MFC], ReCreate
- CD2DTextLayout [MFC], SetFontFamilyName
- CD2DTextLayout [MFC], SetLocaleName
- CD2DTextLayout [MFC], m_pTextLayout
ms.assetid: 724bd13c-f2ef-4e55-a775-8cb04b7b7908
ms.openlocfilehash: 164c8ed5561be6e8f9ee59b07d0aecaced5f7c81
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97240541"
---
# <a name="cd2dtextlayout-class"></a>CD2DTextLayout 类

IDWriteTextLayout 的包装器。

## <a name="syntax"></a>语法

```
class CD2DTextLayout : public CD2DResource;
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CD2DTextLayout：： CD2DTextLayout](#cd2dtextlayout)|构造 CD2DTextLayout 对象。|
|[CD2DTextLayout：： ~ CD2DTextLayout](#_dtorcd2dtextlayout)|析构函数。 当 D2D 文本布局对象被销毁时调用。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CD2DTextLayout：： Create](#create)|创建 CD2DTextLayout。  (重写 [CD2DResource：： Create](../../mfc/reference/cd2dresource-class.md#create). ) |
|[CD2DTextLayout：:D estroy](#destroy)|销毁 CD2DTextLayout 对象。  (重写 [CD2DResource：:D estroy](../../mfc/reference/cd2dresource-class.md#destroy)。 ) |
|[CD2DTextLayout：： Get](#get)|返回 IDWriteTextLayout 接口|
|[CD2DTextLayout：： GetFontFamilyName](#getfontfamilyname)|复制指定位置的文本的字体系列名称。|
|[CD2DTextLayout：： GetLocaleName](#getlocalename)|获取指定位置处的文本的区域设置名称。|
|[CD2DTextLayout：： IsValid](#isvalid)|检查资源有效性 (重写 [CD2DResource：： IsValid](../../mfc/reference/cd2dresource-class.md#isvalid). ) |
|[CD2DTextLayout：：重新创建](#recreate)|重新创建 CD2DTextLayout。  (重写 [CD2DResource：：重新创建](../../mfc/reference/cd2dresource-class.md#recreate)。 ) |
|[CD2DTextLayout：： SetFontFamilyName](#setfontfamilyname)|为指定文本范围内的文本设置以 null 结尾的字体系列名称|
|[CD2DTextLayout：： SetLocaleName](#setlocalename)|为指定文本范围内的文本设置区域设置名称|

### <a name="public-operators"></a>公共运算符

|名称|描述|
|----------|-----------------|
|[CD2DTextLayout：： operator IDWriteTextLayout *](#operator_idwritetextlayout_star)|返回 IDWriteTextLayout 接口|

### <a name="protected-data-members"></a>受保护的数据成员

|名称|描述|
|----------|-----------------|
|[CD2DTextLayout：： m_pTextLayout](#m_ptextlayout)|指向 IDWriteTextLayout 的指针。|

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

[CD2DResource](../../mfc/reference/cd2dresource-class.md)

[CD2DTextLayout](../../mfc/reference/cd2dtextlayout-class.md)

## <a name="requirements"></a>要求

**标头：** afxrendertarget

## <a name="cd2dtextlayoutcd2dtextlayout"></a><a name="_dtorcd2dtextlayout"></a> CD2DTextLayout：： ~ CD2DTextLayout

析构函数。 当 D2D 文本布局对象被销毁时调用。

```
virtual ~CD2DTextLayout();
```

## <a name="cd2dtextlayoutcd2dtextlayout"></a><a name="cd2dtextlayout"></a> CD2DTextLayout：： CD2DTextLayout

构造 CD2DTextLayout 对象。

```
CD2DTextLayout(
    CRenderTarget* pParentTarget,
    const CString& strText,
    CD2DTextFormat& textFormat,
    const CD2DSizeF& sizeMax,
    BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>parameters

*pParentTarget*<br/>
指向呈现器目标的指针。

*strText*<br/>
一个 CString 对象，其中包含用于创建新 CD2DTextLayout 对象的字符串。

*textFormat*<br/>
一个 CString 对象，其中包含要应用于字符串的格式。

*sizeMax*<br/>
布局框的大小。

*bAutoDestroy*<br/>
指示对象将被所有者 (pParentTarget) 销毁。

## <a name="cd2dtextlayoutcreate"></a><a name="create"></a> CD2DTextLayout：： Create

创建 CD2DTextLayout。

```
virtual HRESULT Create(CRenderTarget* */);
```

### <a name="return-value"></a>返回值

如果该方法成功，则它会返回 S_OK。 否则，它将返回 HRESULT 错误代码。

## <a name="cd2dtextlayoutdestroy"></a><a name="destroy"></a> CD2DTextLayout：:D estroy

销毁 CD2DTextLayout 对象。

```
virtual void Destroy();
```

## <a name="cd2dtextlayoutget"></a><a name="get"></a> CD2DTextLayout：： Get

返回 IDWriteTextLayout 接口

```
IDWriteTextLayout* Get();
```

### <a name="return-value"></a>返回值

指向 IDWriteTextLayout 接口的指针; 如果对象尚未初始化，则为 NULL。

## <a name="cd2dtextlayoutgetfontfamilyname"></a><a name="getfontfamilyname"></a> CD2DTextLayout：： GetFontFamilyName

复制指定位置的文本的字体系列名称。

```
CString GetFontFamilyName(
    UINT32 currentPosition,
    DWRITE_TEXT_RANGE* textRange = NULL) const;
```

### <a name="parameters"></a>parameters

*currentPosition*<br/>
要检查的文本的位置。

*textRange*<br/>
与 currentPosition 指定的位置上的文本格式相同的文本范围。 这意味着运行的格式与指定位置的格式完全相同，包括但不限于字体系列名称。

### <a name="return-value"></a>返回值

包含当前字体系列名称的 CString 对象。

## <a name="cd2dtextlayoutgetlocalename"></a><a name="getlocalename"></a> CD2DTextLayout：： GetLocaleName

获取指定位置处的文本的区域设置名称。

```
CString GetLocaleName(
    UINT32 currentPosition,
    DWRITE_TEXT_RANGE* textRange = NULL) const;
```

### <a name="parameters"></a>parameters

*currentPosition*<br/>
要检查的文本的位置。

*textRange*<br/>
与 currentPosition 指定的位置上的文本格式相同的文本范围。 这意味着运行的格式与指定位置的格式完全相同，包括但不限于区域设置名称。

### <a name="return-value"></a>返回值

包含当前区域设置名称的 CString 对象。

## <a name="cd2dtextlayoutisvalid"></a><a name="isvalid"></a> CD2DTextLayout：： IsValid

检查资源有效性

```
virtual BOOL IsValid() const;
```

### <a name="return-value"></a>返回值

如果资源有效，则为 TRUE;否则为 FALSE。

## <a name="cd2dtextlayoutm_ptextlayout"></a><a name="m_ptextlayout"></a> CD2DTextLayout：： m_pTextLayout

指向 IDWriteTextLayout 的指针。

```
IDWriteTextLayout* m_pTextLayout;
```

## <a name="cd2dtextlayoutoperator-idwritetextlayout"></a><a name="operator_idwritetextlayout_star"></a> CD2DTextLayout：： operator IDWriteTextLayout *

返回 IDWriteTextLayout 接口

```
operator IDWriteTextLayout*();
```

### <a name="return-value"></a>返回值

指向 IDWriteTextLayout 接口的指针; 如果对象尚未初始化，则为 NULL。

## <a name="cd2dtextlayoutrecreate"></a><a name="recreate"></a> CD2DTextLayout：：重新创建

重新创建 CD2DTextLayout。

```
virtual HRESULT ReCreate(CRenderTarget* */);
```

### <a name="return-value"></a>返回值

如果该方法成功，则它会返回 S_OK。 否则，它将返回 HRESULT 错误代码。

## <a name="cd2dtextlayoutsetfontfamilyname"></a><a name="setfontfamilyname"></a> CD2DTextLayout：： SetFontFamilyName

为指定文本范围内的文本设置以 null 结尾的字体系列名称

```
BOOL SetFontFamilyName(
    LPCWSTR pwzFontFamilyName,
    DWRITE_TEXT_RANGE textRange);
```

### <a name="parameters"></a>parameters

*pwzFontFamilyName*<br/>
应用于 textRange 指定范围内的整个文本字符串的字体系列名称

*textRange*<br/>
应用此更改的文本范围

### <a name="return-value"></a>返回值

如果该方法成功，则返回 TRUE。 否则，返回 FALSE

## <a name="cd2dtextlayoutsetlocalename"></a><a name="setlocalename"></a> CD2DTextLayout：： SetLocaleName

为指定文本范围内的文本设置区域设置名称

```
BOOL SetLocaleName(
    LPCWSTR pwzLocaleName,
    DWRITE_TEXT_RANGE textRange);
```

### <a name="parameters"></a>parameters

*pwzLocaleName*<br/>
以 null 值结束的区域设置名称字符串

*textRange*<br/>
应用此更改的文本范围

### <a name="return-value"></a>返回值

如果该方法成功，则返回 TRUE。 否则，返回 FALSE

## <a name="see-also"></a>请参阅

[类](../../mfc/reference/mfc-classes.md)
