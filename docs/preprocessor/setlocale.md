---
description: 详细了解 pragma Microsoft c/c + + 中的 setlocale 指令
title: setlocale pragma
ms.date: 01/22/2021
f1_keywords:
- setlocale_CPP
- vc-pragma.setlocale
helpviewer_keywords:
- pragma, setlocale
- setlocale pragma
no-loc:
- pragma
ms.openlocfilehash: 936aa1c2eb26798438b48e61ec28007a12080f28
ms.sourcegitcommit: a26a66a3cf479e0e827d549a9b850fad99b108d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2021
ms.locfileid: "98713202"
---
# <a name="setlocale-no-locpragma"></a>`setlocale` pragma

定义在转换宽字符常量和字符串文本时要使用的 *区域设置*、国家/地区和语言。

## <a name="syntax"></a>语法

> **`#pragma setlocale( "`** [ *locale 字符串* ] **`" )`**

## <a name="remarks"></a>注解

由于将多字节字符转换为宽字符的算法可能会因区域设置而异，或编译可能发生在不同的区域设置中，可执行文件将在此区域设置中运行，这 pragma 提供了在编译时指定目标区域设置的方法。 它可确保以正确的格式存储宽字符字符串。

默认 *区域设置字符串* 为由指定的空字符串 `#pragma setlocale( "" )` 。

**`"C"`** 区域设置将字符串中的每个字符映射为其值 **`wchar_t`** 。 的其他有效值 `setlocale` 是在 [语言字符串](../c-runtime-library/language-strings.md) 列表中找到的条目。 例如，可以指定：

```cpp
#pragma setlocale("dutch")
```

指定语言字符串的能力取决于计算机上的代码页和语言 ID 支持。

## <a name="see-also"></a>另请参阅

[杂注指令和 `__pragma` 和 `_Pragma` 关键字](./pragma-directives-and-the-pragma-keyword.md)
