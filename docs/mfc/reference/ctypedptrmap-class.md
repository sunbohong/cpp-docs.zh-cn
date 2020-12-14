---
description: 了解详细信息： CTypedPtrMap 类
title: CTypedPtrMap Class
ms.date: 11/04/2016
f1_keywords:
- CTypedPtrMap
- AFXTEMPL/CTypedPtrMap
- AFXTEMPL/CTypedPtrMap::GetNextAssoc
- AFXTEMPL/CTypedPtrMap::Lookup
- AFXTEMPL/CTypedPtrMap::RemoveKey
- AFXTEMPL/CTypedPtrMap::SetAt
helpviewer_keywords:
- CTypedPtrMap [MFC], GetNextAssoc
- CTypedPtrMap [MFC], Lookup
- CTypedPtrMap [MFC], RemoveKey
- CTypedPtrMap [MFC], SetAt
ms.assetid: 9f377385-c6e9-4471-8b40-8fe220c50164
ms.openlocfilehash: 25476a9195fe4a522ed31937dc1e2c5156ef6792
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97344986"
---
# <a name="ctypedptrmap-class"></a>CTypedPtrMap Class

为 `CMapPtrToPtr`、 `CMapPtrToWord`、 `CMapWordToPtr`和 `CMapStringToPtr`指针映射类的对象提供安全类型“包装器”。

## <a name="syntax"></a>语法

```
template<class BASE_CLASS, class KEY, class VALUE>
class CTypedPtrMap : public BASE_CLASS
```

#### <a name="parameters"></a>parameters

*BASE_CLASS*<br/>
类型化指针映射类的基类;必须是指针映射类 ( `CMapPtrToPtr` 、 `CMapPtrToWord` 、 `CMapWordToPtr` 或 `CMapStringToPtr`) 。

*KEY*<br/>
用作映射键的对象的类。

*VALUE*<br/>
存储在映射中的对象的类。

## <a name="members"></a>成员

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CTypedPtrMap：： GetNextAssoc](#getnextassoc)|获取用于循环访问的下一个元素。|
|[CTypedPtrMap：： Lookup](#lookup)|返回 `KEY` 基于的 `VALUE` 。|
|[CTypedPtrMap：： RemoveKey](#removekey)|移除由键指定的元素。|
|[CTypedPtrMap：： SetAt](#setat)|将元素插入到映射中;如果找到匹配的键，则替换现有元素。|

### <a name="public-operators"></a>公共运算符

|名称|描述|
|----------|-----------------|
|[CTypedPtrMap：： operator \[\]](#operator_at)|将元素插入到映射中。|

## <a name="remarks"></a>备注

使用时 `CTypedPtrMap` ，c + + 类型检查功能可帮助消除不匹配的指针类型引起的错误。

由于所有 `CTypedPtrMap` 函数都是内联的，因此，使用此模板并不会对代码的大小或速度产生重大影响。

有关使用的详细信息 `CTypedPtrMap` ，请参阅文章 [集合](../../mfc/collections.md) 和 [基于模板的类](../../mfc/template-based-classes.md)。

## <a name="inheritance-hierarchy"></a>继承层次结构

`BASE_CLASS`

`CTypedPtrMap`

## <a name="requirements"></a>要求

**标头：** afxtempl.h

## <a name="ctypedptrmapgetnextassoc"></a><a name="getnextassoc"></a> CTypedPtrMap：： GetNextAssoc

检索中的 map 元素 `rNextPosition` ，然后更新 `rNextPosition` 以引用映射中的下一个元素。

```cpp
void GetNextAssoc(
    POSITION& rPosition,
    KEY& rKey,
    VALUE& rValue) const;
```

### <a name="parameters"></a>parameters

*rPosition*<br/>
指定对由 previous `GetNextAssoc` 或 `BASE_CLASS` **：： GetStartPosition** 调用返回的位置值的引用。

*KEY*<br/>
指定地图项类型的模板参数。

*rKey*<br/>
指定检索到的元素的返回键。

*VALUE*<br/>
指定地图值类型的模板参数。

*右值*<br/>
指定检索到的元素的返回值。

### <a name="remarks"></a>备注

此函数最适用于遍历映射中的所有元素。 请注意，位置序列不一定与键值序列相同。

如果检索到的元素是映射中的最后一个，则的新值将 `rNextPosition` 设置为 NULL。

此内联函数调用 `BASE_CLASS` **：： GetNextAssoc**。

## <a name="ctypedptrmaplookup"></a><a name="lookup"></a> CTypedPtrMap：： Lookup

`Lookup` 使用哈希算法快速查找具有完全匹配的键的 map 元素。

```
BOOL Lookup(BASE_CLASS ::BASE_ARG_KEY key, VALUE& rValue) const;
```

### <a name="parameters"></a>parameters

*BASE_CLASS*<br/>
指定此映射的类的基类的模板参数。

*key*<br/>
要查找的元素的键。

*VALUE*<br/>
指定存储在此映射中的值类型的模板参数。

*右值*<br/>
指定检索到的元素的返回值。

### <a name="return-value"></a>返回值

如果找到元素，则为非零值;否则为0。

### <a name="remarks"></a>备注

此内联函数调用 `BASE_CLASS` **：： Lookup**。

## <a name="ctypedptrmapoperator--"></a><a name="operator_at"></a> CTypedPtrMap：： operator []

此运算符仅可用于 (左值) 赋值语句的左侧。

```
VALUE& operator[ ](base_class ::base_arg_key key);
```

### <a name="parameters"></a>parameters

*VALUE*<br/>
指定存储在此映射中的值类型的模板参数。

*BASE_CLASS*<br/>
指定此映射的类的基类的模板参数。

*key*<br/>
要在映射中查找或创建的元素的键。

### <a name="remarks"></a>备注

如果没有具有指定键的 map 元素，则创建一个新元素。 由于可能在映射中找不到键，因此没有 "右边" (r-值) 与此运算符等效。 使用 `Lookup` 成员函数进行元素检索。

## <a name="ctypedptrmapremovekey"></a><a name="removekey"></a> CTypedPtrMap：： RemoveKey

此成员函数调用 `BASE_CLASS` **：： RemoveKey**。

```
BOOL RemoveKey(KEY key);
```

### <a name="parameters"></a>parameters

*KEY*<br/>
指定地图项类型的模板参数。

*key*<br/>
要移除的元素的键。

### <a name="return-value"></a>返回值

如果已找到并成功删除该项，则为非零值;否则为0。

### <a name="remarks"></a>备注

有关更详细的说明，请参阅 [CMapStringToOb：： RemoveKey](../../mfc/reference/cmapstringtoob-class.md#removekey)。

## <a name="ctypedptrmapsetat"></a><a name="setat"></a> CTypedPtrMap：： SetAt

此成员函数调用 `BASE_CLASS` **：： SetAt**。

```cpp
void SetAt(KEY key, VALUE newValue);
```

### <a name="parameters"></a>parameters

*KEY*<br/>
指定地图项类型的模板参数。

*key*<br/>
指定 newValue 的键值。

*newValue*<br/>
指定作为新元素的值的对象指针。

### <a name="remarks"></a>备注

有关更详细的说明，请参阅 [CMapStringToOb：： SetAt](../../mfc/reference/cmapstringtoob-class.md#setat)。

## <a name="see-also"></a>请参阅

[MFC 示例收集](../../overview/visual-cpp-samples.md)<br/>
[层次结构图](../../mfc/hierarchy-chart.md)<br/>
[CMapPtrToPtr 类](../../mfc/reference/cmapptrtoptr-class.md)<br/>
[CMapPtrToWord 类](../../mfc/reference/cmapptrtoword-class.md)<br/>
[CMapWordToPtr 类](../../mfc/reference/cmapwordtoptr-class.md)<br/>
[CMapStringToPtr 类](../../mfc/reference/cmapstringtoptr-class.md)
