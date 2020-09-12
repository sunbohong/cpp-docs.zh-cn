---
title: ATL 集合类概述
ms.date: 11/19/2018
helpviewer_keywords:
- DestructElements function
- collection classes, choosing
- ConstructElements function
- SerializeElements function
- traits classes
- collection classes, about collection classes
- CTraits classes
- collection classes
ms.assetid: 4d619d46-5b4e-41dd-b9fd-e86b1fbc00b5
ms.openlocfilehash: 039af388a3713540c6ba7d39e8b639cf83d291ff
ms.sourcegitcommit: 6280a4c629de0f638ebc2edd446de2a9b11f0406
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/12/2020
ms.locfileid: "90040855"
---
# <a name="atl-collection-classes"></a>ATL 集合类

ATL 提供了许多用于存储和访问数据的类。 您决定使用哪个类取决于多个因素，包括：

- 要存储的数据量

- 访问数据时的效率与性能

- 按索引或按键访问数据的功能

- 如何对数据进行排序

- 个人首选项

## <a name="small-collection-classes"></a>小型集合类

ATL 提供以下用于处理少量对象的数组类。 但是，这些类受到限制，并专用于 ATL 内部使用。 不建议在程序中使用它们。

|类|数据存储类型|
|-----------|--------------------------|
|[CSimpleArray](../atl/reference/csimplearray-class.md)|实现一个用于处理少量对象的数组类。|
|[CSimpleMap](../atl/reference/csimplemap-class.md)|实现用于处理少量对象的映射类。|

## <a name="general-purpose-collection-classes"></a>常规用途集合类

以下类实现数组、列表和映射，并作为常规用途集合类提供：

|类|数据存储类型|
|-----------|--------------------------|
|[CAtlArray](../atl/reference/catlarray-class.md)|实现数组。|
|[CAtlList](../atl/reference/catllist-class.md)|实现列表。|
|[CAtlMap](../atl/reference/catlmap-class.md)|实现一个映射结构，通过该键或值来引用数据。|
|[CRBMap](../atl/reference/crbmap-class.md)|使用红黑色算法实现映射结构。|
|[CRBMultiMap](../atl/reference/crbmultimap-class.md)|实现 Red-黑色 multimapping 结构。|

在调试版本中使用时，这些类将捕获许多编程错误，但为了提高性能，将不会在零售版本中执行这些检查。

## <a name="specialized-collection-classes"></a>专用集合类

还提供了更多专用集合类用于管理内存指针和接口指针：

|类|目的|
|-----------|-------------|
|[CAutoPtrArray](../atl/reference/cautoptrarray-class.md)|提供在构造智能指针数组时有用的方法。|
|[CAutoPtrList](../atl/reference/cautoptrlist-class.md)|提供在构造智能指针列表时有用的方法。|
|[CComUnkArray](../atl/reference/ccomunkarray-class.md)|存储 `IUnknown` 指针，旨在用作 [IConnectionPointImpl](../atl/reference/iconnectionpointimpl-class.md) 模板类的参数。|
|[CHeapPtrList](../atl/reference/cheapptrlist-class.md)|提供在构造堆指针列表时有用的方法。|
|[CInterfaceArray](../atl/reference/cinterfacearray-class.md)|提供在构造 COM 接口指针数组时有用的方法。|
|[CInterfaceList](../atl/reference/cinterfacelist-class.md)|提供在构造 COM 接口指针列表时有用的方法。|

## <a name="choosing-a-collection-class"></a>选择集合类

每个可用的集合类都提供不同的性能特征，如下表所示。

- 列2和3描述了每个类的排序和访问特性。 在表中，术语“决定顺序”是指插入和删除项的顺序决定其在集合中的顺序；不是指项在其内容中的排序。 术语“索引检索”是指集合中的项可通过整数索引进行检索，这与典型数组中的项很相似。

- 列4和5描述了每个类的性能。 在需要多次插入集合的应用程序中，插入速度可能特别重要；而对于其他应用程序，查找速度可能更为重要。

- 列 6 描述了每个形状是否允许重复元素。

- 给定集合类操作的性能以完成操作所需的时间与集合中的元素数之间的关系表示。 如果操作所用的时间量随着元素数量的增加而线性增加，则会将其描述为 O (n) 算法。 与此相反，如果操作所用的时间超过了元素数增加的时间，则会将其描述为 O (log n) 算法。 因此，在性能方面，O (log n) 算法优于 O (n) 算法随着元素数量的增加而越来越多。

### <a name="collection-shape-features"></a>Collection Shape Features（集合形状特征）

|形状|已订购|已编制索引|插入<br /><br /> element|搜索<br /><br /> 指定元素|复制<br /><br /> 元素|
|-----------|--------------|--------------|---------------------------|--------------------------------------|-----------------------------|
|列表|是|否|快速 (常量时间) |慢 O (n) |是|
|Array|是|按 int (常量时间) |慢 O (n) ，除非在结尾处插入，在这种情况下，常量时间|慢 O (n) |是|
|映射|否|按键 (常量时间) |快速 (常量时间) |快速 (常量时间) |否（键）是（值）|
|红色-黑色地图|是 (按键) |按键 O (日志 n) |Fast O (日志 n) |Fast O (日志 n) |否|
|红色-黑色多重映射|是 (按键) |按键 O (日志 n) 每个密钥 (多个值) |Fast O (日志 n) |Fast O (日志 n) |是 (每个键) 多个值|

## <a name="using-ctraits-objects"></a>使用 CTraits 对象

由于 ATL 集合类可用于存储各种用户定义的数据类型，因此能够替代重要函数（如比较）可能会很有用。 这是使用 CTraits 类实现的。

CTraits 类类似于 MFC 集合类 helper 函数，但更灵活：有关详细信息，请参阅 [集合类帮助](../mfc/reference/collection-class-helpers.md) 器。

构造集合类时，可以选择指定 CTraits 类。 此类将包含代码，这些代码将在由组成集合类的其他方法调用时执行运算，如比较。 例如，如果您的列表对象包含您自己的用户定义的结构，则可能需要重新定义相等性测试，以仅比较特定的成员变量。 这样，列表对象的 Find 方法将以更实用的方式运行。

## <a name="example"></a>示例

### <a name="code"></a>代码

[!code-cpp[NVC_ATL_Utilities#112](../atl/codesnippet/cpp/atl-collection-classes_1.cpp)]

## <a name="comments"></a>注释

有关 CTraits 类的列表，请参阅 [集合类](../atl/collection-classes.md)。

下图显示了 CTraits 类的类层次结构。

![集合类的特征层次结构](../atl/media/vctraitscollectionclasseshierarchy.gif "集合类的特征层次结构")

## <a name="collection-classes-samples"></a>集合类示例

下面的示例演示集合类：

- [MMXSwarm 示例](../overview/visual-cpp-samples.md)

- [DynamicConsumer 示例](../overview/visual-cpp-samples.md)

- [UpdatePV 示例](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/ATL/OLEDB/Provider/UPDATEPV)

- [天棚示例](../overview/visual-cpp-samples.md)

## <a name="see-also"></a>另请参阅

[概念](../atl/active-template-library-atl-concepts.md)<br/>
[集合类](../atl/collection-classes.md)
