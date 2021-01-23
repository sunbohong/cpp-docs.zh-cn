---
description: 详细了解 pragma Microsoft c/c + + 中的 detect_mismatch 指令
title: detect_mismatch pragma
ms.date: 01/22/2021
f1_keywords:
- vc-pragma.detect_mismatch
- detect_mismatch_CPP
helpviewer_keywords:
- pragma, detect_mismatch
- detect_mismatch pragma
no-loc:
- pragma
ms.openlocfilehash: 33bc899eaaed73329e24e7f210fa91adc8addaa9
ms.sourcegitcommit: a26a66a3cf479e0e827d549a9b850fad99b108d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2021
ms.locfileid: "98713670"
---
# <a name="detect_mismatch-no-locpragma"></a>`detect_mismatch` pragma

将记录放在一个对象中。 链接器将检查这些记录中的潜在不匹配项。

## <a name="syntax"></a>语法

> **`#pragma detect_mismatch(`** "*name*" **`,`** "*value*" **`)`**

## <a name="remarks"></a>注解

链接项目时，如果项目包含两个具有相同 *名称* 的对象，但每个对象具有不同的 *值*，则链接器将引发 [LNK2038](../error-messages/tool-errors/linker-tools-error-lnk2038.md)错误。 用于 pragma 阻止链接对象文件不一致。

*名称* 和 *值* 都是字符串文本，并遵循有关转义字符和串联的字符串文字的规则。 它们是区分大小写的，不能包含逗号、等号、引号或 **null** 字符。

## <a name="example"></a>示例

此示例将创建版本标签相同但版本号不同的两个文件。

```cpp
// pragma_directive_detect_mismatch_a.cpp
#pragma detect_mismatch("myLib_version", "9")
int main ()
{
   return 0;
}

// pragma_directive_detect_mismatch_b.cpp
#pragma detect_mismatch("myLib_version", "1")
```

如果使用命令行编译这两个文件 `cl pragma_directive_detect_mismatch_a.cpp pragma_directive_detect_mismatch_b.cpp` ，则将收到错误 LNK2038。

## <a name="see-also"></a>另请参阅

[杂注指令和 `__pragma` 和 `_Pragma` 关键字](./pragma-directives-and-the-pragma-keyword.md)
