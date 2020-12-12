---
description: 详细了解：宏定义中的优先级
title: 宏定义中的优先级
ms.date: 11/04/2016
helpviewer_keywords:
- NMAKE program, precedence in macro definitions
- macros, precedence
ms.assetid: 0c13182d-83cb-4cbd-af2d-f4c916b62aeb
ms.openlocfilehash: 1738c4ba77f330103395278a6daae169b04fae4c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97225890"
---
# <a name="precedence-in-macro-definitions"></a>宏定义中的优先级

如果宏具有多个定义，NMAKE 使用最高优先级的定义。 以下列表显示了优先级从高到低的顺序：

1. 在命令行上定义的宏

1. 生成文件或包含文件中定义的宏

1. 继承的环境变量宏

1. Tools.ini 文件中定义的宏

1. 预定义宏，如 [CC](command-macros-and-options-macros.md) 和 [as](command-macros-and-options-macros.md)

使用/E 使从环境变量继承的宏替代同名的生成文件宏。 使用 **！UNDEF** 重写命令行。

## <a name="see-also"></a>请参阅

[定义 NMAKE 宏](defining-an-nmake-macro.md)
