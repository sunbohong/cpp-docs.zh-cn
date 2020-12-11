---
description: 了解详细信息：了解窗口特性
title: ATL 窗口特性
ms.date: 11/04/2016
helpviewer_keywords:
- window traits
ms.assetid: c90cf850-9e91-49da-9cf3-ad4efb30347d
ms.openlocfilehash: a42ef66afe09e0e528f05419799dce48c43b1bbf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97157290"
---
# <a name="understanding-window-traits"></a>了解窗口特性

窗口特征类提供了一种简单的方法，用于标准化用于创建 ATL 窗口对象的样式。 作为模板参数， [CWindowImpl](../atl/reference/cwindowimpl-class.md) 和其他 ATL 窗口类接受窗口特征作为在类级提供默认窗口样式的方式。

如果窗口实例的创建者未在 [创建](../atl/reference/cwindowimpl-class.md#create)的调用中显式提供样式，则可以使用特征类确保仍使用正确的样式创建窗口。 您甚至可以确保为该窗口类的所有实例设置某些样式，同时允许对每个实例设置其他样式。

## <a name="atl-window-traits-templates"></a>ATL 窗口特征模板

ATL 提供两个窗口特性模板，使您可以在编译时使用其模板参数设置默认样式。

|类|描述|
|-----------|-----------------|
|[CWinTraits](../atl/reference/cwintraits-class.md)|如果希望提供默认窗口样式，而该样式仅在对的调用中未指定其他样式时使用，则使用此模板 `Create` 。 运行时提供的样式优先于编译时设置的样式。|
|[CWinTraitsOR](../atl/reference/cwintraitsor-class.md)|如果要指定必须始终为窗口类设置的样式，请使用此类。 在运行时提供的样式与使用按位 OR 运算符编译时设置的样式组合在一起。|

除了这些模板以外，ATL 还为 `CWinTraits` 常用的窗口样式组合提供了大量预定义的模板专用化。 有关完整详细信息，请参阅 [CWinTraits](../atl/reference/cwintraits-class.md) 参考文档。

## <a name="custom-window-traits"></a>自定义窗口特性

在专门提供 ATL 提供的模板中的一种不太可能的情况下，你需要创建自己的特征类，你只需创建一个实现两个静态函数的类： `GetWndStyle` 和 `GetWndStyleEx` ：

[!code-cpp[NVC_ATL_Windowing#68](../atl/codesnippet/cpp/understanding-window-traits_1.h)]

其中的每个函数都将在运行时传递到可用于生成新样式值的样式值。 如果您的窗口特征类用作 ATL 窗口类的模板参数，则传递给这些静态函数的样式值将是作为要 [创建](../atl/reference/cwindowimpl-class.md#create)的样式参数传递的任何内容。

## <a name="see-also"></a>请参阅

[窗口类](../atl/atl-window-classes.md)
