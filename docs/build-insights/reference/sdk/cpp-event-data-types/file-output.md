---
title: FileOutput 类
description: C++ Build Insights SDK FileOutput 类引用。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- FileOutput
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 65e23715d8ac47a8653215e8bd3ee7a43bbe80a3
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/29/2020
ms.locfileid: "92923251"
---
# <a name="fileoutput-class"></a>FileOutput 类

::: moniker range="<=msvc-140"

C++ Build Insights SDK 与 Visual Studio 2017 及更高版本兼容。 若要查看这些版本的文档，请将本文的 Visual Studio“版本”选择器控件设置为 Visual Studio 2017 或 Visual Studio 2019。 它位于此页面上目录表的顶部。

::: moniker-end
::: moniker range=">=msvc-150"

`FileOutput` 类与 [MatchEvent](../functions/match-event.md)、[MatchEventInMemberFunction](../functions/match-event-in-member-function.md)、[MatchEventStack](../functions/match-event-stack.md) 和 [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) 函数一起结合使用。 使用它来匹配 [EXECUTABLE_IMAGE_OUTPUT](../event-table.md#executable-image-output)、[EXP_OUTPUT](../event-table.md#exp-output)、[IMP_LIB_OUTPUT](../event-table.md#imp-lib-output)、[LIB_OUTPUT](../event-table.md#lib-output) 或 [OBJ_OUTPUT](../event-table.md#obj-output) 事件。

## <a name="syntax"></a>语法

```cpp
class FileOutput : public SimpleEvent
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

    FileOutput(const RawEvent& event);

    const wchar_t* Path() const;
    Type           Type() const;
};
```

## <a name="members"></a>成员

除了从自己的 [SimpleEvent](simple-event.md) 基类继承的成员外，`FileOutput` 类还包含以下成员：

### <a name="constructors"></a>构造函数

[FileOutput](#file-output)

### <a name="functions"></a>函数

[Path](#path)
[Type](#type)

## <a name="fileoutput"></a><a name="file-output"></a> FileOutput

```cpp
FileOutput(const RawEvent& event);
```

### <a name="parameters"></a>参数

*event*\
[EXECUTABLE_IMAGE_OUTPUT](../event-table.md#executable-image-output)、[EXP_OUTPUT](../event-table.md#exp-output)、[IMP_LIB_OUTPUT](../event-table.md#imp-lib-output)、[LIB_OUTPUT](../event-table.md#lib-output) 或 [OBJ_OUTPUT](../event-table.md#obj-output) 事件。

## <a name="path"></a><a name="path"></a> Path

```cpp
const wchar_t Path() const;
```

### <a name="return-value"></a>返回值

输出文件的绝对路径。

## <a name="type"></a><a name="type"></a> 类型

```cpp
Type Type() const;
```

### <a name="return-value"></a>返回值

描述输出文件类型的代码。

::: moniker-end
