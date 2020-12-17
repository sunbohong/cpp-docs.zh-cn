---
description: 详细了解：使用没有 () 的函数名不产生代码
title: 使用没有 () 的函数名不产生代码
ms.date: 11/04/2016
helpviewer_keywords:
- functions [C++], without parentheses
ms.assetid: edf4a177-a160-44aa-8436-e077b5b27809
ms.openlocfilehash: 1fedc296422a759878c26469ccc20955043b3913
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97277253"
---
# <a name="using-function-name-without--produces-no-code"></a>使用没有 () 的函数名不产生代码

在不带括号的情况下使用程序中声明的函数名称时，编译器不会生成代码。 无论函数是否采用参数，都会发生这种情况，因为编译器会计算函数地址；但是，由于函数调用运算符“()”不存在，因此不进行任何调用。 此结果类似于以下内容：

```
// compile with /Wall to generate a warning
int a;
a;      // no code generated here either
```

在 Visual C++ 中，即使使用警告等级 4，也不会生成诊断输出。 不发出警告；不生成任何代码。

下面的示例代码会进行编译（出现警告）并正确链接（没有错误），但是不会在 `funcn( )` 的引用中生成任何代码。 若要使此代码正常工作，请添加函数调用运算符“()”。

```
#include <stdio.h>
void funcn();

int main() {
   funcn;      /* missing function call operator;
                  call will fail.  Use funcn() */
   }

void funcn() {
   printf("\nHello World\n");
}
```

## <a name="see-also"></a>请参阅

[优化代码](optimizing-your-code.md)
