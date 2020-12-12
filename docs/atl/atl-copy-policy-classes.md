---
description: 了解详细信息： ATL 复制策略类
title: ATL 复制策略类
ms.date: 11/04/2016
helpviewer_keywords:
- data [C++], ATL
- classes [C++], copy policy
- copy policy classes [C++]
- _Copy class
- _CopyInterface class
ms.assetid: 06704b68-d318-4c5d-a65b-71457fe9d00d
ms.openlocfilehash: 502befadbd9317602c49d9a5815dee6ebc239d78
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97165753"
---
# <a name="atl-copy-policy-classes"></a>ATL 复制策略类

复制策略类是用于初始化、复制和删除数据的 [实用工具类](../atl/utility-classes.md) 。 复制策略类允许您为任何类型的数据定义复制语义，并定义不同数据类型之间的转换。

ATL 在其以下模板的实现中使用复制策略类：

- [CComEnumImpl](../atl/reference/ccomenumimpl-class.md)

- [IEnumOnSTLImpl](../atl/reference/ienumonstlimpl-class.md)

- [ICollectionOnSTLImpl](../atl/reference/icollectiononstlimpl-class.md)

通过在可作为模板参数传递的复制策略类中封装复制或转换数据所需的信息，ATL 开发人员提供了这些类的极大可重用性。 例如，如果需要使用任意数据类型来实现集合，只需提供相应的复制策略即可;您不必接触实现集合的代码。

## <a name="definition"></a>定义

按照定义，提供以下静态函数的类是复制策略类：

`static void init(` `DestinationType` `* p);`

`static HRESULT copy(` `DestinationType` `* pTo, const`  `SourceType` `* pFrom);`

`static void destroy(` `DestinationType` `* p);`

可以将类型 `DestinationType` 和 *SourceType* 替换为每个复制策略的任意数据类型。

> [!NOTE]
> 尽管可以为任意数据类型定义复制策略类，但在 ATL 代码中使用类应限制有意义的类型。 例如，将复制策略类与 ATL 的集合或枚举器实现一起使用时， `DestinationType` 必须是可用作 COM 接口方法中的参数的类型。

使用 **init** 初始化数据、 **复制** 数据并将其 **销毁** ，以释放数据。 "初始化"、"复制" 和 "析构" 的精确含义是复制策略类的域，将因所涉及的数据类型而异。

复制策略类的使用和实现有两个要求：

- 要 **复制** 的第一个参数必须仅接收指向以前使用 **init** 初始化的数据的指针。

- **销毁** 只需收到指向以前使用 **init** 初始化或通过 **复制** 复制的数据的指针。

## <a name="standard-implementations"></a>标准实现

ATL 以 `_Copy` 和模板类的形式提供两个复制策略类 `_CopyInterface` ：

- `_Copy`类只允许同类复制 () 数据类型之间的转换，因为它仅提供一个模板参数来指定 `DestinationType` 和 *SourceType*。 此模板的泛型实现不包含初始化或析构代码，并使用 `memcpy` 来复制数据。 ATL 还提供了 `_Copy` LPOLESTR、OLEVERB 和 CONNECTDATA 数据类型的专用化。

- `_CopyInterface`类提供了一个实现，用于在标准 COM 规则后复制接口指针。 同样，此类仅允许同类复制，因此它使用简单赋值和对的调用 `AddRef` 来执行复制。

## <a name="custom-implementations"></a>自定义实现

通常，你需要为异类复制定义你自己的复制策略类， (也就是说，) 之间的数据类型之间的转换。 有关自定义复制策略类的一些示例，请查看 [ATLCollections](../overview/visual-cpp-samples.md) 示例中的文件 VCUE_Copy .h 和 VCUE_CopyString。 这些文件包含两个模板复制策略类， `GenericCopy` 以及 `MapCopy` `GenericCopy` 不同数据类型的多个专用化。

### <a name="genericcopy"></a>GenericCopy

`GenericCopy` 允许您指定 *SourceType* 和 `DestinationType` as 模板参数。 下面是来自 VCUE_Copy 的最常见的 `GenericCopy` 类形式：

[!code-cpp[NVC_ATL_COM#30](../atl/codesnippet/cpp/atl-copy-policy-classes_1.h)]

VCUE_Copy 也包含此类的以下专用化： `GenericCopy<BSTR>` 、 `GenericCopy<VARIANT, BSTR>` 、 `GenericCopy<BSTR, VARIANT>` 。 VCUE_CopyString 包含用于从 **std：： string** s： `GenericCopy<std::string>` 、和进行复制的专用化。 `GenericCopy<VARIANT, std::string>` `GenericCopy<BSTR, std::string>` 可以 `GenericCopy` 通过提供自己的专用化来增强。

### <a name="mapcopy"></a>MapCopy

`MapCopy` 假设要复制的数据存储在 c + + 标准库样式的映射中，因此可以使用它来指定存储数据的映射类型和目标类型。 类的实现只使用由 *MapType* 类提供的 typedef 来确定源数据的类型，并调用适当的 `GenericCopy` 类。 不需要此类的专用化。

[!code-cpp[NVC_ATL_COM#31](../atl/codesnippet/cpp/atl-copy-policy-classes_2.h)]

## <a name="see-also"></a>请参阅

[实现 c + + 标准 Library-Based 集合](../atl/implementing-an-stl-based-collection.md)<br/>
[ATLCollections 示例](../overview/visual-cpp-samples.md)
