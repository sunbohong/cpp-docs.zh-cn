---
description: 了解详细信息： COM 特性
title: COM 特性
ms.date: 10/03/2018
helpviewer_keywords:
- attributes [C++/CLI], reference topics
- attributes [COM]
- COM, attributes
ms.assetid: 52a5dd70-e8be-4bba-afd6-daf90fe689a0
ms.openlocfilehash: d1377bdcb449190d01f529b2a4c713f138cbef5f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97269167"
---
# <a name="com-attributes"></a>COM 特性

COM 属性注入代码以支持许多 COM 开发区域和 .NET Framework 公共语言运行时开发。 这些区域包括自定义接口实现，并支持现有接口以支持常用属性、方法和事件。 此外，还可以找到支持组合和 ActiveX 控件。

|特性|描述|
|---------------|-----------------|
|[aggregatable](aggregatable.md)|指示控件可由另一个控件聚合。|
|[集中](aggregates.md)|指示控件聚合目标类。|
|[coclass](coclass.md)|创建可实现 COM 接口的 COM 对象。|
|[com_interface_entry](com-interface-entry-cpp.md)|向 COM 映射添加接口条目。|
|[implements_category](implements-category.md)|指定类实现的组件类别。|
|[progid](progid.md)|定义控件的 ProgID。|
|[rdx](rdx.md)|创建或修改注册表项。|
|[registration_script](registration-script.md)|执行指定的注册脚本。|
|[requires_category](requires-category.md)|指定类所需的组件类别。|
|[support_error_info](support-error-info.md)|支持对目标对象进行错误报告。|
|[同步](synchronize.md)|同步对方法的访问。|
|[线程](threading-cpp.md)|指定 COM 对象的线程模型。|
|[vi_progid](vi-progid.md)|为控件定义独立于版本的 ProgID。|

## <a name="see-also"></a>请参阅

[按组的属性](attributes-by-group.md)
