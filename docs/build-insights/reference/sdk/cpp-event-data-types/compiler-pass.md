---
title: CompilerPass 类
description: C++ 生成见解 SDK CompilerPass 类引用。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- CompilerPass
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 054bdf75dcfca42b8c202565fb44df671f17f912
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/25/2020
ms.locfileid: "88831614"
---
# <a name="compilerpass-class"></a>CompilerPass 类

::: moniker range="<=vs-2015"

C++ Build Insights SDK 与 Visual Studio 2017 及更高版本兼容。 若要查看这些版本的文档，请将本文的 Visual Studio“版本”选择器控件设置为 Visual Studio 2017 或 Visual Studio 2019。 它位于此页面上目录表的顶部。

::: moniker-end
::: moniker range=">=vs-2017"

`CompilerPass` 类与 [MatchEvent](../functions/match-event.md)、[MatchEventInMemberFunction](../functions/match-event-in-member-function.md)、[MatchEventStack](../functions/match-event-stack.md) 和 [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) 函数一起结合使用。 使用它来匹配 [BACK_END_PASS](../event-table.md#back-end-pass) 或 [FRONT_END_PASS](../event-table.md#front-end-pass) 事件。

## <a name="syntax"></a>语法

```cpp
class CompilerPass : public Activity
{
public:
    enum class PassCode
    {
        FRONT_END,
        BACK_END
    };

    CompilerPass(const RawEvent& event);

    PassCode       PassCode() const;
    const wchar_t* InputSourcePath() const;
    const wchar_t* OutputObjectPath() const;
};
```

## <a name="members"></a>成员

除了从自己的 [Activity](activity.md) 基类继承的成员外，`CompilerPass` 类还包含以下成员：

### <a name="constructors"></a>构造函数

[CompilerPass](#compiler-pass)

### <a name="enums"></a>枚举

#### <a name="passcode"></a>PassCode

|值|说明|
|-|-|
|FRONT_END|前端传递。|
|BACK_END|后端传递。|

### <a name="functions"></a>函数

[InputSourcePath](#input-source-path)\
[OutputObjectPath](#output-object-path)\
[PassCode](#pass-code)\

## <a name="compilerpass"></a><a name="compiler-pass"></a> CompilerPass

```cpp
CompilerPass(const RawEvent& event);
```

### <a name="parameters"></a>参数

*event*\
[BACK_END_PASS](../event-table.md#back-end-pass) 或 [FRONT_END_PASS](../event-table.md#front-end-pass) 事件。

## <a name="inputsourcepath"></a><a name="input-source-path"></a> InputSourcePath

```cpp
const wchar_t* InputSourcePath() const;
```

### <a name="return-value"></a>返回值

此编译器传递处理的输入源文件的绝对路径。

## <a name="outputobjectpath"></a><a name="output-object-path"></a> OutputObjectPath

```cpp
const wchar_t* OutputObjectPath() const;
```

### <a name="return-value"></a>返回值

此编译器传递生成的输出对象文件的绝对路径。

## <a name="passcode"></a><a name="pass-code"></a> PassCode

```cpp
PassCode PassCode() const;
```

### <a name="return-value"></a>返回值

用于指示此 CompilerPass 对象所表示的编译器传递的代码。

::: moniker-end
