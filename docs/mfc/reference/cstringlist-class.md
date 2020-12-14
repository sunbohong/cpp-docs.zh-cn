---
description: 了解详细信息： CStringList 类
title: CStringList 类
ms.date: 11/04/2016
f1_keywords:
- CStringList
- AFXCOLL/CStringList
- AFXCOLL/CStringList::CStringList
- AFXCOLL/CStringList::AddHead
- AFXCOLL/CStringList::AddTail
- AFXCOLL/CStringList::Find
- AFXCOLL/CStringList::FindIndex
- AFXCOLL/CStringList::GetAt
- AFXCOLL/CStringList::GetCount
- AFXCOLL/CStringList::GetHead
- AFXCOLL/CStringList::GetHeadPosition
- AFXCOLL/CStringList::GetNext
- AFXCOLL/CStringList::GetPrev
- AFXCOLL/CStringList::GetSize
- AFXCOLL/CStringList::GetTail
- AFXCOLL/CStringList::GetTailPosition
- AFXCOLL/CStringList::InsertAfter
- AFXCOLL/CStringList::InsertBefore
- AFXCOLL/CStringList::IsEmpty
- AFXCOLL/CStringList::RemoveAll
- AFXCOLL/CStringList::RemoveAt
- AFXCOLL/CStringList::RemoveHead
- AFXCOLL/CStringList::RemoveTail
- AFXCOLL/CStringList::SetAt
helpviewer_keywords:
- CStringList [MFC], CStringList
- CStringList [MFC], AddHead
- CStringList [MFC], AddTail
- CStringList [MFC], Find
- CStringList [MFC], FindIndex
- CStringList [MFC], GetAt
- CStringList [MFC], GetCount
- CStringList [MFC], GetHead
- CStringList [MFC], GetHeadPosition
- CStringList [MFC], GetNext
- CStringList [MFC], GetPrev
- CStringList [MFC], GetSize
- CStringList [MFC], GetTail
- CStringList [MFC], GetTailPosition
- CStringList [MFC], InsertAfter
- CStringList [MFC], InsertBefore
- CStringList [MFC], IsEmpty
- CStringList [MFC], RemoveAll
- CStringList [MFC], RemoveAt
- CStringList [MFC], RemoveHead
- CStringList [MFC], RemoveTail
- CStringList [MFC], SetAt
ms.assetid: 310a7edb-263c-4bd2-ac43-0bfbfddc5a33
ms.openlocfilehash: c9043ef648f50e880f3b5946c1912deca3de6714
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97345064"
---
# <a name="cstringlist-class"></a>CStringList 类

支持 `CString` 对象列表。

## <a name="syntax"></a>语法

```
class CStringList : public CObject
```

## <a name="members"></a>成员

的成员函数 `CStringList` 类似于类 [CObList](../../mfc/reference/coblist-class.md)的成员函数。 由于此相似性，因此你可以使用 `CObList` 参考文档获取成员函数细节。 无论你在何处看到 `CObject` 作为返回值的指针，都要用 `CString` (而不是 `CString` 指针) 。 无论你在何处看到 `CObject` 作为函数参数的指针，都将替换为 `LPCTSTR` 。

`CObject*& CObList::GetHead() const;`

例如，转换为

`CString& CStringList::GetHead() const;`

和

`POSITION AddHead( CObject* <newElement> );`

转换为

`POSITION AddHead( LPCTSTR <newElement> );`

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CStringList：： CStringList](../../mfc/reference/coblist-class.md#coblist)|构造一个空列表。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CStringList：： AddHead](../../mfc/reference/coblist-class.md#addhead)|将一个元素 (或另一个列表中的所有元素) 添加到列表的开头 (会成为新的 head) 。|
|[CStringList：： AddTail](../../mfc/reference/coblist-class.md#addtail)|将一个元素 (或另一个列表中的所有元素) 添加到列表的尾部 (会生成新的尾部) 。|
|[CStringList：： Find](../../mfc/reference/coblist-class.md#find)|获取由指针值指定的元素的位置。|
|[CStringList：： FindIndex](../../mfc/reference/coblist-class.md#findindex)|获取以零为基的索引指定的元素的位置。|
|[CStringList：： GetAt](../../mfc/reference/coblist-class.md#getat)|获取给定位置处的元素。|
|[CStringList：： GetCount](../../mfc/reference/coblist-class.md#getcount)|返回此列表中的元素数。|
|[CStringList：： GetHead](../../mfc/reference/coblist-class.md#gethead)|返回 (不能为空) 列表的头元素。|
|[CStringList：： GetHeadPosition](../../mfc/reference/coblist-class.md#getheadposition)|返回列表头元素的位置。|
|[CStringList：： GetNext](../../mfc/reference/coblist-class.md#getnext)|获取用于循环访问的下一个元素。|
|[CStringList：： GetPrev](../../mfc/reference/coblist-class.md#getprev)|获取用于循环访问的上一个元素。|
|[CStringList：： GetSize](../../mfc/reference/coblist-class.md#getsize)|返回此列表中的元素数。|
|[CStringList：： GetTail](../../mfc/reference/coblist-class.md#gettail)|返回列表的尾元素， (不能为空) 。|
|[CStringList：： GetTailPosition](../../mfc/reference/coblist-class.md#gettailposition)|返回列表的尾元素的位置。|
|[CStringList：： InsertAfter](../../mfc/reference/coblist-class.md#insertafter)|将新元素插入到给定位置之后。|
|[CStringList：： InsertBefore](../../mfc/reference/coblist-class.md#insertbefore)|将新元素插入到给定位置之前。|
|[CStringList：： IsEmpty](../../mfc/reference/coblist-class.md#isempty)|测试空列表条件 (不) 任何元素。|
|[CStringList：： RemoveAll](../../mfc/reference/coblist-class.md#removeall)|从此列表中移除所有元素。|
|[CStringList：： RemoveAt](../../mfc/reference/coblist-class.md#removeat)|从此列表中移除按位置指定的元素。|
|[CStringList：： RemoveHead](../../mfc/reference/coblist-class.md#removehead)|从列表头中删除元素。|
|[CStringList：： RemoveTail](../../mfc/reference/coblist-class.md#removetail)|从列表的末尾移除元素。|
|[CStringList：： SetAt](../../mfc/reference/coblist-class.md#setat)|设置位于给定位置的元素。|

## <a name="remarks"></a>备注

所有比较都是通过值来完成的，这意味着会比较字符串中的字符而不是字符串的地址。

`CStringList` 合并 IMPLEMENT_SERIAL 宏，以支持其元素的序列化和转储。 如果 `CString` 使用重载的插入运算符或成员函数将对象列表存储到存档， `Serialize` 则每个 `CString` 元素将依次序列化。

如果需要单个元素的转储 `CString` ，则必须将转储上下文的深度设置为1或更大。

有关使用的详细信息 `CStringList` ，请参阅文章 [集合](../../mfc/collections.md)。

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

`CStringList`

## <a name="requirements"></a>要求

**标头：** afxcoll。h

## <a name="see-also"></a>请参阅

[MFC 示例收集](../../overview/visual-cpp-samples.md)<br/>
[CObject 类](../../mfc/reference/cobject-class.md)<br/>
[层次结构图](../../mfc/hierarchy-chart.md)
