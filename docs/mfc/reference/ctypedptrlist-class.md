---
description: 了解详细信息： CTypedPtrList 类
title: CTypedPtrList 类
ms.date: 11/04/2016
f1_keywords:
- CTypedPtrList
- AFXTEMPL/CTypedPtrList
- AFXTEMPL/CTypedPtrList::AddHead
- AFXTEMPL/CTypedPtrList::AddTail
- AFXTEMPL/CTypedPtrList::GetAt
- AFXTEMPL/CTypedPtrList::GetHead
- AFXTEMPL/CTypedPtrList::GetNext
- AFXTEMPL/CTypedPtrList::GetPrev
- AFXTEMPL/CTypedPtrList::GetTail
- AFXTEMPL/CTypedPtrList::RemoveHead
- AFXTEMPL/CTypedPtrList::RemoveTail
- AFXTEMPL/CTypedPtrList::SetAt
helpviewer_keywords:
- CTypedPtrList [MFC], AddHead
- CTypedPtrList [MFC], AddTail
- CTypedPtrList [MFC], GetAt
- CTypedPtrList [MFC], GetHead
- CTypedPtrList [MFC], GetNext
- CTypedPtrList [MFC], GetPrev
- CTypedPtrList [MFC], GetTail
- CTypedPtrList [MFC], RemoveHead
- CTypedPtrList [MFC], RemoveTail
- CTypedPtrList [MFC], SetAt
ms.assetid: c273096e-1756-4340-864b-4a08b674a65e
ms.openlocfilehash: 353e9af00b1366b260ce3cb3689018a8e4e370c1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97318528"
---
# <a name="ctypedptrlist-class"></a>CTypedPtrList 类

为 `CPtrList`类的对象提供安全类型“包装器”。

## <a name="syntax"></a>语法

```
template<class BASE_CLASS, class TYPE>
class CTypedPtrList : public BASE_CLASS
```

#### <a name="parameters"></a>parameters

*BASE_CLASS*<br/>
类型化指针列表类的基类;必须是一个指针列表类 ( `CObList` 或 `CPtrList`) 。

*TYPE*<br/>
基类列表中存储的元素的类型。

## <a name="members"></a>成员

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CTypedPtrList：： AddHead](#addhead)|将一个元素 (或另一个列表中的所有元素) 添加到列表的开头 (会成为新的 head) 。|
|[CTypedPtrList：： AddTail](#addtail)|将一个元素 (或另一个列表中的所有元素) 添加到列表的尾部 (会生成新的尾部) 。|
|[CTypedPtrList：： GetAt](#getat)|获取给定位置处的元素。|
|[CTypedPtrList：： GetHead](#gethead)|返回 (不能为空) 列表的头元素。|
|[CTypedPtrList：： GetNext](#getnext)|获取用于循环访问的下一个元素。|
|[CTypedPtrList：： GetPrev](#getprev)|获取用于循环访问的上一个元素。|
|[CTypedPtrList：： GetTail](#gettail)|返回列表的尾元素， (不能为空) 。|
|[CTypedPtrList：： RemoveHead](#removehead)|从列表头中删除元素。|
|[CTypedPtrList：： RemoveTail](#removetail)|从列表的末尾移除元素。|
|[CTypedPtrList：： SetAt](#setat)|设置位于给定位置的元素。|

## <a name="remarks"></a>备注

当你使用 `CTypedPtrList` 而不是时 `CObList` `CPtrList` ，c + + 类型检查功能可帮助消除不匹配指针类型引起的错误。

此外， `CTypedPtrList` 如果您使用了或，则包装将执行很多强制转换 `CObList` `CPtrList` 。

由于所有 `CTypedPtrList` 函数都是内联的，因此，使用此模板并不会对代码的大小或速度产生重大影响。

从派生的列表 `CObList` 可以进行序列化，但派生自的列表 `CPtrList` 不能。

当删除 `CTypedPtrList` 对象或其元素时，仅删除指针而不是指针引用的实体。

有关使用的详细信息 `CTypedPtrList` ，请参阅文章 [集合](../../mfc/collections.md) 和 [基于模板的类](../../mfc/template-based-classes.md)。

## <a name="example"></a>示例

此示例将创建一个实例 `CTypedPtrList` ，添加一个对象，将列表序列化到磁盘，然后删除该对象：

[!code-cpp[NVC_MFCCollections#110](../../mfc/codesnippet/cpp/ctypedptrlist-class_1.cpp)]

[!code-cpp[NVC_MFCCollections#111](../../mfc/codesnippet/cpp/ctypedptrlist-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>继承层次结构

`BASE_CLASS`

`_CTypedPtrList`

`CTypedPtrList`

## <a name="requirements"></a>要求

**标头：** afxtempl.h

## <a name="ctypedptrlistaddhead"></a><a name="addhead"></a> CTypedPtrList：： AddHead

此成员函数调用 `BASE_CLASS` **：： AddHead**。

```
POSITION AddHead(TYPE newElement);
void AddHead(CTypedPtrList<BASE_CLASS, TYPE>* pNewList);
```

### <a name="parameters"></a>parameters

*TYPE*<br/>
基类列表中存储的元素的类型。

*（Newelement*<br/>
要添加到此列表中的对象指针。 允许空值。

*BASE_CLASS*<br/>
类型化指针列表类的基类;必须是指针列表类 ( [CObList](../../mfc/reference/coblist-class.md) 或 [CPtrList](../../mfc/reference/cptrlist-class.md)) 。

*pNewList*<br/>
指向另一个 [CTypedPtrList](../../mfc/reference/ctypedptrlist-class.md) 对象的指针。 *PNewList* 中的元素将添加到此列表中。

### <a name="return-value"></a>返回值

第一个版本返回新插入元素的位置值。

### <a name="remarks"></a>备注

第一个版本在列表的开头添加一个新元素。 第二个版本在头前面添加了另一个元素列表。

## <a name="ctypedptrlistaddtail"></a><a name="addtail"></a> CTypedPtrList：： AddTail

此成员函数调用 `BASE_CLASS` **：： AddTail**。

```
POSITION AddTail(TYPE newElement);
void AddTail(CTypedPtrList<BASE_CLASS, TYPE>* pNewList);
```

### <a name="parameters"></a>parameters

*TYPE*<br/>
基类列表中存储的元素的类型。

*（Newelement*<br/>
要添加到此列表中的对象指针。 允许空值。

*BASE_CLASS*<br/>
类型化指针列表类的基类;必须是指针列表类 ( [CObList](../../mfc/reference/coblist-class.md) 或 [CPtrList](../../mfc/reference/cptrlist-class.md)) 。

*pNewList*<br/>
指向另一个 [CTypedPtrList](../../mfc/reference/ctypedptrlist-class.md) 对象的指针。 *PNewList* 中的元素将添加到此列表中。

### <a name="return-value"></a>返回值

第一个版本返回新插入元素的位置值。

### <a name="remarks"></a>备注

第一个版本在列表的末尾后面添加一个新元素。 第二个版本在列表的结尾之后添加另一个元素列表。

## <a name="ctypedptrlistgetat"></a><a name="getat"></a> CTypedPtrList：： GetAt

POSITION 类型的变量是列表的键。

```
TYPE& GetAt(POSITION position);
TYPE GetAt(POSITION position) const;
```

### <a name="parameters"></a>parameters

*TYPE*<br/>
指定存储在列表中的元素类型的模板参数。

*position*<br/>
由 previous `GetHeadPosition` 或成员函数调用返回的位置值 `Find` 。

### <a name="return-value"></a>返回值

如果通过指向的指针访问列表 `const CTypedPtrList` ，则 `GetAt` 返回由模板参数 *类型* 指定的类型的指针。 这只允许在赋值语句右侧使用该函数，从而保护列表不被修改。

如果直接访问该列表或通过指向的指针访问该列表 `CTypedPtrList` ，则 `GetAt` 返回对由模板参数 *类型* 指定的类型的指针的引用。 这允许将函数用于赋值语句的任意一侧，从而允许修改列表项。

### <a name="remarks"></a>备注

它与索引不同，不能自行操作位置值。 `GetAt` 检索 `CObject` 与给定位置关联的指针。

您必须确保您的位置值表示列表中的有效位置。 如果无效，则 Microsoft 基础类库断言的调试版本。

此内联函数调用 `BASE_CLASS` **：： GetAt**。

## <a name="ctypedptrlistgethead"></a><a name="gethead"></a> CTypedPtrList：： GetHead

获取表示此列表头元素的指针。

```
TYPE& GetHead();
TYPE GetHead() const;
```

### <a name="parameters"></a>parameters

*TYPE*<br/>
指定存储在列表中的元素类型的模板参数。

### <a name="return-value"></a>返回值

如果通过指向的指针访问列表 `const CTypedPtrList` ，则 `GetHead` 返回由模板参数 *类型* 指定的类型的指针。 这只允许在赋值语句右侧使用该函数，从而保护列表不被修改。

如果直接访问该列表或通过指向的指针访问该列表 `CTypedPtrList` ，则 `GetHead` 返回对由模板参数 *类型* 指定的类型的指针的引用。 这允许将函数用于赋值语句的任意一侧，从而允许修改列表项。

### <a name="remarks"></a>备注

在调用之前，必须确保列表不为空 `GetHead` 。 如果列表为空，则 Microsoft 基础类库断言的调试版本。 使用 [IsEmpty](../../mfc/reference/coblist-class.md#isempty) 验证列表中是否包含元素。

## <a name="ctypedptrlistgetnext"></a><a name="getnext"></a> CTypedPtrList：： GetNext

获取由 *rPosition* 标识的列表元素，然后将 *rPosition* 设置为列表中下一项的位置值。

```
TYPE& GetNext(POSITION& rPosition);
TYPE GetNext(POSITION& rPosition) const;
```

### <a name="parameters"></a>parameters

*TYPE*<br/>
指定此列表中包含的元素类型的模板参数。

*rPosition*<br/>
对上一个 `GetNext` 、 `GetHeadPosition` 或其他成员函数调用返回的位置值的引用。

### <a name="return-value"></a>返回值

如果通过指向的指针访问列表 `const CTypedPtrList` ，则 `GetNext` 返回由模板参数 *类型* 指定的类型的指针。 这只允许在赋值语句右侧使用该函数，从而保护列表不被修改。

如果直接访问该列表或通过指向的指针访问该列表 `CTypedPtrList` ，则 `GetNext` 返回对由模板参数 *类型* 指定的类型的指针的引用。 这允许将函数用于赋值语句的任意一侧，从而允许修改列表项。

### <a name="remarks"></a>备注

`GetNext`如果通过调用 `GetHeadPosition` 或[CPtrList：： Find](../../mfc/reference/coblist-class.md#find)建立初始位置，则可以在向前迭代循环中使用。

您必须确保您的位置值表示列表中的有效位置。 如果无效，则 Microsoft 基础类库断言的调试版本。

如果检索到的元素是列表中的最后一个，则 *rPosition* 的新值将设置为 NULL。

可以在迭代期间删除某个元素。 请参阅 [CObList：： RemoveAt](../../mfc/reference/coblist-class.md#removeat)的示例。

## <a name="ctypedptrlistgetprev"></a><a name="getprev"></a> CTypedPtrList：： GetPrev

获取由 *rPosition* 标识的列表元素，然后将 *rPosition* 设置为列表中上一项的位置值。

```
TYPE& GetPrev(POSITION& rPosition);
TYPE GetPrev(POSITION& rPosition) const;
```

### <a name="parameters"></a>parameters

*TYPE*<br/>
指定此列表中包含的元素类型的模板参数。

*rPosition*<br/>
对上一个 `GetPrev` 或其他成员函数调用返回的位置值的引用。

### <a name="return-value"></a>返回值

如果通过指向的指针访问列表 `const CTypedPtrList` ，则 `GetPrev` 返回由模板参数 *类型* 指定的类型的指针。 这只允许在赋值语句右侧使用该函数，从而保护列表不被修改。

如果直接访问该列表或通过指向的指针访问该列表 `CTypedPtrList` ，则 `GetPrev` 返回对由模板参数 *类型* 指定的类型的指针的引用。 这允许将函数用于赋值语句的任意一侧，从而允许修改列表项。

### <a name="remarks"></a>备注

`GetPrev`如果使用或调用建立初始位置，则可以在反向迭代循环中使用 `GetTailPosition` `Find` 。

您必须确保您的位置值表示列表中的有效位置。 如果无效，则 Microsoft 基础类库断言的调试版本。

如果检索到的元素是列表中的第一个元素，则 *rPosition* 的新值将设置为 NULL。

## <a name="ctypedptrlistgettail"></a><a name="gettail"></a> CTypedPtrList：： GetTail

获取表示此列表头元素的指针。

```
TYPE& GetTail();
TYPE GetTail() const;
```

### <a name="parameters"></a>parameters

*TYPE*<br/>
指定存储在列表中的元素类型的模板参数。

### <a name="return-value"></a>返回值

如果通过指向的指针访问列表 `const CTypedPtrList` ，则 `GetTail` 返回由模板参数 *类型* 指定的类型的指针。 这只允许在赋值语句右侧使用该函数，从而保护列表不被修改。

如果直接访问该列表或通过指向的指针访问该列表 `CTypedPtrList` ，则 `GetTail` 返回对由模板参数 *类型* 指定的类型的指针的引用。 这允许将函数用于赋值语句的任意一侧，从而允许修改列表项。

### <a name="remarks"></a>备注

在调用之前，必须确保列表不为空 `GetTail` 。 如果列表为空，则 Microsoft 基础类库断言的调试版本。 使用 [IsEmpty](../../mfc/reference/coblist-class.md#isempty) 验证列表中是否包含元素。

## <a name="ctypedptrlistremovehead"></a><a name="removehead"></a> CTypedPtrList：： RemoveHead

从列表头中删除元素并将其返回。

```
TYPE RemoveHead();
```

### <a name="parameters"></a>parameters

*TYPE*<br/>
指定存储在列表中的元素类型的模板参数。

### <a name="return-value"></a>返回值

之前位于列表的开头的指针。 此指针的类型由模板参数 *类型* 指定。

### <a name="remarks"></a>备注

在调用之前，必须确保列表不为空 `RemoveHead` 。 如果列表为空，则 Microsoft 基础类库断言的调试版本。 使用 [IsEmpty](../../mfc/reference/coblist-class.md#isempty) 验证列表中是否包含元素。

## <a name="ctypedptrlistremovetail"></a><a name="removetail"></a> CTypedPtrList：： RemoveTail

删除列表末尾的元素，并返回该元素。

```
TYPE RemoveTail();
```

### <a name="parameters"></a>parameters

*TYPE*<br/>
指定存储在列表中的元素类型的模板参数。

### <a name="return-value"></a>返回值

位于列表末尾的指针。 此指针的类型由模板参数 *类型* 指定。

### <a name="remarks"></a>备注

在调用之前，必须确保列表不为空 `RemoveTail` 。 如果列表为空，则 Microsoft 基础类库断言的调试版本。 使用 [IsEmpty](../../mfc/reference/coblist-class.md#isempty) 验证列表中是否包含元素。

## <a name="ctypedptrlistsetat"></a><a name="setat"></a> CTypedPtrList：： SetAt

此成员函数调用 `BASE_CLASS` **：： SetAt**。

```cpp
void SetAt(POSITION pos, TYPE newElement);
```

### <a name="parameters"></a>参数

pos<br/>
要设置的元素的位置。

*TYPE*<br/>
基类列表中存储的元素的类型。

*（Newelement*<br/>
要写入到列表中的对象指针。

### <a name="remarks"></a>备注

POSITION 类型的变量是列表的键。 它与索引不同，不能自行操作位置值。 `SetAt` 将对象指针写入到列表中的指定位置。

您必须确保您的位置值表示列表中的有效位置。 如果无效，则 Microsoft 基础类库断言的调试版本。

有关更详细的说明，请参阅 [CObList：： SetAt](../../mfc/reference/coblist-class.md#setat)。

## <a name="see-also"></a>请参阅

[MFC 示例收集](../../overview/visual-cpp-samples.md)<br/>
[层次结构图](../../mfc/hierarchy-chart.md)<br/>
[CPtrList 类](../../mfc/reference/cptrlist-class.md)<br/>
[CObList 类](../../mfc/reference/coblist-class.md)
