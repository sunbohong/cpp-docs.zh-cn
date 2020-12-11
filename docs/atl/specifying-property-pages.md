---
description: 了解详细信息：指定属性页
title: " (ATL) 指定属性页"
ms.date: 11/04/2016
helpviewer_keywords:
- ISpecifyPropertyPages method
- property pages, specifying
ms.assetid: ee8678cf-c708-49ab-b0ad-fc2db31f1ac3
ms.openlocfilehash: 171440dde11178c85d1f636874b0b161691cb9cc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97157420"
---
# <a name="specifying-property-pages"></a>指定属性页

创建 ActiveX 控件时，通常需要将其与可用于设置控件的属性的属性页相关联。 控件容器使用 `ISpecifyPropertyPages` 接口来确定哪些属性页可用于设置控件的属性。 你将需要在控件上实现此接口。

若要 `ISpecifyPropertyPages` 使用 ATL 实现，请执行以下步骤：

1. 从 [ISpecifyPropertyPagesImpl](../atl/reference/ispecifypropertypagesimpl-class.md)派生类。

1. 向 `ISpecifyPropertyPages` 类的 COM 映射添加一个项。

1. 将 [PROP_PAGE](reference/property-map-macros.md#prop_page) 条目添加到与控件相关联的每个页面的属性映射。

> [!NOTE]
> 使用 [ATL 控件向导](../atl/reference/atl-control-wizard.md)生成标准控件时，只需将 PROP_PAGE 项添加到属性映射。 向导将生成其他步骤所需的代码。

正常情况容器会按照属性映射中 PROP_PAGE 条目的顺序来显示指定的属性页。 通常情况下，应在属性映射中的自定义页面的条目后面放置标准属性页条目，以便用户可以首先查看特定于控件的页面。

## <a name="example"></a>示例

日历控件的以下类使用 `ISpecifyPropertyPages` 接口来告知容器使用自定义日期页和 "常用颜色" 页可以设置其属性。

[!code-cpp[NVC_ATL_Windowing#72](../atl/codesnippet/cpp/specifying-property-pages_1.h)]

## <a name="see-also"></a>请参阅

[属性页](../atl/atl-com-property-pages.md)<br/>
[ATLPages 示例](../overview/visual-cpp-samples.md)
