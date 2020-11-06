---
title: FileInput 类
description: C++ Build Insights SDK FileInput 类引用。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- FileInput
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 6e12336c10347f00ea2663116f2f308658775e0d
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/29/2020
ms.locfileid: "92920679"
---
# <a name="fileinput-class"></a>FileInput 类

::: moniker range="<=msvc-140"

C++ Build Insights SDK 与 Visual Studio 2017 及更高版本兼容。 若要查看这些版本的文档，请将本文的 Visual Studio“版本”选择器控件设置为 Visual Studio 2017 或 Visual Studio 2019。 它位于此页面上目录表的顶部。

::: moniker-end
::: moniker range=">=msvc-150"

`FileInput` 类与 [MatchEvent](../functions/match-event.md)、[MatchEventInMemberFunction](../functions/match-event-in-member-function.md)、[MatchEventStack](../functions/match-event-stack.md) 和 [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) 函数一起结合使用。 使用它来匹配 [FILE_INPUT](../event-table.md#file-input) 事件。

## <a name="syntax"></a>语法

```cpp
class FileInput : public SimpleEvent
{
public:
    enum class Type
    {
        OTHER               = FILE_TYPE_CODE_OTHER,
        OBJ                 = FILE_TYPE_CODE_OBJ,
        EXECUTABLE_IMAGE    = FILE_TYPE_CODE_EXECUTABLE_IMAGE,
        LIB                 = FILE_TYPE_CODE_LIB,
        IMP_LIB             = FILE_TYPE_CODE_IMP_LIB,
        EXP                 = FILE_TYPE_CODE_EXP
    };

    FileInput(const RawEvent& event);

    const wchar_t* Path() const;
    Type           Type() const;
};
```

## <a name="members"></a>成员

除了从自己的 [SimpleEvent](simple-event.md) 基类继承的成员外，`FileInput` 类还包含以下成员：

### <a name="constructors"></a>构造函数

[FileInput](#file-input)

### <a name="functions"></a>函数

[Path](#path)
[Type](#type)

## <a name="fileinput"></a><a name="file-input"></a> FileInput

```cpp
FileInput(const RawEvent& event);
```

### <a name="parameters"></a>参数

*event*\
[FILE_INPUT](../event-table.md#file-input) 事件。

## <a name="path"></a><a name="path"></a> Path

```cpp
const wchar_t Path() const;
```

### <a name="return-value"></a>返回值

输入文件的绝对路径。

## <a name="type"></a><a name="type"></a> 类型

```cpp
Type Type() const;
```

### <a name="return-value"></a>返回值

描述输入文件类型的代码。

::: moniker-end
