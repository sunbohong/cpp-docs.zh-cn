---
description: 了解详细信息：生成文件中的长文件名
title: 生成文件中的长文件名
ms.date: 11/04/2016
helpviewer_keywords:
- NMAKE program, long filenames
- long filenames
ms.assetid: 626d56fc-8879-46ba-9c2d-dd386c78cccc
ms.openlocfilehash: 4a432fbdfb9ee66d46451082067f9fea161b9444
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97199111"
---
# <a name="long-filenames-in-a-makefile"></a>生成文件中的长文件名

用双引号将长文件名括起来，如下所示：

```
all : "VeryLongFileName.exe"
```

## <a name="see-also"></a>请参阅

[生成文件的内容](contents-of-a-makefile.md)
