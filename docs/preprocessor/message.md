---
description: pragma在 Microsoft c/c + + 中了解消息指令的详细信息
title: 消息 pragma
ms.date: 01/22/2021
f1_keywords:
- message_CPP
- vc-pragma.message
helpviewer_keywords:
- message pragma
- pragma, message
no-loc:
- pragma
ms.openlocfilehash: 6f5e39896e0ba644f9d40665e80cbf7de9026223
ms.sourcegitcommit: a26a66a3cf479e0e827d549a9b850fad99b108d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2021
ms.locfileid: "98713488"
---
# <a name="message-no-locpragma"></a>`message` pragma

在未结束编译的情况下将字符串发送到标准输出。

## <a name="syntax"></a>语法

> **`#pragma message(`***消息-字符串***`)`**

## <a name="remarks"></a>注解

的典型用法 **`message`** pragma 是在编译时显示信息性消息。

*消息字符串* 参数可以是扩展到字符串文字的宏，你可以使用任意组合将此类宏与字符串文字连接起来。

如果在中使用预定义的宏 **`message`** pragma ，宏应返回一个字符串。 否则，你必须将宏的输出转换为字符串。

下面的代码片段使用在 **`message`** pragma 编译过程中显示消息：

```cpp
// pragma_directives_message1.cpp
// compile with: /LD
#if _M_IX86 >= 500
#pragma message("_M_IX86 >= 500")
#endif

#pragma message("")

#pragma message( "Compiling " __FILE__ )
#pragma message( "Last modified on " __TIMESTAMP__ )

#pragma message("")

// with line number
#define STRING2(x) #x
#define STRING(x) STRING2(x)

#pragma message (__FILE__ "[" STRING(__LINE__) "]: test")

#pragma message("")
```

## <a name="see-also"></a>另请参阅

[杂注指令和 `__pragma` 和 `_Pragma` 关键字](./pragma-directives-and-the-pragma-keyword.md)
