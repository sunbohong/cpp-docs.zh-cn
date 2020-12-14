---
description: 了解详细信息：失败挂钩
title: 失败挂钩
ms.date: 11/04/2016
helpviewer_keywords:
- delayed loading of DLLs, failure hooks
ms.assetid: 12bb303b-ffe6-4471-bffe-9ef4f8bb2d30
ms.openlocfilehash: a0e74e3413fc81505941dd6f4545988a0d39436f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97200723"
---
# <a name="failure-hooks"></a>失败挂钩

启用失败挂钩的方式与 [通知挂钩](notification-hooks.md)相同。 挂钩例程需要返回合适的值，以便处理可以继续 (HINSTANCE 或 FARPROC) 或0，以指示应引发异常。

引用用户定义函数的指针变量是：

```
// This is the failure hook, dliNotify = {dliFailLoadLib|dliFailGetProc}
ExternC
PfnDliHook   __pfnDliFailureHook2;
```

**DelayLoadInfo** 结构包含正确报告错误所需的所有相关数据，其中包括中的值 `GetLastError` 。

如果通知是 **dliFailLoadLib** 的，则挂钩函数可以返回：

- 如果无法处理失败，则为0。

- 如果故障挂接修复了问题并加载了库本身，则为 HMODULE。

如果通知是 **dliFailGetProc** 的，则挂钩函数可以返回：

- 如果无法处理失败，则为0。

- 有效的过程地址 (导入函数地址) （如果失败挂钩已成功获取地址本身）。

## <a name="see-also"></a>请参阅

[错误处理和通知](error-handling-and-notification.md)
