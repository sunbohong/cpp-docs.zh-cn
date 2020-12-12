---
description: 了解详细信息：链接器工具错误 LNK1301
title: 链接器工具错误 LNK1301
ms.date: 11/04/2016
f1_keywords:
- LNK1301
helpviewer_keywords:
- LNK1301
ms.assetid: 760da428-7182-4b25-b20a-de90d4b9a9cd
ms.openlocfilehash: ac282aea62836591c6e30abb3030ef2143a78003
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97335951"
---
# <a name="linker-tools-error-lnk1301"></a>链接器工具错误 LNK1301

找到 LTCG clr 模块，与/LTCG： parameter 不兼容

使用/clr 和/GL 编译的模块已传递给链接器，并连同一个按配置优化 (PGO) 参数/LTCG。

对于/clr 模块，不支持按配置优化。

有关详细信息，请参阅：

- [/GL (完全程序优化) ](../../build/reference/gl-whole-program-optimization.md)

- [/LTCG () 的链接时间代码生成 ](../../build/reference/ltcg-link-time-code-generation.md)

- [/cgthreads（公共语言运行时编译）](../../build/reference/clr-common-language-runtime-compilation.md)

- [按配置优化](../../build/profile-guided-optimizations.md)

### <a name="to-correct-this-error"></a>更正此错误

1. 不要用/clr 编译，或不要链接到/LTCG. 中的某个 PGO 参数

## <a name="example"></a>示例

下面的示例生成 LNK1301：

```cpp
// LNK1301.cpp
// compile with: /clr /GL /link /LTCG:PGI LNK1301.obj
// LNK1301 expected
class MyClass {
public:
   int i;
};
```
