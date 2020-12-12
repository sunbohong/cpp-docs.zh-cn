---
description: 了解详细信息：加载 Delay-Loaded DLL 的所有导入
title: 加载被延迟加载的 DLL 的所有导入
ms.date: 11/04/2016
helpviewer_keywords:
- __HrLoadAllImportsForDll linker option
ms.assetid: 975fcd97-1a56-4a16-9698-e1a249d2d592
ms.openlocfilehash: 0f1334f30568e4722bd97579145ddcae9851b901
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97190909"
---
# <a name="loading-all-imports-for-a-delay-loaded-dll"></a>加载被延迟加载的 DLL 的所有导入

**__HrLoadAllImportsForDll** 函数（在 delayhlp 中定义）通知链接器加载使用 [/delayload](delayload-delay-load-import.md)链接器选项指定的 DLL 中的所有导入。

加载所有导入后，你可以将错误处理放入代码中的一个位置，而不必使用异常处理来处理对导入的实际调用。 它还避免了在帮助程序代码无法加载导入的情况下，应用程序在部分过程中失败的情况。

调用 **__HrLoadAllImportsForDll** 不会更改挂钩和错误处理的行为;有关详细信息，请参阅 [错误处理和通知](error-handling-and-notification.md) 。

传递给 **__HrLoadAllImportsForDll** 的 DLL 名称与 dll 本身中存储的名称进行比较，并区分大小写。

下面的示例演示如何调用 **__HrLoadAllImportsForDll**：

```
if (FAILED(__HrLoadAllImportsForDll("delay1.dll"))) {
   printf ( "failed on snap load, exiting\n" );
   exit(2);
}
```

## <a name="see-also"></a>请参阅

[Delay-Loaded Dll 的链接器支持](linker-support-for-delay-loaded-dlls.md)
