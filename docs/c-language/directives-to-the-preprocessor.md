---
description: 详细了解：对预处理器的指令
title: 对预处理器的指令
ms.date: 11/04/2016
ms.assetid: adc6251e-cf6b-4508-bdbb-55f446c838d3
ms.openlocfilehash: 50691647436f492b329b6af43a626e933453d3a3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97213951"
---
# <a name="directives-to-the-preprocessor"></a>对预处理器的指令

“指令”指示 C 预处理器在编译之前先对程序的文本执行特定操作。 《预处理器参考》  中完整描述了[预处理器指令](../preprocessor/preprocessor-directives.md)。 本示例使用预处理器指令 `#define`：

```
#define MAX 100
```

该语句告知编译器在编译前将 `MAX` 的每个匹配项替换为 `100`。 C 编译器预处理器指令为：

|#define|#endif|#ifdef|#line|
|--------------|-------------|-------------|------------|
|`#elif`|`#error`|#ifndef |**#pragma**|
|`#else`|`#if`|`#include`|`#undef`|

## <a name="see-also"></a>请参阅

[源文件和源程序](../c-language/source-files-and-source-programs.md)
