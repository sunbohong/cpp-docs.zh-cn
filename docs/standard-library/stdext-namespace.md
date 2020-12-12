---
description: 了解详细信息： stdext 命名空间
title: stdext 命名空间
ms.date: 09/06/2017
f1_keywords:
- stdext
helpviewer_keywords:
- _DEFINE_DEPRECATED_HASH_CLASSES symbol
- stdext namespace
ms.assetid: 3e94fc89-0584-424f-bc09-081b73379545
ms.openlocfilehash: bb81dde22014ec91f7212ce4313c21a8410f30a9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97153780"
---
# <a name="stdext-namespace"></a>stdext 命名空间

[\<hash_map>](../standard-library/hash-map.md)和 [\<hash_set>](../standard-library/hash-set.md) 标头文件的成员当前不是 ISO c + + 标准的一部分。 因此，这些类型和成员已从 `std` 命名空间移动到命名空间 `stdext`以保持符合 C++ 标准。

使用 [/ze](../build/reference/za-ze-disable-language-extensions.md)（默认值）进行编译时，编译器会发出警告，指出对 `std` \<hash_map> 和 \<hash_set> 标头文件的成员使用。 若要禁用该警告，请使用 [警告](../preprocessor/warning.md) 杂注。

若要让编译器生成错误以将 `std` \<hash_map> 和 \<hash_set> 标头文件的成员用于 **/ze**，请在 `#include` 任何 c + + 标准库标头文件之前添加以下指令。

```cpp
#define _DEFINE_DEPRECATED_HASH_CLASSES 0
```

使用 **/za** 进行编译时，编译器会生成错误。

## <a name="see-also"></a>请参阅

[C + + 标准库概述](../standard-library/cpp-standard-library-overview.md)
