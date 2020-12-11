---
description: 了解有关以下内容的详细信息： &lt; istream &gt; 函数
title: '&lt;istream&gt; 函数'
ms.date: 11/04/2016
f1_keywords:
- istream/std::swap
- istream/std::ws
ms.assetid: 0301ea0d-4ded-4841-83dd-4253b55b3188
ms.openlocfilehash: c71770d8c6e86829eb4e0153abc924d612d3eff6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97154170"
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

### <a name="parameters"></a>parameters

*左中*\
一个流。

*然后*\
一个流。

## <a name="ws"></a><a name="ws"></a> ws

跳过流中的空白。

```cpp
template class<Elem, Tr> basic_istream<Elem, Tr>& ws(basic_istream<Elem, Tr>& _Istr);
```

### <a name="parameters"></a>parameters

*_Istr*\
一个流。

### <a name="return-value"></a>返回值

流。

### <a name="remarks"></a>备注

操控器提取并丢弃 `ch` [use_facet](../standard-library/basic-filebuf-class.md#open) <  **ctype** \< **Elem**> > ( [getloc](../standard-library/ios-base-class.md#getloc)) 的任何元素。 **(** **ctype** \< **Elem**> ：： **space**、 **ch**) 为 true。

此函数如果在提取元素时遇到文件末尾，则会调用 [setstate](../standard-library/basic-ios-class.md#setstate)( **eofbit**)。 它将返回 *_Istr*。

### <a name="example"></a>示例

有关使用 `ws` 的示例，请参阅 [operator>>](../standard-library/istream-operators.md#op_gt_gt)。

## <a name="see-also"></a>请参阅

[\<istream>](../standard-library/istream.md)
