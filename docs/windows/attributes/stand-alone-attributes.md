---
description: 了解详细信息： Stand-Alone 属性
title: 'C + + COM (Stand-Alone 特性) '
ms.date: 10/02/2018
helpviewer_keywords:
- standalone attributes
- attributes [C++/CLI], standalone
ms.assetid: 0d72e84e-236c-43b3-ac9a-d9b91fcd6794
ms.openlocfilehash: 39b7356243f9b6ba7c42e907ca0733f59b85961e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97329591"
---
# <a name="stand-alone-attributes"></a>独立特性

独立属性对 c + + 关键字不起作用，但更类似于代码行。 独立的 attribute 语句需要在行的末尾使用分号。

## <a name="stand-alone-attribute-list"></a>独立属性列表

|特性|描述|
|---------------|-----------------|
|[cpp_quote](cpp-quote.md)|向生成的标头文件发出指定的字符串（不含引号字符）。|
|[客户](custom-cpp.md)|允许您定义自己的属性。|
|[db_command](db-command.md)|创建 OLE DB 命令。|
|[emitidl](emitidl.md)|确定是否将处理所有后续 IDL 特性并将其放置在生成的 .idl 文件中。|
|[idl_module](idl-module.md)|指定 DLL 中的入口点。|
|[idl_quote](idl-quote.md)|允许你使用 Visual C++ 的当前版本中不支持的 IDL 构造，并将其传递到生成的 .idl 文件。|
|[import](import.md)|指定另一个 .idl、odl 或 .h 文件，其中包含要从您的主 .idl 文件引用的定义。|
|[importidl](importidl.md)|将指定的 .idl 文件插入生成的 .idl 文件|
|[importlib](importlib.md)|使已编译到另一个类型库中的类型可供所创建的类型库使用。|
|[包括](include-cpp.md)|指定要包含在生成的 .idl 文件中的一个或多个标头文件。|
|[includelib](includelib-cpp.md)|导致在生成的 .idl 文件中包含 .idl 或 .h 文件。|
|[library_block](library-block.md)|将构造置于 .idl 文件的库块内。|
|[模块](module-cpp.md)|定义.Idl 文件中的库块。|
|[no_injected_text](no-injected-text.md)|阻止编译器将代码注入到属性使用的结果中。|
|[杂](pragma.md)|向生成的 .idl 文件发出指定的字符串（不含引号字符）。|

## <a name="see-also"></a>请参阅

[按使用情况的属性](attributes-by-usage.md)
