---
description: 了解详细信息：/APPCONTAINER
title: /APPCONTAINER
ms.date: 11/04/2016
f1_keywords:
- /APPCONTAINER
helpviewer_keywords:
- APPCONTAINER editbin option
- -APPCONTAINER editbin option
- /APPCONTAINER editbin option
ms.assetid: 0ca4f1ec-c8de-4a37-b3e2-deda7af0bb88
ms.openlocfilehash: f9ea7ff8cac45e45626f15745f77d2230afc1d4b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97187164"
---
# <a name="appcontainer"></a>/APPCONTAINER

标记必须在应用容器中运行的可执行文件，例如 Microsoft Store 或通用 Windows 应用。

```

/APPCONTAINER[:NO]
```

## <a name="remarks"></a>备注

设置了 **/APPCONTAINER** 选项的可执行文件只能在应用容器中运行，应用容器是 Windows 8 中引入的进程隔离环境。 对于 Microsoft Store 和通用 Windows 应用，必须设置此选项。

## <a name="see-also"></a>请参阅

[EDITBIN 选项](editbin-options.md)<br/>
[什么是通用 Windows 应用？](/windows/uwp/get-started/universal-application-platform-guide)
