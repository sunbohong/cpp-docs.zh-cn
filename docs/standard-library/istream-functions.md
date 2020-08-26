---
title: '&lt;istream&gt; 函数'
ms.date: 11/04/2016
f1_keywords:
- istream/std::swap
- istream/std::ws
ms.assetid: 0301ea0d-4ded-4841-83dd-4253b55b3188
ms.openlocfilehash: 6d1fede2726d3d8f5dd678b95fd7a22a301ea95a
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/25/2020
ms.locfileid: "88840968"
---
# <a name="ltistreamgt-functions"></a>&lt;istream&gt; 函数

[购](#istream_swap)\
[ws](#ws)

## <a name="swap"></a><a name="istream_swap"></a> 购

交换两个流对象的元素。

```cpp
template <class Elem, class Tr>
void swap(
    basic_istream<Elem, Tr>& left,
    basic_istream<Elem, Tr>& right);

template <class Elem, class Tr>
void swap(
    basic_iostream<Elem, Tr>& left,
    basic_iostream<Elem, Tr>& right);
```

### <a name="parameters"></a>参数

*左中*\
一个流。

*然后*\
一个流。

## <a name="ws"></a><a name="ws"></a> ws

跳过流中的空白。

```cpp
template class<Elem, Tr> basic_istream<Elem, Tr>& ws(basic_istream<Elem, Tr>& _Istr);
```

### <a name="parameters"></a>参数

*_Istr*\
一个流。

### <a name="return-value"></a>返回值

流。

### <a name="remarks"></a>注解

操控器提取并丢弃 `ch` [use_facet](../standard-library/basic-filebuf-class.md#open) <  **ctype** \< **Elem**> > ( [getloc](../standard-library/ios-base-class.md#getloc)) 的任何元素。 ** (** **ctype** \< **Elem**> ：： **space**、 **ch**) 为 true。

此函数如果在提取元素时遇到文件末尾，则会调用 [setstate](../standard-library/basic-ios-class.md#setstate)( **eofbit**)。 它将返回 *_Istr*。

### <a name="example"></a>示例

有关使用 `ws` 的示例，请参阅 [operator>>](../standard-library/istream-operators.md#op_gt_gt)。

## <a name="see-also"></a>另请参阅

[\<istream>](../standard-library/istream.md)
