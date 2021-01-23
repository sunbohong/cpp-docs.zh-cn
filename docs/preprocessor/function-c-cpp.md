---
description: 详细了解 pragma Microsoft c/c + + 中的函数指令
title: 才能 pragma
ms.date: 01/22/2021
f1_keywords:
- function_CPP
- vc-pragma.function
helpviewer_keywords:
- function pragma
- pragma, function
no-loc:
- pragma
ms.openlocfilehash: 3d4b1e2f50cd118e613235271428588ac585affc
ms.sourcegitcommit: a26a66a3cf479e0e827d549a9b850fad99b108d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2021
ms.locfileid: "98712825"
---
# <a name="function-no-locpragma"></a>`function` pragma

通知编译器生成对的参数列表中指定的函数的调用 pragma ，而不是内联它们。

## <a name="syntax"></a>语法

> **`#pragma function(`***function1* [ **`,`** *function2* ]**`)`**

## <a name="remarks"></a>注解

内部函数通常生成为内联代码，而不是函数调用。 如果使用 [ `intrinsic` pragma](intrinsic.md)或 [`/Oi`](../build/reference/oi-generate-intrinsic-functions.md) 编译器选项告知编译器生成内部函数，则可以使用 **`function`** pragma 显式强制执行函数调用。 一旦 **`function`** pragma 出现，它会在包含指定内部函数的第一个函数定义上生效。 该效果将继续到源文件的末尾，或 `intrinsic` pragma 指定相同内部函数的外观。 在 **`function`** pragma 全局级别，只能在函数之外使用。

有关具有内部形式的函数的列表，请参阅[ `intrinsic` pragma ](intrinsic.md)。

## <a name="example"></a>示例

```cpp
// pragma_directive_function.cpp
#include <ctype.h>
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

// use intrinsic forms of memset and strlen
#pragma intrinsic(memset, strlen)

// Find first word break in string, and set remaining
// chars in string to specified char value.
char *set_str_after_word(char *string, char ch) {
   int i;
   int len = strlen(string);  /* NOTE: uses intrinsic for strlen */

   for(i = 0; i < len; i++) {
      if (isspace(*(string + i)))
         break;
   }

   for(; i < len; i++)
      *(string + i) = ch;

   return string;
}

// do not use strlen intrinsic
#pragma function(strlen)

// Set all chars in string to specified char value.
char *set_str(char *string, char ch) {
   // Uses intrinsic for memset, but calls strlen library function
   return (char *) memset(string, ch, strlen(string));
}

int main() {
   char *str = (char *) malloc(20 * sizeof(char));

   strcpy_s(str, sizeof("Now is the time"), "Now is the time");
   printf("str is '%s'\n", set_str_after_word(str, '*'));
   printf("str is '%s'\n", set_str(str, '!'));
}
```

```Output
str is 'Now************'
str is '!!!!!!!!!!!!!!!'
```

## <a name="see-also"></a>另请参阅

[杂注指令和 `__pragma` 和 `_Pragma` 关键字](./pragma-directives-and-the-pragma-keyword.md)
