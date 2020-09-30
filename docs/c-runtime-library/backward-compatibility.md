---
title: Backward Compatibility
description: 如何使用 Microsoft OLDNAMES.LIB。用于映射函数名称以实现向后兼容的 LIB 库。
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- CRT, compatibility
- backward compatibility, C run-time libraries
- compatibility, C run-time libraries
- backward compatibility
ms.assetid: cc3175cf-97fd-492f-b329-5791aea63090
ms.openlocfilehash: b09104a5cff4d8e4cc31f9cc4707e808988401d6
ms.sourcegitcommit: 9451db8480992017c46f9d2df23fb17b503bbe74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/30/2020
ms.locfileid: "91590285"
---
# <a name="backward-compatibility"></a>Backward Compatibility

对于产品版本间的兼容性，库 OLDNAMES.LIB 将旧名称映射到新名称。 例如，`open` 将映射到 `_open`。 仅在使用以下命令行选项的组合进行编译时必须显式链接 OLDNAMES.LIB：

- `/Zl`（从对象文件中忽略默认库名称）和 `/Ze`（默认值 - 使用 Microsoft 扩展）

- `/link`（链接器控件）、`/NOD`（无默认库搜索）和 `/Ze`

有关编译器命令行选项的详细信息，请参阅[编译器参考](../build/reference/compiler-options.md)。

## <a name="see-also"></a>另请参阅

[兼容性](../c-runtime-library/compatibility.md)
