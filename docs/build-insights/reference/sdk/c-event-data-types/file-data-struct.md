---
title: FILE_DATA 结构
description: C++ Build Insights SDK FILE_DATA 结构参考。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- FILE_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 1a03c2c47be82fac2ee036a632e4df775f6c4f5f
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/29/2020
ms.locfileid: "92923596"
---
# <a name="file_data-structure"></a>FILE_DATA 结构

::: moniker range="<=msvc-140"

C++ Build Insights SDK 与 Visual Studio 2017 及更高版本兼容。 若要查看这些版本的文档，请将本文的 Visual Studio“版本”选择器控件设置为 Visual Studio 2017 或 Visual Studio 2019。 它位于此页面上目录表的顶部。

::: moniker-end
::: moniker range=">=msvc-150"

`FILE_DATA` 结构描述文件输入或输出。

## <a name="syntax"></a>语法

```cpp
typedef struct FILE_DATA_TAG
{
    const wchar_t*      Path;
    int                 TypeCode;

} FILE_DATA;
```

## <a name="members"></a>成员

| 名称 | 说明 |
|--|--|
| `Path` | 文件的绝对路径 |
| `TypeCode` | 描述文件类型的代码。 有关详细信息，请参阅 [FILE_TYPE_CODE](file-type-code-enum.md)。 |

::: moniker-end
