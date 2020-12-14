---
description: 了解有关以下内容的详细信息：编译器错误 C3300 到 C3399
title: 编译器错误 C3300 - C3399
ms.date: 04/21/2019
f1_keywords:
- C3300
- C3301
- C3302
- C3304
- C3305
- C3306
- C3307
- C3308
- C3310
- C3311
- C3312
- C3313
- C3314
- C3315
- C3316
- C3317
- C3318
- C3319
- C3321
- C3323
- C3324
- C3325
- C3326
- C3327
- C3328
- C3329
- C3330
- C3331
- C3332
- C3335
- C3336
- C3337
- C3338
- C3339
- C3341
- C3343
- C3344
- C3346
- C3348
- C3349
- C3355
- C3357
- C3359
- C3361
- C3362
- C3376
- C3377
- C3378
helpviewer_keywords:
- C3300
- C3301
- C3302
- C3304
- C3305
- C3306
- C3307
- C3308
- C3310
- C3311
- C3312
- C3313
- C3314
- C3315
- C3316
- C3317
- C3318
- C3319
- C3321
- C3323
- C3324
- C3325
- C3326
- C3327
- C3328
- C3329
- C3330
- C3331
- C3332
- C3335
- C3336
- C3337
- C3338
- C3339
- C3341
- C3343
- C3344
- C3346
- C3348
- C3349
- C3355
- C3357
- C3359
- C3361
- C3362
- C3376
- C3377
- C3378
ms.assetid: 190b7d29-ffe6-4261-921d-140da1935d00
ms.openlocfilehash: 7c3a2f00edd5bee55ba623125c65590584751c39
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97238643"
---
# <a name="compiler-errors-c3300-through-c3399"></a>编译器错误 C3300 - C3399

文档的本节中的文章介绍了编译器生成的错误消息的子集。

[!INCLUDE[error-boilerplate](../../error-messages/includes/error-boilerplate.md)]

## <a name="error-messages"></a>错误消息

|错误|消息|
|-----------|-------------|
|编译器错误 C3300|"*symbol*"： IDL "*value*" 的格式不正确|
|编译器错误 C3301|"*coclass*"：组件类不能是 "*symbol*" 接口|
|编译器错误 C3302|"*identifier*"：标识符 *包含多个字符*|
|[编译器错误 C3303](compiler-error-c3303.md)|"*attribute*"：特性只能在 "*type*" 上使用|
|编译器错误 C3304|已过时。|
|编译器错误 C3305|已过时。|
|编译器错误 C3306|"*template*"：不允许未命名的类模板/泛型|
|编译器错误 C3307|"*module*"：无法创建 IDL 模块|
|编译器错误 C3308|" *function*"：不支持通过导入类进行直接调用|
|[编译器错误 C3309](compiler-error-c3309.md)|"*macro* / *关键字*"：模块名称不能是宏或关键字|
|编译器错误 C3310|"*identifier*"：模块名称冲突|
|编译器错误 C3311|模块特性必须在全局范围内定义|
|编译器错误 C3312|找不到类型 "*type*" 的可调用 "*identifier*" 函数|
|编译器错误 C3313|"*identifier*"：变量不能具有类型 "*type*"|
|编译器错误 C3314|"*symbol*"：不是支持的 IDL 模块类型|
|编译器错误 C3315|" *function*"：必须是成员函数|
|编译器错误 C3316|"*type*"：未知大小的数组不能在基于范围的 for 语句中使用|
|编译器错误 C3317|"*identifier*"：重载函数不能在基于范围的 for 语句中用作表达式|
|编译器错误 C3318|"*type*"：数组不能具有包含 "auto" 的元素类型|
|编译器错误 C3319|已过时。|
|[编译器错误 C3320](compiler-error-c3320.md)|"*type*"：类型不能与模块的 "name" 属性同名|
|编译器错误 C3321|此上下文中存在意外的初始值设定项列表|
|[编译器错误 C3322](compiler-error-c3322.md)|"*property*"：不是特性 "*attribute*" 的有效属性|
|编译器错误 C3323|函数声明上不允许使用 "alignas" 和 "__declspec (align) "|
|编译器错误 C3324|"*property*"：属性在特性 "*attribute*" 中出现多次|
|编译器错误 C3325|"*attribute*"：特性的参数太多|
|编译器错误 C3326|"*value*"：不是特性 "*attribute*" 的属性 "*property*" 的有效值|
|编译器错误 C3327|"*property*"：必须指定特性 "*attribute*" 的属性的值|
|编译器错误 C3328|"*attribute*"：特性没有足够的参数|
|编译器错误 C3329|语法错误：应为 "*token1*" 而不是 "*token2*"|
|编译器错误 C3330|" *function*"：函数不能返回数组 "*type*"|
|编译器错误 C3331|"*identifier*"：仅对 COM 接口和组件类允许使用参数的特性|
|编译器错误 C3332|"*property*"：语法不一致，属性 "*property*" 既是必需的，又具有默认值|
|[编译器错误 C3333](compiler-error-c3333.md)|"*library*"：不 #import 损坏的类型库|
|[编译器错误 C3334](compiler-error-c3334.md)|无法 #import 损坏的类型库|
|编译器错误 C3335|"*identifier*"：组件类 "*class*" 最多可以有一个默认接口|
|编译器错误 C3336|此操作必须在类范围内执行|
|编译器错误 C3337|"*identifier*"： defaultvtable 必须是组件类 "*class*" 的事件源|
|编译器错误 C3338|"*identifier*"：最多可以有一个默认接口，它也是组件类 "*class*" 的事件源|
|编译器错误 C3339|模板模板参数需要参数列表后的 "class" 或 "typename"|
|[编译器错误 C3340](compiler-error-c3340.md)|"*identifier*"：组件类 "*class*" 中的接口不能同时为 "受限" 和 "default"|
|编译器错误 C3341|"*interface*"： defaultvtable 接口必须是 "双重" 或 "custom"|
|[编译器错误 C3342](compiler-error-c3342.md)|"*identifier*"：不明确的特性|
|编译器错误 C3343|"*class*：：*name*"：特性标识符的字符太多|
|编译器错误 C3344|不能定义显式专用化或 "*symbol*" 的部分专用化|
|[编译器错误 C3345](compiler-error-c3345.md)|"*name*"：模块名称的标识符无效|
|编译器错误 C3346|在非命名空间范围导出的声明|
|[编译器错误 C3347](compiler-error-c3347.md)|"*argument*"： attribute *asttribute* 中未指定必需的参数|
|编译器错误 C3348|导出的模板不是当前 c + + 标准的一部分|
|编译器错误 C3349|"*class*：：*member*"：多路广播特性已由提供 *程序提供程序* 实现|
|[编译器错误 C3350](compiler-error-c3350.md)|" *function*"：委托构造函数需要 *number* 参数 (s) |
|[编译器错误 C3351](compiler-error-c3351.md)|" *function*"：如果向委托构造函数传递 NULL 对象实例，还必须传递静态成员函数的地址|
|[编译器错误 C3352](compiler-error-c3352.md)|"*function*"：指定的函数与委托类型 "*type*" 不匹配|
|[编译器错误 C3353](compiler-error-c3353.md)|"*identifier*"：委托只能从全局函数或托管/WinRT 类型的成员函数创建|
|[编译器错误 C3354](compiler-error-c3354.md)|"*identifier*"：用于创建委托的函数不能有返回类型 "*type*"|
|编译器错误 C3355|"*class*：：*member*"：多路广播特性侦听提供程序 "*provider1*"，但由提供程序 "*provider2*" 实现|
|[编译器错误 C3356](compiler-error-c3356.md)|"*identifier*"：无法使用完全限定名调用多路广播特性|
|编译器错误 C3357|"*attribute*"：特性不明确，必须使用完全限定名|
|[编译器错误 C3358](compiler-error-c3358.md)|"*symbol*"：未找到符号|
|编译器错误 C3359|"*专用化*"：无法专用化模板|
|[编译器错误 C3360](compiler-error-c3360.md)|"*string*"：无法创建 *名称*|
|编译器错误 C3361|没有要执行 *操作* 的上下文|
|编译器错误 C3362|"*class*：：*member*"：多路广播特性尚未实现|
|[编译器错误 C3363](compiler-error-c3363.md)|"*identifier*"： "typeid" 只能应用于类型|
|[编译器错误 C3364](compiler-error-c3364.md)|" *function*"：委托构造函数的参数无效;委托目标必须是指向成员函数的指针|
|[编译器错误 C3365](compiler-error-c3365.md)|运算符 "*operator*"：区分类型为 "*type*" 和 "*type*" 的操作数|
|[编译器错误 C3366](compiler-error-c3366.md)|"*member*"：托管/WinRT 类型的静态数据成员必须在类定义中定义|
|[编译器错误 C3367](compiler-error-c3367.md)|" *function*"：不能使用静态函数创建未绑定的委托|
|[编译器错误 C3368](compiler-error-c3368.md)|"*声明符*"： IDL 的调用约定无效|
|[编译器错误 C3369](compiler-error-c3369.md)|"*module*"：已定义 idl_module|
|[编译器错误 C3370](compiler-error-c3370.md)|"*module*"：尚未定义 idl_module|
|[编译器错误 C3371](compiler-error-c3371.md)|“idl_module”: 此处只允许“name”属性|
|[编译器错误 C3372](compiler-error-c3372.md)|必须为组件类上的特性 "*attribute*" 至少指定1个接口|
|[编译器错误 C3373](compiler-error-c3373.md)|除了组件类，特性 "*attribute*" 不使用任何参数|
|[编译器错误 C3374](compiler-error-c3374.md)|除非创建委托实例，否则不能使用 " *function*" 的地址|
|[编译器错误 C3375](compiler-error-c3375.md)|"*function*"：不明确的委托函数|
|编译器错误 C3376|"*template*"：只允许使用静态数据成员模板|
|编译器错误 C3377|new 表达式中不允许使用 "decltype (auto) "|
|编译器错误 C3378|只能从模块接口单元中导出声明|
|[编译器错误 C3379](compiler-error-c3379.md)|"*class*"：嵌套类不能将程序集访问说明符作为声明的一部分|
|[编译器错误 C3380](compiler-error-c3380.md)|"*说明符*"：程序集访问说明符无效-只允许 "public" 或 "private"|
|[编译器错误 C3381](compiler-error-c3381.md)|"*说明符*"：程序集访问说明符仅可用于使用/clr 选项编译的代码中|
|[编译器错误 C3382](compiler-error-c3382.md)|不支持将“sizeof”与 /clr:safe 一同使用|
|[编译器错误 C3383](compiler-error-c3383.md)|不支持将“operator new”与 /clr:safe 一起使用|
|[编译器错误 C3384](compiler-error-c3384.md)|"*type*"：值约束与 ref 约束互相排斥|
|[编译器错误 C3385](compiler-error-c3385.md)|" *function*"：具有 DllImport 自定义特性的函数不能返回类的实例|
|[编译器错误 C3386](compiler-error-c3386.md)|"*type*"： __declspec (dllexport) /__declspec (dllimport) 不能应用于托管的/WinRT 类型|
|[编译器错误 C3387](compiler-error-c3387.md)|"*member*"： __declspec (dllexport) /__declspec (dllimport) 不能应用于托管/WinRT 类型的成员|
|[编译器错误 C3388](compiler-error-c3388.md)|"*token*"：不允许作为约束，假定为 "*value*" 以继续进行分析|
|[编译器错误 C3389](compiler-error-c3389.md)|__declspec (*说明符*) 不能与/clr： pure 或/clr： safe 一起使用|
|[编译器错误 C3390](compiler-error-c3390.md)|"*type*"：泛型 "*generic_type*" 的泛型参数 "*parameter*" 的类型参数无效，它必须是引用类型|
|[编译器错误 C3391](compiler-error-c3391.md)|"*type*"：泛型 "*generic_type*" 的泛型参数 "*parameter*" 的类型参数无效，它必须是不可以为 null 的值类型|
|[编译器错误 C3392](compiler-error-c3392.md)|"*type*"：泛型 "*generic_type*" 的泛型参数 "*parameter*" 的类型参数无效，它必须具有公共的无参数构造函数|
|[编译器错误 C3393](compiler-error-c3393.md)|constraint 子句有语法错误： "*identifier*" 不是一个类型|
|[编译器错误 C3394](compiler-error-c3394.md)|constraint 子句有语法错误：所发现的 "*symbol*" 应为类型|
|[编译器错误 C3395](compiler-error-c3395.md)|" *function*"：不能将 __declspec (dllexport) 应用于具有 __clrcall 调用约定的函数|
|[编译器错误 C3396](compiler-error-c3396.md)|'*class*。*成员*"：在"*namespace*"中找不到自定义特性|
|[编译器错误 C3397](compiler-error-c3397.md)|默认参数中不允许进行聚合初始化|
|[编译器错误 C3398](compiler-error-c3398.md)|"*operator*"：不能从 "*type*" 转换为 "*type*"。 源表达式必须是函数符号|
|[编译器错误 C3399](compiler-error-c3399.md)|"*type*"：创建泛型参数的实例时无法提供参数|

## <a name="see-also"></a>请参阅

[C/c + + 编译器和生成工具错误和警告](../compiler-errors-1/c-cpp-build-errors.md) \
[编译器错误 C2000 - C3999](../compiler-errors-1/compiler-errors-c2000-c3999.md)
