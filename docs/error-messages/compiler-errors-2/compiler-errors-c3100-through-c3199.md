---
description: 了解有关以下内容的详细信息：编译器错误 C3100 到 C3199
title: 编译器错误 C3100 - C3199
ms.date: 04/21/2019
f1_keywords:
- C3102
- C3105
- C3107
- C3108
- C3109
- C3111
- C3112
- C3119
- C3122
- C3123
- C3124
- C3125
- C3127
- C3128
- C3129
- C3143
- C3144
- C3146
- C3147
- C3148
- C3151
- C3158
- C3164
- C3165
- C3169
- C3177
- C3178
- C3184
- C3188
- C3191
- C3193
helpviewer_keywords:
- C3102
- C3105
- C3107
- C3108
- C3109
- C3111
- C3112
- C3119
- C3122
- C3123
- C3124
- C3125
- C3127
- C3128
- C3129
- C3143
- C3144
- C3146
- C3147
- C3148
- C3151
- C3158
- C3164
- C3165
- C3169
- C3177
- C3178
- C3184
- C3188
- C3191
- C3193
ms.assetid: 7bc40c2f-6a8d-488a-b665-f39375afee77
ms.openlocfilehash: d2398fa8ae783a34662efc361730a5054a982458
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97238708"
---
# <a name="compiler-errors-c3100-through-c3199"></a>编译器错误 C3100 - C3199

文档的本节中的文章介绍了编译器生成的错误消息的子集。

[!INCLUDE[error-boilerplate](../../error-messages/includes/error-boilerplate.md)]

## <a name="error-messages"></a>错误消息

|错误|消息|
|-----------|-------------|
|[编译器错误 C3100](compiler-error-c3100.md)|"*identifier*"：未知的特性限定符|
|[编译器错误 C3101](compiler-error-c3101.md)|命名特性参数 "*identifier*" 的表达式非法|
|编译器错误 C3102|已过时。|
|[编译器错误 C3103](compiler-error-c3103.md)|"*identifier*"：重复的命名参数|
|[编译器错误 C3104](compiler-error-c3104.md)|非法的特性参数|
|编译器错误 C3105|"*symbol*"：不能用作特性|
|[编译器错误 C3106](compiler-error-c3106.md)|"*attribute*"：未命名参数必须在命名参数之前|
|编译器错误 C3107|"*attribute*"：不能定义本机特性的成员函数|
|编译器错误 C3108|无法推导出类型，因为初始值设定项列表不是表达式|
|编译器错误 C3109|"*identifier*"：接口方法必须使用 "__stdcall" 或 "__cdecl" 调用约定|
|[编译器错误 C3110](compiler-error-c3110.md)|"*function*"：不能重载 COM 接口方法|
|编译器错误 C3111|初始值设定项列表不能用作模板参数的默认参数|
|编译器错误 C3112|"*interface*"：接口只能在全局或命名空间范围内声明|
|[编译器错误 C3113](compiler-error-c3113.md)|"interface/enum" 不能是模板/泛型|
|[编译器错误 C3114](compiler-error-c3114.md)|"*identifier*"：不是有效的命名特性参数|
|[编译器错误 C3115](compiler-error-c3115.md)|"*attribute*"：在 "*构造*" 上不允许使用此特性|
|[编译器错误 C3116](compiler-error-c3116.md)|"*说明符*"：接口方法的存储类无效|
|[编译器错误 C3117](compiler-error-c3117.md)|"*interface*"：接口只能有一个基类|
|[编译器错误 C3118](compiler-error-c3118.md)|"*interface*"：接口不支持虚拟继承|
|编译器错误 C3119|不允许 alignas (void) |
|[编译器错误 C3120](compiler-error-c3120.md)|"*identifier*"：接口方法不能接受变量参数列表|
|[编译器错误 C3121](compiler-error-c3121.md)|无法更改类 "*class*" 的 GUID|
|编译器错误 C3122|"*interface*"： WinRT 泛型接口不能有 GUID|
|编译器错误 C3123|WinRT 泛型接口不能有约束|
|编译器错误 C3124|"有符号 char" 不是有效的 WinRT 数据类型。 请改用 "无符号 char"、"wchar_t" 或 "已签名 short"。|
|编译器错误 C3125|"*type*"：类型无法直接或间接从 "Platform：： Exception" 派生|
|[编译器错误 C3126](compiler-error-c3126.md)|无法在托管的/WinRT 类型 "*type*" 内定义联合 "*union*"|
|编译器错误 C3127|"*type*"： "*特征*" 特征只能在 WinRT ref 类上使用|
|编译器错误 C3128|"*type*" 没有由 "*type*" 引入的 vtable|
|编译器错误 C3129|"*type*"： __default_vptr_for_base 只能在本地定义的多态类型和基上使用|
|[编译器错误 C3130](compiler-error-c3130.md)|内部编译器错误：未能将插入的代码块写入 PDB|
|[编译器错误 C3131](compiler-error-c3131.md)|项目必须具有 "module" 特性和 "name" 属性|
|[编译器错误 C3132](compiler-error-c3132.md)|"*parameter*"：参数数组只能应用于 "一维托管/WinRT 数组" 类型的形参|
|[编译器错误 C3133](compiler-error-c3133.md)|特性不能应用于 c + + varargs|
|[编译器错误 C3134](compiler-error-c3134.md)|"*value*"：特性参数 "*argument*" 的值没有有效的类型 "*type*"|
|[编译器错误 C3135](compiler-error-c3135.md)|"*identifier*"：属性不能有 "const" 或 "volatile" 类型|
|[编译器错误 C3136](compiler-error-c3136.md)|"*interface*"： COM 接口只能从另一个 com 接口继承，"*interface*" 不是 com 接口|
|[编译器错误 C3137](compiler-error-c3137.md)|"*identifier*"：属性不能初始化|
|[编译器错误 C3138](compiler-error-c3138.md)|"*identifier*"： "*attribute*" 接口必须从 idispatch 继承，或者从继承自 idispatch 的接口继承|
|[编译器错误 C3139](compiler-error-c3139.md)|"*type*"：不能导出没有成员的 UDT|
|[编译器错误 C3140](compiler-error-c3140.md)|同一编译单元中不能有多个 "module" 特性|
|[编译器错误 C3141](compiler-error-c3141.md)|"*interface*"：接口只支持公共继承|
|[编译器错误 C3142](compiler-error-c3142.md)|"*property*"：不能采用属性的地址|
|编译器错误 C3143|"*argument*"：特性参数不能有多个值|
|编译器错误 C3144|"*attribute*"：特性需要显式参数，"*argument*" 未命名|
|[编译器错误 C3145](compiler-error-c3145.md)|"*identifier*"：全局或静态变量不能具有托管/WinRT 类型 "*type*"|
|编译器错误 C3146|已过时。|
|编译器错误 C3147|已过时。|
|编译器错误 C3148|已过时。|
|[编译器错误 C3149](compiler-error-c3149.md)|"*type*"：不能在没有顶级 "*token*" 的情况下使用此类型|
|[编译器错误 C3150](compiler-error-c3150.md)|"*构造*"： "*attribute*" 只能应用于类、结构、接口、数组或指针|
|编译器错误 C3151|已过时。|
|[编译器错误 C3152](compiler-error-c3152.md)|"*function*"： "*关键字*" 只能应用于类、结构或虚拟成员函数|
|[编译器错误 C3153](compiler-error-c3153.md)|"*interface*"：不能创建接口的实例|
|[编译器错误 C3154](compiler-error-c3154.md)|省略号之前应为 "，"。 参数数组函数不支持非逗号分隔的省略号。|
|[编译器错误 C3155](compiler-error-c3155.md)|属性索引器中不允许使用特性|
|[编译器错误 C3156](compiler-error-c3156.md)|"*class*"：不能有托管/WinRT 类型的本地定义|
|[编译器错误 C3157](compiler-error-c3157.md)|ParamArray 特性只能应用于最后一个参数|
|编译器错误 C3158|"*function*"： "*关键字*" 只能应用于虚成员函数|
|[编译器错误 C3159](compiler-error-c3159.md)|"*identifier*"：不能声明指向值类型的指针数组|
|[编译器错误 C3160](compiler-error-c3160.md)|"*type*"：托管/WinRT 类的数据成员不能具有此类型|
|[编译器错误 C3161](compiler-error-c3161.md)|"*interface*"：接口中的嵌套类、结构或接口是非法的;类或结构中的嵌套接口是非法的|
|[编译器错误 C3162](compiler-error-c3162.md)|"*type*"：具有析构函数的引用类型不能用作静态数据成员 "*member*" 的类型|
|[编译器错误 C3163](compiler-error-c3163.md)|"*class*"：特性与以前的声明不一致|
|编译器错误 C3164|已过时。|
|编译器错误 C3165|"*value*"：无法转换为整数或浮点值|
|[编译器错误 C3166](compiler-error-c3166.md)|已过时。 "*type*"：托管或 WinRT 类的数据成员不能具有类型 "*pointer_type* 内部 *managed_pointer_type*"|
|[编译器错误 C3167](compiler-error-c3167.md)|无法初始化 .NET Framework：请确保它已安装|
|[编译器错误 C3168](compiler-error-c3168.md)|"*type*"：枚举的基础类型非法|
|编译器错误 C3169|"*type*"：无法从 "*type*" 推导 "auto" 的类型|
|[编译器错误 C3170](compiler-error-c3170.md)|项目中不能有不同的模块标识符|
|[编译器错误 C3171](compiler-error-c3171.md)|"*module*"：在项目中不能指定不同的模块特性|
|[编译器错误 C3172](compiler-error-c3172.md)|"*identifier*"：不能在项目中指定不同的 idl_module 特性|
|[编译器错误 C3173](compiler-error-c3173.md)|idl 合并中的版本不匹配|
|[编译器错误 C3174](compiler-error-c3174.md)|未指定模块特性|
|[编译器错误 C3175](compiler-error-c3175.md)|"*function*"：不能从非托管函数 "*function*" 调用托管类型的方法|
|[编译器错误 C3176](compiler-error-c3176.md)|"*type*"：不能声明局部值类型|
|编译器错误 C3177|不能对包含 "*type*" 的类型使用转换函数|
|编译器错误 C3178|"*type*"：不能在具有默认参数的函数中使用 ParamArray|
|[编译器错误 C3179](compiler-error-c3179.md)|不允许使用未命名的托管/WinRT 类型|
|[编译器错误 C3180](compiler-error-c3180.md)|"*type*"：名称超出了 "*number*" 个字符的元数据限制|
|[编译器错误 C3181](compiler-error-c3181.md)|"*type*"：*运算符* 的操作数无效|
|[编译器错误 C3182](compiler-error-c3182.md)|"*type*"：托管的/WinRT 类型中的成员 using 声明或访问声明非法|
|[编译器错误 C3183](compiler-error-c3183.md)|无法在托管的/WinRT 类型 "*class*" 内定义未命名的类、结构或联合|
|编译器错误 C3184|已过时。|
|[编译器错误 C3185](compiler-error-c3185.md)|"typeid"：在托管/WinRT 类型 "*type*" 中使用，请改用 "*operator*"|
|编译器错误 C3186|已过时。|
|[编译器错误 C3187](compiler-error-c3187.md)|"*identifier*"：仅在函数体内可用|
|编译器错误 C3188|已过时。|
|[编译器错误 C3189](compiler-error-c3189.md)|"typeid<*声明符*>"：不再支持此语法，请改用：： typeid|
|[编译器错误 C3190](compiler-error-c3190.md)|具有所提供的模板参数的 "*声明符*" 不是 "*type*" 的任何成员函数的显式实例化|
|编译器错误 C3191|已过时。|
|[编译器错误 C3192](compiler-error-c3192.md)|语法错误： "^" 不是前缀运算符 (是否表示 "*"？ ) |
|编译器错误 C3193|"*构造*"：需要 "/clr" 或 "/ZW" 命令行选项|
|[编译器错误 C3194](compiler-error-c3194.md)|"*type*"：值类型不能具有赋值运算符|
|[编译器错误 C3195](compiler-error-c3195.md)|"*关键字*"：是保留值，不能用作 ref 类或值类型的成员。 必须使用 "operator" 关键字定义 CLR/WinRT 运算符|
|[编译器错误 C3196](compiler-error-c3196.md)|"*identifier*"：多次使用|
|[编译器错误 C3197](compiler-error-c3197.md)|"*关键字*"：只能在定义中使用|
|[编译器错误 C3198](compiler-error-c3198.md)|使用浮点 pragma 无效： fenv_access 杂注仅在精确模式下运行|
|[编译器错误 C3199](compiler-error-c3199.md)|使用浮点 pragma 无效：在非精确模式下不支持异常|

## <a name="see-also"></a>请参阅

[C/c + + 编译器和生成工具错误和警告](../compiler-errors-1/c-cpp-build-errors.md) \
[编译器错误 C2000 - C3999](../compiler-errors-1/compiler-errors-c2000-c3999.md)
