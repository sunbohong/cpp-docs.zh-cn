---
title: FILE_TYPE_CODE 枚举
description: C++ Build Insights SDK FILE_TYPE_CODE 枚举引用。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- FILE_TYPE_CODE
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: ddd625829e94786c0daddf0e78b914e225b2ecfb
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/29/2020
ms.locfileid: "92921018"
---
# <a name="file_type_code-enum"></a>FILE_TYPE_CODE 枚举

::: moniker range="<=msvc-140"

C++ Build Insights SDK 与 Visual Studio 2017 及更高版本兼容。 若要查看这些版本的文档，请将本文的 Visual Studio“版本”选择器控件设置为 Visual Studio 2017 或 Visual Studio 2019。 它位于此页面上目录表的顶部。

::: moniker-end
::: moniker range=">=msvc-150"

`FILE_TYPE_CODE` 枚举描述文件的类型。

## <a name="members"></a>成员

| 名称 | 值 | 说明 |
|--|--|--|
| `FILE_TYPE_CODE_OTHER` | 0 (0x00000000) | 此枚举中未列出的文件类型。 |
| `FILE_TYPE_CODE_OBJ` | 1 (0x00000001) | 对象 (\*.obj) 文件。 |
| `FILE_TYPE_CODE_EXECUTABLE_IMAGE` | 2 (0x00000002) | 可执行文件 (\*.exe) 或 DLL (\*.dll) 文件。 |
| `FILE_TYPE_CODE_LIB` | 3 (0x00000003) | 静态库 (*.lib) 文件。 |
| `FILE_TYPE_CODE_IMP_LIB` | 4 (0x00000004) | 导入库 (*.lib) |
| `FILE_TYPE_CODE_EXP` | 5 (0x00000005) | 导出 (*.exp) 文件。 |

## <a name="remarks"></a>备注

::: moniker-end
