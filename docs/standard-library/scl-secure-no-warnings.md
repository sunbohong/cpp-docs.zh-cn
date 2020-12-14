---
description: 了解详细信息： _SCL_SECURE_NO_WARNINGS
title: _SCL_SECURE_NO_WARNINGS
ms.date: 11/04/2016
f1_keywords:
- _SCL_SECURE_NO_DEPRECATE
- _SCL_SECURE_NO_WARNINGS
helpviewer_keywords:
- _SCL_SECURE_NO_DEPRECATE
- _SCL_SECURE_NO_WARNINGS
ms.assetid: ef0ddea9-7c62-4b53-8b64-5f4fd369776f
ms.openlocfilehash: 383aeed0bdedc4830076248100c8cf0a1acf34b1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97187918"
---
# <a name="_scl_secure_no_warnings"></a>_SCL_SECURE_NO_WARNINGS

如果调用 c + + 标准库中任何可能不安全的方法，将导致 [编译器警告 (级别 3) C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md)。 若要禁用此警告，可在代码中将宏定义为 _SCL_SECURE_NO_WARNINGS：

```cpp
#define _SCL_SECURE_NO_WARNINGS
```

如果使用预编译头，请将此指令置于预编译头文件中，然后再添加任何 C 运行库或标准库标头。 如果将其放在单独的源代码文件中，然后再包含预编译头文件，编译器将忽略该文件。

## <a name="remarks"></a>备注

禁用 C4996 警告的其他方式包括：

- 使用 [/D（预处理器定义）](../build/reference/d-preprocessor-definitions.md)编译器选项：

   > cl/D_SCL_SECURE_NO_WARNINGS [其他编译器选项] myfile.txt .cpp

- 使用 [/w](../build/reference/compiler-option-warning-level.md) 编译器选项：

   > cl/wd4996 [其他编译器选项] myfile.txt

- 使用 [#pragma warning](../preprocessor/warning.md) 指令：

   ```cpp
   #pragma warning(disable:4996)
   ```

此外，还可以手动更改 C4996 和 **/w \<l> \<n>** 编译器选项的警告级别。 例如，可将警告 C4996 设置为级别 4：

> cl/w44996 [其他编译器选项] myfile.txt

有关详细信息，请参阅 [/w, /W0, /W1, /W2, /W3, /W4, /w1, /w2, /w3, /w4, /Wall, /wd, /we, /wo, /Wv, /WX（警告级别）](../build/reference/compiler-option-warning-level.md)。

## <a name="see-also"></a>请参阅

[安全库： c + + 标准库](../standard-library/safe-libraries-cpp-standard-library.md)
