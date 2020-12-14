---
description: 了解详细信息：推理规则中的优先级
title: 推理规则中的优先级
ms.date: 11/04/2016
helpviewer_keywords:
- inference rules in NMAKE
- rules, inference
- precedence, inference rule
ms.assetid: 69e3dc02-0815-4c3a-b02b-1cb85fceaf24
ms.openlocfilehash: b56d01cce63aaaac92e011630e45bcf43e7fe0b3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97225903"
---
# <a name="precedence-in-inference-rules"></a>推理规则中的优先级

如果对推理规则进行了多次定义，NMAKE 将使用最高优先级的定义。 以下列表显示了优先级从高到低的顺序：

1. 生成文件中定义的推理规则;稍后定义优先。

1. 在 Tools.ini 中定义的推理规则;稍后定义优先。

1. 预定义的推理规则。

## <a name="see-also"></a>请参阅

[推理规则](inference-rules.md)
