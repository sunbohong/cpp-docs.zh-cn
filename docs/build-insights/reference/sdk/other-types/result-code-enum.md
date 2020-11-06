---
title: RESULT_CODE 枚举
description: C++ Build Insights SDK RESULT_CODE 枚举引用。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- RESULT_CODE
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 3d9d18d535d15d04a2e449bdbbf693364276a518
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/29/2020
ms.locfileid: "92922411"
---
# <a name="result_code-enum"></a>RESULT_CODE 枚举

::: moniker range="<=msvc-140"

C++ Build Insights SDK 与 Visual Studio 2017 及更高版本兼容。 若要查看这些版本的文档，请将本文的 Visual Studio“版本”选择器控件设置为 Visual Studio 2017 或 Visual Studio 2019。 它位于此页面上目录表的顶部。

::: moniker-end
::: moniker range=">=msvc-150"

`RESULT_CODE` 枚举描述成功和失败情况。

## <a name="members"></a>成员

| 名称 | 值 | 说明 |
|--|--|--|
| `RESULT_CODE_SUCCESS` | 0 (0x00000000) | 操作成功。 |
| `RESULT_CODE_FAILURE_ANALYSIS_ERROR` | 1 (0x00000001) | [ANALYSIS_DESCRIPTOR](analysis-descriptor-struct.md) 或 [RELOG_DESCRIPTOR](relog-descriptor-struct.md) 中的回调函数之一返回 `CALLBACK_CODE_ANALYSIS_FAILURE` 值。 此值是 [CALLBACK_CODE](callback-code-enum.md) 枚举的成员。 |
| `RESULT_CODE_FAILURE_CANCELLED` | 2 (0x00000002) | [ANALYSIS_DESCRIPTOR](analysis-descriptor-struct.md) 或 [RELOG_DESCRIPTOR](relog-descriptor-struct.md) 中的回调函数之一返回 `CALLBACK_CODE_ANALYSIS_CANCEL` 值。 此值是 [CALLBACK_CODE](callback-code-enum.md) 枚举的成员。 |
| `RESULT_CODE_FAILURE_INVALID_INPUT_LOG_FILE` | 3 (0x00000003) | 指定的输入 Windows 事件跟踪 (ETW) 跟踪无效。 |
| `RESULT_CODE_FAILURE_INVALID_OUTPUT_LOG_FILE` | 4 (0x00000004) | 指定的输出 ETW 跟踪无效。 |
| `RESULT_CODE_FAILURE_MISSING_ANALYSIS_CALLBACK` | 5 (0x00000005) | [ANALYSIS_CALLBACKS](analysis-callbacks-struct.md) 结构未正确初始化。 |
| `RESULT_CODE_FAILURE_MISSING_RELOG_CALLBACK` | 6 (0x00000006) | [RELOG_CALLBACKS](relog-callbacks-struct.md) 结构未正确初始化。 |
| `RESULT_CODE_FAILURE_OPEN_INPUT_TRACE` | 7 (0x00000007) | 无法打开输入 ETW 跟踪。 |
| `RESULT_CODE_FAILURE_PROCESS_TRACE` | 8 (0x00000008) | 处理输入 ETW 跟踪时出错。 |
| `RESULT_CODE_FAILURE_START_RELOGGER` | 9 (0x00000009) | 尝试启动重新记录会话时出错。 |
| `RESULT_CODE_FAILURE_DROPPED_EVENTS` | 10 (0x0000000A) | 输入 ETW 跟踪缺少重要事件。 |
| `RESULT_CODE_FAILURE_UNSUPPORTED_OS` | 11 (0x0000000B) | 在不受支持的 Windows 版本上使用 C++ Build Insights。 |
| `RESULT_CODE_FAILURE_INVALID_TRACING_SESSION_NAME` | 12 (0x0000000C) | 提供的会话名称无效。 |
| `RESULT_CODE_FAILURE_INSUFFICIENT_PRIVILEGES` | 13 (0x0000000D) | 此操作需要管理员特权。 |
| `RESULT_CODE_FAILURE_GENERATE_GUID` | 14 (0x0000000E) | 生成 GUID 时出错。 |
| `RESULT_CODE_FAILURE_OBTAINING_TEMP_DIRECTORY` | 15 (0x0000000F) | 尝试确定临时目录路径时出错。 |
| `RESULT_CODE_FAILURE_CREATE_TEMPORARY_DIRECTORY` | 16 (0x00000010) | 尝试为正在启动的跟踪会话创建临时目录时出错。 |
| `RESULT_CODE_FAILURE_START_SYSTEM_TRACE` | 17 (0x00000011) | 尝试启动系统跟踪时出错。 |
| `RESULT_CODE_FAILURE_START_MSVC_TRACE` | 18 (0x00000012) | 尝试启动 MSVC 跟踪时出错。 |
| `RESULT_CODE_FAILURE_STOP_MSVC_TRACE` | 19 (0x00000013) | 尝试停止 MSVC 跟踪时出错。 |
| `RESULT_CODE_FAILURE_STOP_SYSTEM_TRACE` | 20 (0x00000014) | 尝试启动系统跟踪时出错。 |
| `RESULT_CODE_FAILURE_SESSION_DIRECTORY_RESOLUTION` | 21 (0x00000015) | 已停止跟踪，但找不到跟踪会话的临时目录。 |
| `RESULT_CODE_FAILURE_MSVC_TRACE_FILE_NOT_FOUND` | 22 (0x00000016) | 找不到正在停止的 MSVC 跟踪的跟踪文件。 |
| `RESULT_CODE_FAILURE_MERGE_TRACES` | 23 (0x00000017) | 使用内核跟踪控制合并跟踪时出错。 |
| `RESULT_CODE_FAILURE_UNKNOWN_ERROR` | 24 (0x00000018) | 发生未知错误。 |

::: moniker-end
