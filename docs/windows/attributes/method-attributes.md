---
description: 了解有关以下方面的详细信息：方法特性
title: C + + COM)  (方法特性
ms.date: 10/02/2018
helpviewer_keywords:
- method attributes
- attributes [C++/CLI], reference topics
ms.assetid: b2313352-480d-488b-8c35-6242ffd3a549
ms.openlocfilehash: 29acb1f92b01e85960bc727c9b3e91f9a52732d5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97327493"
---
# <a name="method-attributes"></a>方法特性

以下属性适用于类、组件类或接口中的方法。

|特性|描述|
|---------------|-----------------|
|[bindable](bindable.md)|指示该属性支持数据绑定。|
|[call_as](call-as.md)|使不可远程处理函数能够映射到远程函数。|
|[客户](custom-cpp.md)|允许您定义自己的属性。|
|[db_column](db-column.md)|将指定列绑定到行集。|
|[db_command](db-command.md)|创建 OLE DB 命令。|
|[db_param](db-param.md)|将指定的成员变量与输入或输出参数关联，并将变量分隔。|
|[db_source](db-source.md)|创建与数据源的连接。|
|[db_table](db-table.md)|打开 OLE DB 表。|
|[defaultbind](defaultbind.md)|指示最能表示对象的单个可绑定属性。|
|[defaultcollelem](defaultcollelem.md)|用于 Visual Basic 代码优化。|
|[displaybind](displaybind.md)|指示应作为可绑定属性显示给用户的属性。|
|[helpcontext](helpcontext.md)|指定一个上下文 ID，该 ID 允许用户在 **帮助** 文件中查看有关此元素的信息。|
|[helpfile](helpfile.md)|设置类型库的 **帮助** 文件的名称。|
|[helpstring](helpstring.md)|指定一个字符串，用于描述应用该字符串的元素。|
|[helpstringcontext](helpstringcontext.md)|指定 .hlp 或 .chm 文件中帮助主题的 ID。|
|[helpstringdll](helpstringdll.md)|指定要用于执行文档字符串查找 (本地化) 的 DLL 的名称。|
|[消隐](hidden.md)|指示该项存在，但不应在面向用户的浏览器中显示。|
|[id](id.md)|为接口或调度接口) 中的属性或方法 (的成员函数指定 DISPID。|
|[immediatebind](immediatebind.md)|指示将立即通知数据库对数据绑定对象的属性所做的所有更改。|
|[in](in-cpp.md)|指示参数将从调用过程传递给被调用过程。|
|[地方](local-cpp.md)|允许在接口标头中使用 MIDL 编译器时将其用作标头生成器。 在单独的函数中使用时，指定不会为其生成存根的本地过程。|
|[nonbrowsable](nonbrowsable.md)|指示不应在属性浏览器中显示接口成员。|
|[propget](propget.md)|指定属性访问器函数。|
|[propput](propput.md)|指定属性设置函数。|
|[propputref](propputref.md)|指定使用引用而不是值的属性设置函数。|
|[ptr](ptr.md)|将指针指定为完全指针。|
|[range](range-cpp.md)|为其值在运行时设置的参数或字段指定一系列允许的值。|
|[requestedit](requestedit.md)|指示该属性支持 `OnRequestEdit` 通知。|
|[限制](restricted.md)|指定不能任意调用模块、接口或调度接口的成员。|
|[satype](satype.md)|指定结构的数据类型 `SAFEARRAY` 。|
|[source](source-cpp.md)|指定类上的连接点的控件源接口。 在属性或方法上， `source` 特性指示成员返回作为事件源的对象或变体。|
|[同步](synchronize.md)|同步对目标方法的访问。|
|[vararg](vararg.md)|指定该函数采用可变数量的参数。|

## <a name="see-also"></a>请参阅

[按使用情况的属性](attributes-by-usage.md)
