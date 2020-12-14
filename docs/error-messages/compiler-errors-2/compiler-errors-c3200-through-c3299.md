---
description: 了解有关以下内容的详细信息：编译器错误 C3200 到 C3299
title: 编译器错误 C3200 - C3299
ms.date: 04/21/2019
f1_keywords:
- C3220
- C3221
- C3245
- C3249
- C3250
- C3256
- C3257
- C3258
- C3259
- C3260
- C3261
- C3263
- C3267
- C3281
- C3294
helpviewer_keywords:
- C3220
- C3221
- C3245
- C3249
- C3250
- C3256
- C3257
- C3258
- C3259
- C3260
- C3261
- C3263
- C3267
- C3281
- C3294
ms.assetid: 6b3104f6-63bc-4823-b6f3-b8a16be4b87f
ms.openlocfilehash: e54d980634372099d76d9f30020f68f3f4affb59
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97238656"
---
# <a name="compiler-errors-c3200-through-c3299"></a>编译器错误 C3200 - C3299

文档的本节中的文章介绍了编译器生成的错误消息的子集。

[!INCLUDE[error-boilerplate](../../error-messages/includes/error-boilerplate.md)]

## <a name="error-messages"></a>错误消息

|错误|消息|
|-----------|-------------|
|[编译器错误 C3200](compiler-error-c3200.md)|"*type*"：模板参数 "*parameter*" 的模板参数无效，应为类模板|
|[编译器错误 C3201](compiler-error-c3201.md)|类模板 "*template*" 的模板参数列表与模板参数 "*parameter*" 的模板参数列表不匹配|
|[编译器错误 C3202](compiler-error-c3202.md)|"*identifier*"：默认参数无效，应为类模板|
|[编译器错误 C3203](compiler-error-c3203.md)|"*identifier*"：未专用化的类模板/泛型不能用作模板/泛型参数 "*parameter*" 的模板/泛型参数，应为 real 类型|
|[编译器错误 C3204](compiler-error-c3204.md)|不能从 catch 块内调用 "*function*"|
|[编译器错误 C3205](compiler-error-c3205.md)|缺少模板模板参数 "*identifier*" 的参数列表|
|[编译器错误 C3206](compiler-error-c3206.md)|"*function*"： "*template*" 的模板/泛型参数无效，缺少类模板/泛型 "*type*" 的模板/泛型参数列表|
|[编译器错误 C3207](compiler-error-c3207.md)|"*function*"： "*parameter*" 的模板参数无效，应为类模板|
|[编译器错误 C3208](compiler-error-c3208.md)|"*function*"：类模板 "*template*" 的模板参数列表与模板模板参数 "*parameter*" 的模板参数列表不匹配|
|[编译器错误 C3209](compiler-error-c3209.md)|"*type*"：泛型类必须是托管的/WinRT 类|
|[编译器错误 C3210](compiler-error-c3210.md)|"*identifier*"：访问声明只能应用于基类成员|
|[编译器错误 C3211](compiler-error-c3211.md)|"*function*"：显式专用化正在使用部分专用化语法，请改用模板 <> |
|[编译器错误 C3212](compiler-error-c3212.md)|"*function*"：模板成员的显式专用化必须是显式专用化的成员|
|[编译器错误 C3213](compiler-error-c3213.md)|基类 "*class*" 的可访问性低于 "*derived_class*"|
|[编译器错误 C3214](compiler-error-c3214.md)|"*argument*"：泛型 "*type*" 的泛型参数 "*parameter*" 的类型参数无效，不符合约束 "*constraint*"|
|[编译器错误 C3215](compiler-error-c3215.md)|"*e*"：泛型类型参数已由 "*e*" 进行约束|
|[编译器错误 C3216](compiler-error-c3216.md)|约束必须是泛型参数，而不能是 "*type*"|
|[编译器错误 C3217](compiler-error-c3217.md)|"*parameter*"：泛型参数不能在此声明中进行约束|
|[编译器错误 C3218](compiler-error-c3218.md)|"*type*"：类型不允许作为约束|
|[编译器错误 C3219](compiler-error-c3219.md)|"*parameter*"：泛型参数不能由多个非接口约束： "*type*"|
|编译器错误 C3220|"*interface*"：接口不能有 progid|
|编译器错误 C3221|"*member*"：成员上不允许有多个 "default" 和 "case" 特性|
|[编译器错误 C3222](compiler-error-c3222.md)|"*function*"：不能为托管/WinRT 类型或泛型函数的成员函数声明默认参数|
|[编译器错误 C3223](compiler-error-c3223.md)|"*property*"：不能将 "typeid" 应用于属性|
|[编译器错误 C3224](compiler-error-c3224.md)|"*type*"：没有任何重载泛型类采用 "*number*" 泛型类型参数|
|[编译器错误 C3225](compiler-error-c3225.md)|"*argument*" 的泛型类型参数不能是 "*type*"，它必须是值类型或引用类型的句柄|
|[编译器错误 C3226](compiler-error-c3226.md)|泛型声明内不允许出现模板声明|
|[编译器错误 C3227](compiler-error-c3227.md)|"*type*"：不能使用 "*operator*" 来分配泛型类型|
|[编译器错误 C3228](compiler-error-c3228.md)|"*function*"： "*argument*" 的泛型类型参数不能是 "*type*"，它必须是值类型或句柄类型|
|[编译器错误 C3229](compiler-error-c3229.md)|"*type*"：不允许泛型类型参数上的间接寻址|
|[编译器错误 C3230](compiler-error-c3230.md)|"*function*"： "*argument*" 的模板类型参数不能包含泛型类型参数： "*type*"|
|[编译器错误 C3231](compiler-error-c3231.md)|"*type*"：模板类型参数不能使用泛型类型参数|
|[编译器错误 C3232](compiler-error-c3232.md)|"*parameter*"：泛型类型参数不能用于限定名中|
|[编译器错误 C3233](compiler-error-c3233.md)|"*type*"：泛型类型参数已被约束|
|[编译器错误 C3234](compiler-error-c3234.md)|泛型类可能无法从泛型类型参数派生|
|[编译器错误 C3235](compiler-error-c3235.md)|"*特殊化*"：不允许显式或部分专用化泛型类|
|[编译器错误 C3236](compiler-error-c3236.md)|不允许显式实例化泛型|
|[编译器错误 C3237](compiler-error-c3237.md)|"*class*"：泛型类不能是自定义属性|
|[编译器错误 C3238](compiler-error-c3238.md)|"*type*"：具有此名称的类型已转发到程序集 "*assembly*"|
|[编译器错误 C3239](compiler-error-c3239.md)|"*type*"：公共语言运行时不允许使用指向内部/固定指针的指针|
|[编译器错误 C3240](compiler-error-c3240.md)|"*identifier*"：必须是 "*type*" 的非重载抽象成员函数|
|[编译器错误 C3241](compiler-error-c3241.md)|"*member*"：此方法不是由 "*interface*" 引入|
|[编译器错误 C3242](compiler-error-c3242.md)|"*function*"：只能显式重写虚函数|
|[编译器错误 C3243](compiler-error-c3243.md)|"*interface*" 未引入任何重载函数|
|[编译器错误 C3244](compiler-error-c3244.md)|"*member*"：此方法由 "*interface1*" 引入，而不是 "*interface2*"|
|编译器错误 C3245|"*function*"：使用变量模板需要模板参数列表|
|[编译器错误 C3246](compiler-error-c3246.md)|"*class*"：不能从 "*base_class*" 继承，因为它已声明为 "*继承*"|
|[编译器错误 C3247](compiler-error-c3247.md)|"*coclass*"：组件类不能继承自另一个组件类 "*base_class*"|
|[编译器错误 C3248](compiler-error-c3248.md)|已过时。 "*function*"：声明为 "sealed" 的函数不能由 "*function*" 重写|
|编译器错误 C3249|"constexpr" 函数的语句或子表达式非法|
|编译器错误 C3250|"*声明*"：不允许在 "constexpr" 函数体中进行声明|
|[编译器错误 C3251](compiler-error-c3251.md)|无法调用在数值类型实例上的基类方法|
|[编译器错误 C3252](compiler-error-c3252.md)|"*function*"：无法降低托管/WinRT 类型中的虚方法的可访问性|
|[编译器错误 C3253](compiler-error-c3253.md)|"*function*"：显式重写时出错|
|[编译器错误 C3254](compiler-error-c3254.md)|"*function*"：类包含显式重写 "*function*"，但不从包含函数声明的接口派生|
|[编译器错误 C3255](compiler-error-c3255.md)|"*type*"：在本机堆上无法动态分配此值类型对象|
|编译器错误 C3256|"*function*"：变量使用不生成常数表达式|
|编译器错误 C3257|已过时。|
|编译器错误 C3258|已过时。|
|编译器错误 C3259|"constexpr" 函数只能有一个 return 语句|
|编译器错误 C3260|"*token*"：跳过 lambda 主体之前)  (的意外标记|
|编译器错误 C3261|返回托管/WinRT 数组的函数在声明的结尾处必须有数组括号： "*identifier* ( ... ) []"|
|[编译器错误 C3262](compiler-error-c3262.md)|无效的数组索引：为 *数字* 维 "*type*" 指定了 *数字* 维度 (s) |
|编译器错误 C3263|已过时。|
|[编译器错误 C3264](compiler-error-c3264.md)|"*identifier*"：类构造函数不能有返回类型|
|[编译器错误 C3265](compiler-error-c3265.md)|无法在非托管的 "*unmanaged_construct*" 中声明托管的 "*managed_construct*"|
|[编译器错误 C3266](compiler-error-c3266.md)|"*function*"：类构造函数必须具有 "void" 参数列表|
|编译器错误 C3267|已过时。|
|[编译器错误 C3268](compiler-error-c3268.md)|"*function*"：泛型函数或泛型类的成员函数不能有变量参数列表|
|[编译器错误 C3269](compiler-error-c3269.md)|"*function*"：托管/WinRT 类型的成员函数不能用 "..." 声明|
|[编译器错误 C3270](compiler-error-c3270.md)|"*field*"： FieldOffset 特性只能在 StructLayout (LayoutKind：： Explicit 的上下文中使用) |
|[编译器错误 C3271](compiler-error-c3271.md)|"*field*"： FieldOffset 特性的值 "*number*" 无效|
|[编译器错误 C3272](compiler-error-c3272.md)|"*symbol*"：符号需要 FieldOffset，因为它是使用 StructLayout (LayoutKind：： Explicit 定义的结构/类 *type_name* 的成员) |
|[编译器错误 C3273](compiler-error-c3273.md)|"*关键字*"：在 c + + try 块上不允许|
|[编译器错误 C3274](compiler-error-c3274.md)|最后/&#95;&#95;，无需匹配 try|
|[编译器错误 C3275](compiler-error-c3275.md)|"*identifier*"：不能使用不带限定符的符号|
|[编译器错误 C3276](compiler-error-c3276.md)|"*关键字*"：跳出/&#95;&#95;finally 块在终止处理期间具有未定义的行为|
|[编译器错误 C3277](compiler-error-c3277.md)|不能在托管 "*type*" 内定义非托管枚举 "*enumeration*"|
|[编译器错误 C3278](compiler-error-c3278.md)|接口或纯方法 "*function*" 的直接调用将在运行时失败|
|[编译器错误 C3279](compiler-error-c3279.md)|不允许对在 cli 命名空间中声明的类模板进行部分专用化、显式专用化和显式实例化|
|[编译器错误 C3280](compiler-error-c3280.md)|"*function*"：托管类型的成员函数不能编译为非托管函数|
|编译器错误 C3281|"*function*"：全局运算符的签名中不能包含托管/WinRT 类型 "*type*"|
|[编译器错误 C3282](compiler-error-c3282.md)|泛型参数列表只能出现在托管/WinRT 类、结构或函数上|
|[编译器错误 C3283](compiler-error-c3283.md)|"*interface*"：接口不能有实例构造函数|
|[编译器错误 C3284](compiler-error-c3284.md)|函数 "*声明*" 的泛型参数 "*parameter*" 的约束必须与函数 "*声明*" 的泛型参数 "*parameter*" 的约束匹配|
|[编译器错误 C3285](compiler-error-c3285.md)|for each 语句不能在 "*type*" 类型的变量上操作|
|[编译器错误 C3286](compiler-error-c3286.md)|"*说明符*"：迭代变量不能包含任何存储类说明符|
|[编译器错误 C3287](compiler-error-c3287.md)|类型 "*type*" (GetEnumerator 的返回类型) 必须具有合适的公共 MoveNext 成员函数和公共的 Current 属性|
|[编译器错误 C3288](compiler-error-c3288.md)|"*type*"：非法取消对句柄类型的引用|
|[编译器错误 C3289](compiler-error-c3289.md)|"*identifier*"：不能索引普通属性|
|[编译器错误 C3290](compiler-error-c3290.md)|"*type*"：普通属性不能具有引用类型|
|[编译器错误 C3291](compiler-error-c3291.md)|"default"：不能是普通属性的名称|
|[编译器错误 C3292](compiler-error-c3292.md)|cli 命名空间不能重新打开|
|[编译器错误 C3293](compiler-error-c3293.md)|"*identifier*"：使用 "default" 访问类 "*class*" (索引器) 的默认属性|
|编译器错误 C3294:|已过时。|
|[编译器错误 C3295](compiler-error-c3295.md)|"#pragma *说明符*" 只能在全局范围或命名空间范围内使用|
|[编译器错误 C3296](compiler-error-c3296.md)|"*identifier*"：已存在具有此名称的属性|
|[编译器错误 C3297](compiler-error-c3297.md)|" *e*"：不能使用 " *e*" 作为约束，因为 " *e*" 具有值约束|
|[编译器错误 C3298](compiler-error-c3298.md)|" *e*"：不能使用 " *e*" 作为约束，因为 " *e*" 具有 ref 约束，而 " *e*" 具有值约束|
|[编译器错误 C3299](compiler-error-c3299.md)|" *function*"：不能指定约束，因为这些约束是从基方法继承的|

## <a name="see-also"></a>请参阅

[C/c + + 编译器和生成工具错误和警告](../compiler-errors-1/c-cpp-build-errors.md) \
[编译器错误 C2000 - C3999](../compiler-errors-1/compiler-errors-c2000-c3999.md)
