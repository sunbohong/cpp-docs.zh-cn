---
description: '了解有关以下内容的详细信息： #import 特性 (c + +) '
title: '#import 特性 (C++)'
ms.date: 08/29/2019
helpviewer_keywords:
- '#import directive, attributes'
ms.assetid: 2a5085e3-82ee-4f83-892b-0aa6cc13863b
ms.openlocfilehash: 87719ba549efab4e0acf13d7e957c6841900d5fc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97300444"
---
# <a name="import-attributes-c"></a>c + + (#import 特性) 

提供与指令一起使用的特性的链接 `#import` 。

**Microsoft 专用**

以下属性可用于 `#import` 指令。

|特性|描述|
|---------------|-----------------|
|[auto_rename](../preprocessor/auto-rename.md)|通过将两个下划线 (__) 追加到变量名称来重命名 C++ 保留字，从而解决可能的名称冲突。|
|[auto_search](../preprocessor/auto-search.md)|指定当使用 #import 引用了类型库，并且它本身引用了另一个类型库时，编译器可以为其他类型库执行隐式 #import。|
|[embedded_idl](../preprocessor/embedded-idl.md)|指定将类型库写入保留了特性生成的代码的 .tlh 文件。|
|[延伸](../preprocessor/exclude-hash-import.md)|从要生成的类型库标头文件中排除项。|
|[high_method_prefix](../preprocessor/high-method-prefix.md)|指定用于命名高级属性和方法的前缀。|
|[high_property_prefixes](../preprocessor/high-property-prefixes.md)|指定用于三个属性方法的备用前缀。|
|[implementation_only](../preprocessor/implementation-only.md)|取消生成 .tlh 头文件（主要头文件）。|
|[包括 ( # B1 ](../preprocessor/include-parens.md)|禁用自动排除。|
|[inject_statement](../preprocessor/inject-statement.md)|将其自变量作为源文本插入类型库标头。|
|[named_guids](../preprocessor/named-guids.md)|通知编译器以旧样式定义和初始化 GUID 变量，格式为 `LIBID_MyLib` 、、 `CLSID_MyCoClass` `IID_MyInterface` 和 `DIID_MyDispInterface` 。|
|[no_auto_exclude](../preprocessor/no-auto-exclude.md)|禁用自动排除。|
|[no_dual_interfaces](../preprocessor/no-dual-interfaces.md)|更改编译器为双重接口方法生成包装器函数的方式。|
|[no_implementation](../preprocessor/no-implementation.md)|取消生成 .tli 标头，它包含包装器成员函数的实现。|
|[no_namespace](../preprocessor/no-namespace.md)|指定命名空间的名称不由编译器生成。|
|[no_registry](../preprocessor/no-registry.md)|告知编译器不在注册表中搜索类型库。|
|[no_search_namespace](../preprocessor/no-search-namespace.md)|具有与 [no_namespace](../preprocessor/no-namespace.md) 特性相同的功能，但用于类型库，该类型库将 #import 指令与 [auto_search](../preprocessor/auto-search.md) 特性结合使用。|
|[no_smart_pointers](../preprocessor/no-smart-pointers.md)|取消对类型库中所有接口的智能指针的创建。|
|[raw_dispinterfaces](../preprocessor/raw-dispinterfaces.md)|通知编译器为调度接口方法和属性生成低级别包装函数，这些方法和属性调用 `IDispatch::Invoke` 并返回 HRESULT 错误代码。|
|[raw_interfaces_only](../preprocessor/raw-interfaces-only.md)|禁止生成使用这些包装函数的错误处理包装函数和 [属性](../cpp/property-cpp.md) 声明。|
|[raw_method_prefix](../preprocessor/raw-method-prefix.md)|指定不同的前缀以避免名称冲突。|
|[raw_native_types](../preprocessor/raw-native-types.md)|禁止在高级包装器函数中使用 COM 支持类，并强制改用低级数据类型。    |
|[raw_property_prefixes](../preprocessor/raw-property-prefixes.md)|指定用于三个属性方法的备用前缀。|
|[rename](../preprocessor/rename-hash-import.md)|解决名称冲突问题。|
|[rename_namespace](../preprocessor/rename-namespace.md)|重命名包含类型库内容的命名空间。|
|[rename_search_namespace](../preprocessor/rename-search-namespace.md)|具有与 [rename_namespace](../preprocessor/rename-namespace.md) 特性相同的功能，但用于类型库，该类型库将 #import 指令与 [auto_search](../preprocessor/auto-search.md) 特性结合使用。|
|[tlbid](../preprocessor/tlbid.md)|允许加载主类型库之外的库。|

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[#import 指令](../preprocessor/hash-import-directive-cpp.md)
