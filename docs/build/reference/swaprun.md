---
description: 了解详细信息：/SWAPRUN
title: /SWAPRUN
ms.date: 11/04/2016
f1_keywords:
- /swaprun_editbin
helpviewer_keywords:
- /SWAPRUN editbin option
- -SWAPRUN editbin option
- SWAPRUN editbin option
ms.assetid: 6eefd7f3-ca47-48e3-8509-323d27cf4ae7
ms.openlocfilehash: 68d53a8d5fa7337fb29f624e26b71790f78d29dd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97230167"
---
# <a name="swaprun"></a>/SWAPRUN

```
/SWAPRUN:{[!]NET|[!]CD}
```

## <a name="remarks"></a>备注

此选项可编辑图像，告知操作系统将映像复制到交换文件，然后从该文件运行。 对于位于网络或可移动媒体上的映像，请使用此选项。

可以添加或删除 NET 或 CD 限定符：

- NET 指示映像驻留在网络上。

- CD 指示映像驻留在 cd-rom 或类似可移动介质上。

- 使用！ NET 和！CD 来反转网络和 CD 的效果。

## <a name="see-also"></a>请参阅

[EDITBIN 选项](editbin-options.md)
