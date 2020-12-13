---
description: 了解有关以下内容的详细信息：实现 c + + 标准 Library-Based 集合
title: 实现 c + + 标准 Library-Based 集合
ms.date: 11/04/2016
helpviewer_keywords:
- ICollectionOnSTLImpl interface
ms.assetid: 6d49f819-1957-4813-b074-3f12c494d8ca
ms.openlocfilehash: 4a403885a6fe66bf8e8578deeab05c7fc08e88a5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97152849"
---
# <a name="implementing-a-c-standard-library-based-collection"></a>实现 c + + 标准 Library-Based 集合

ATL 提供 `ICollectionOnSTLImpl` 接口，使你能够在对象上快速实现基于 c + + 标准库的集合接口。 若要了解此类的工作原理，你将完成下面的一个简单示例 () 使用此类实现一个针对自动化客户端的只读集合。

示例代码来自 [ATLCollections 示例](../overview/visual-cpp-samples.md)。

若要完成此过程，您需要：

- [生成新的简单对象](#vccongenerating_an_object)。

- 编辑生成的接口的[IDL 文件](#vcconedit_the_idl)。

- [创建五个 typedef](#vcconstorage_and_exposure_typedefs) ，描述如何存储收集项以及如何通过 COM 接口将这些项公开给客户端。

- [为复制策略类创建两个 typedef](#vcconcopy_classes)。

- [为枚举器和集合实现创建 typedef](#vcconenumeration_and_collection)。

- [编辑向导生成的 c + + 代码以使用集合 typedef](#vcconedit_the_generated_code)。

- [添加代码以填充集合](#vcconpopulate_the_collection)。

## <a name="generating-a-new-simple-object"></a><a name="vccongenerating_an_object"></a> 生成新的简单对象

创建一个新项目，确保清除 "应用程序设置" 下的 "属性" 框。 使用 "ATL 添加类" 对话框和 "添加简单对象向导" 生成一个名为的简单对象 `Words` 。 请确保已生成名为的双重接口 `IWords` 。 生成的类的对象将用于表示 (为) 的字符串的集合。

## <a name="editing-the-idl-file"></a><a name="vcconedit_the_idl"></a> 编辑 IDL 文件

现在，打开 IDL 文件并添加启用为只读集合接口所需的三个属性 `IWords` ，如下所示：

[!code-cpp[NVC_ATL_COM#24](../atl/codesnippet/cpp/implementing-an-stl-based-collection_1.idl)]

这是一种标准形式，适用于使用自动化客户端设计的只读集合接口。 此接口定义中的编号注释对应于下面的注释：

1. 集合接口通常是双重的，因为自动化客户端 `_NewEnum` 通过访问属性 `IDispatch::Invoke` 。 但是，自动化客户端可以通过 vtable 访问其余方法，因此双重接口比调度接口更好。

1. 如果在运行时不会扩展双重接口或调度接口 (即，你不能通过) 提供额外的方法或属性 `IDispatch::Invoke` ，则应将 **nonextensible** 特性应用于定义。 此特性使自动化客户端能够在编译时执行完整代码验证。 在这种情况下，不应扩展接口。

1. 如果希望自动化客户端能够使用此属性，则正确的 DISPID 非常重要。  (请注意，DISPID_NEWENUM 中只有一个下划线。 ) 

1. 可以提供任何值作为属性的 DISPID `Item` 。 但是， `Item` 通常使用 DISPID_VALUE 使其成为集合的默认属性。 这允许自动化客户端引用属性，而无需对其进行显式命名。

1. 此属性的返回值所使用的数据类型 `Item` 是与 COM 客户端相关的存储在集合中的项的类型。 接口返回字符串，因此应使用标准 COM 字符串类型 BSTR。 您可以在内部使用不同的格式存储数据，您很快就会看到。

1. 用于 DISPID 属性的值 `Count` 是完全任意的。 此属性没有标准 DISPID。

## <a name="creating-typedefs-for-storage-and-exposure"></a><a name="vcconstorage_and_exposure_typedefs"></a> 创建存储和公开的 Typedef

定义集合接口后，需要确定如何存储数据，以及如何通过枚举器公开数据。

这些问题的答案可采用许多 typedef 的形式提供，你可以在新创建的类的标头文件的顶部附近添加内容：

[!code-cpp[NVC_ATL_COM#25](../atl/codesnippet/cpp/implementing-an-stl-based-collection_2.h)]

在这种情况下，你将数据存储为 std： **： string** s 的 **std：： vector** 。 **std：： vector** 是一个 c + + 标准库容器类，它的行为类似于托管数组。 **std：： string** 是 c + + 标准库的字符串类。 使用这些类可以轻松地处理字符串的集合。

由于 Visual Basic 支持对此接口的成功至关重要，因此属性返回的枚举器 `_NewEnum` 必须支持 `IEnumVARIANT` 接口。 这是 Visual Basic 理解的唯一枚举器接口。

## <a name="creating-typedefs-for-copy-policy-classes"></a><a name="vcconcopy_classes"></a> 为复制策略类创建 Typedef

到目前为止，您已创建的 typedef 提供为要由枚举器和集合使用的 copy 类创建进一步的 typedef 所需的所有信息：

[!code-cpp[NVC_ATL_COM#26](../atl/codesnippet/cpp/implementing-an-stl-based-collection_3.h)]

在此示例中，可以使用 `GenericCopy` [ATLCollections](../overview/visual-cpp-samples.md) 示例中的 VCUE_Copy 和 VCUE_CopyString 中定义的自定义类。 您可以在其他代码中使用此类，但您可能需要定义进一步的专用化， `GenericCopy` 以支持您自己的集合中使用的数据类型。 有关详细信息，请参阅 [ATL 复制策略类](../atl/atl-copy-policy-classes.md)。

## <a name="creating-typedefs-for-enumeration-and-collection"></a><a name="vcconenumeration_and_collection"></a> 为枚举和集合创建 Typedef

现在，使用 typedef 的形式提供了专用 `CComEnumOnSTL` 化 `ICollectionOnSTLImpl` 此情况下的和类所需的所有模板参数。 若要简化专用化的使用，请创建另外两个 typedef，如下所示：

[!code-cpp[NVC_ATL_COM#27](../atl/codesnippet/cpp/implementing-an-stl-based-collection_4.h)]

现在 `CollectionType` 是的专用化同义词，用于 `ICollectionOnSTLImpl` 实现 `IWords` 前面定义的接口，并提供支持的枚举器 `IEnumVARIANT` 。

## <a name="editing-the-wizard-generated-code"></a><a name="vcconedit_the_generated_code"></a> 编辑 Wizard-Generated 代码

现在，你必须 `CWords` 从由 `CollectionType` typedef （而非）表示的接口实现派生 `IWords` ，如下所示：

[!code-cpp[NVC_ATL_COM#28](../atl/codesnippet/cpp/implementing-an-stl-based-collection_5.h)]

## <a name="adding-code-to-populate-the-collection"></a><a name="vcconpopulate_the_collection"></a> 添加代码以填充集合

唯一要做的事情就是用数据填充矢量。 在这个简单的示例中，可以在类的构造函数中向集合添加几个单词：

[!code-cpp[NVC_ATL_COM#29](../atl/codesnippet/cpp/implementing-an-stl-based-collection_6.h)]

现在，你可以通过所选的客户端来测试代码。

## <a name="see-also"></a>请参阅

[集合和枚举数](../atl/atl-collections-and-enumerators.md)<br/>
[ATLCollections 示例](../overview/visual-cpp-samples.md)<br/>
[ATL 复制策略类](../atl/atl-copy-policy-classes.md)
