---
description: 了解更多相关信息： ATL 集合和枚举器
title: ATL 集合和枚举数
ms.date: 11/04/2016
helpviewer_keywords:
- enumerator interfaces
- collections, ATL classes
- enumerators, ATL classes
- collection interfaces
ms.assetid: b2d37119-3ab2-4e0a-b65b-f377f07e4098
ms.openlocfilehash: 92e9ab3df52219812d72ae5cb811f57a3ecf4fad
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97166000"
---
# <a name="atl-collections-and-enumerators"></a>ATL 集合和枚举数

`collection`是一个 COM 对象，它提供了一个接口，该接口允许)  (原始数据或其他对象访问一组数据项。 遵循提供对一组对象的访问的标准的接口称为 *集合接口*。

集合接口至少必须提供一个 `Count` 属性，该属性可返回集合中的项数、一个 `Item` 属性，该属性根据索引从集合中返回一个项，并返回一个属性，该属性返回 `_NewEnum` 集合的枚举数。 （可选）集合接口可以提供 `Add` 和 `Remove` 方法，以允许在集合中插入或删除项，使用方法可以 `Clear` 移除所有项。

`enumerator`是一个 COM 对象，它提供用于循环访问集合中的项的接口。 枚举器接口通过四个所需的方法，提供对集合的元素的串行访问： `Next` 、 `Skip` 、 `Reset` 和 `Clone` 。

可以通过读取引用内容（如 [IEnumString](/windows/win32/api/objidl/nn-objidl-ienumstring) 接口）来了解有关枚举器接口的详细信息。

## <a name="in-this-section"></a>本节内容

[ATL 集合和枚举器类](../atl/atl-collection-and-enumerator-classes.md)<br/>
简要描述并提供指向 ATL 类的链接，它们可帮助您实现集合和枚举器。

[集合和枚举器接口的设计原则](../atl/design-principles-for-collection-and-enumerator-interfaces.md)<br/>
讨论每种接口的各种设计原则。

[实现 c + + 标准 Library-Based 集合](../atl/implementing-an-stl-based-collection.md)<br/>
一个扩展示例，指导您实现基于 c + + 标准库的集合。

## <a name="related-sections"></a>相关章节

[ATL](../atl/active-template-library-atl-concepts.md)<br/>
提供了关于如何使用 Active Template Library 进行编程的概念性主题的链接。

[ATLCollections 示例](../overview/visual-cpp-samples.md)<br/>
演示如何使用和的示例 `ICollectionOnSTLImpl` `CComEnumOnSTL` ，以及如何实现自定义复制策略类。

## <a name="see-also"></a>请参阅

[概念](../atl/active-template-library-atl-concepts.md)
