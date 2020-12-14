---
description: 了解详细信息：链接器工具错误 LNK1179
title: 链接器工具错误 LNK1179
ms.date: 11/04/2016
f1_keywords:
- LNK1179
helpviewer_keywords:
- LNK1179
ms.assetid: 4b1536d7-0d3d-4f29-a9c1-6fa5cf6cb665
ms.openlocfilehash: 691476eeffadece2436518c5249ca523adca51c2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97253437"
---
# <a name="linker-tools-error-lnk1179"></a>链接器工具错误 LNK1179

无效或损坏的文件：重复的 COMDAT "filename"

对象模块包含具有相同名称的两个或多个 Comdat。

此错误的原因可能是使用 [/h](../../build/reference/h-restrict-length-of-external-names.md)（限制外部名称的长度）和 [/gy](../../build/reference/gy-enable-function-level-linking.md)（包函数在 comdat 中）。

## <a name="example"></a>示例

在下面的代码中， `function1` 和 `function2` 的前八个字符相同。 使用 **/gy** 和 **/H8** 进行编译会生成链接错误。

```cpp
void function1(void);
void function2(void);

int main() {
    function1();
    function2();
}

void function1(void) {}
void function2(void) {}
```
