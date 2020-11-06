---
title: RelogW
description: C++ Build Insights SDK RelogW 函数引用。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- RelogW
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: e01cf7ca769c60761999ca320a7f9a65b41a8ed6
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/29/2020
ms.locfileid: "92920055"
---
# <a name="relogw"></a>RelogW

::: moniker range="<=msvc-140"

C++ Build Insights SDK 与 Visual Studio 2017 及更高版本兼容。 若要查看这些版本的文档，请将本文的 Visual Studio“版本”选择器控件设置为 Visual Studio 2017 或 Visual Studio 2019。 它位于此页面上目录表的顶部。

::: moniker-end
::: moniker range=">=msvc-150"

`RelogW` 函数用于从输入 Windows 事件跟踪 (ETW) 跟踪读取 MSVC 事件，并将这些事件写入已修改的新 ETW 跟踪。

## <a name="syntax"></a>语法

```cpp
enum RESULT_CODE RelogW(
    const wchar_t*          inputLogFile,
    const wchar_t*          outputLogFile,
    const RELOG_DESCRIPTOR* relogDescriptor);
```

### <a name="parameters"></a>参数

inputLogFile\
要从中读取事件的输入 ETW 跟踪。

outputLogFile\
要在其中写入新事件的文件。

relogDescriptor\
指向 [RELOG_DESCRIPTOR](../other-types/relog-descriptor-struct.md) 对象的指针。 使用此对象配置重新记录会话。

### <a name="return-value"></a>返回值

[RESULT_CODE](../other-types/result-code-enum.md) 枚举中的结果代码。

::: moniker-end
