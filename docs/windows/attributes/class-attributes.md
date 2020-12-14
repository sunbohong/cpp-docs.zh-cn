---
description: 了解详细信息：类特性
title: C + + COM)  (类特性
ms.date: 10/02/2018
helpviewer_keywords:
- attributes [C++/CLI], class attributes
ms.assetid: fad04ea1-d8ff-46d4-bb42-2b4500a6ab60
ms.openlocfilehash: ea929ed7f5fac949393e6d3cf2b24195babfeea7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97247379"
---
# <a name="class-attributes"></a>类特性

以下属性适用于 [类](../../cpp/class-cpp.md) c + + 关键字。

|特性|描述|
|---------------|-----------------|
|[aggregatable](aggregatable.md)|指示类支持聚合。|
|[集中](aggregates.md)|指示控件聚合目标类。|
|[appobject](appobject.md)|将 coclass 标识为与完整 .exe 应用程序关联的应用程序对象，并指示 coclass 的函数和属性在此类型库中全局可用。|
|[case](case-cpp.md)|与联合中的 [switch_type](switch-type.md) 特性一起使用。|
|[coclass](coclass.md)|创建 ActiveX 控件。|
|[com_interface_entry](com-interface-entry-cpp.md)|向 COM 映射添加接口条目。|
|[control](control.md)|指定用户定义类型为控件。|
|[客户](custom-cpp.md)|允许您定义自己的属性。|
|[db_command](db-command.md)|创建 OLE DB 命令。|
|[db_param](db-param.md)|将指定的成员变量与输入或输出参数关联，并将变量分隔。|
|[db_source](db-source.md)|创建与数据源的连接。|
|[db_table](db-table.md)|打开 OLE DB 表。|
|[default](default-cpp.md)|指示组件类中定义的自定义接口或调度接口表示默认的可编程性接口。|
|[defaultvtable](defaultvtable.md)|将接口定义为控件的默认 vtable 接口。|
|[event_receiver](event-receiver.md)|创建事件接收器。|
|[event_source](event-source.md)|创建事件源。|
|[helpcontext](helpcontext.md)|指定一个上下文 ID，该 ID 允许用户在 **帮助** 文件中查看有关此元素的信息。|
|[helpfile](helpfile.md)|设置类型库的帮助文件的名称。|
|[helpstringcontext](helpstringcontext.md)|指定 .hlp 或 .chm 文件中帮助主题的 ID。|
|[helpstring](helpstring.md)|指定一个字符串，用于描述应用该字符串的元素。|
|[消隐](hidden.md)|指示该项存在，但不应在面向用户的浏览器中显示。|
|[实现](implements-cpp.md)|指定强制成为 IDL 组件类成员的调度接口。|
|[implements_category](implements-category.md)|指定类实现的组件类别。|
|[模块](module-cpp.md)|定义.Idl 文件中的库块。|
|[noncreatable](noncreatable.md)|定义一个对象，该对象不能单独实例化。|
|[progid](progid.md)|定义控件的 ProgID。|
|[registration_script](registration-script.md)|执行指定的注册脚本。|
|[requestedit](requestedit.md)|指示该属性支持 `OnRequestEdit` 通知。|
|[source](source-cpp.md)|指定类上的连接点的控件源接口。 在属性或方法上， `source` 特性指示成员返回对象或作为 `VARIANT` 事件的源。|
|[support_error_info](support-error-info.md)|支持对目标对象进行错误报告。|
|[线程](threading-cpp.md)|指定控件的线程模型。|
|[uuid](uuid-cpp-attributes.md)|指定类或接口的唯一 ID。|
|[version](version-cpp.md)|标识类的多个版本中的特定版本。|
|[vi_progid](vi-progid.md)|指定 ProgID 的与版本无关的形式。|

## <a name="see-also"></a>请参阅

[按使用情况的属性](attributes-by-usage.md)
