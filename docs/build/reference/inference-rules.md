---
description: 了解更多：推理规则
title: 推理规则
ms.date: 11/04/2016
helpviewer_keywords:
- inference rules in NMAKE
- rules, inference
- NMAKE program, inference rules
ms.assetid: caff320f-fb07-4eea-80c3-a6a2133a8492
ms.openlocfilehash: fc063f71ff88442ce6f7fc02c5b22f015ce0010c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97199748"
---
# <a name="inference-rules"></a>推理规则

推理规则提供用于更新目标和推导目标的依赖项的命令。 推理规则中的扩展与具有相同基名称的单个目标和依赖项匹配。 推理规则是用户定义的或预定义的规则;可以重新定义预定义的规则。

如果过期依赖项没有命令，则为; 如果为，则为 [。后缀](dot-directives.md) 包含依赖项的扩展，NMAKE 使用其扩展与目标和当前或指定目录中的现有文件匹配的规则。 如果有多个规则与现有文件匹配，则 **。后缀** 列表确定使用的是;列表优先级从左到右递减。 如果某个依赖文件不存在并且未在另一个描述块中作为目标列出，则推理规则可以从具有相同基名称的另一个文件创建缺少的依赖项。 如果说明块的目标没有依赖项或命令，推理规则可以更新目标。 即使不存在描述块，推理规则仍可以生成命令行目标。 即使指定了显式依赖项，NMAKE 也可以调用推断依赖项的规则。

## <a name="what-do-you-want-to-know-more-about"></a>你想进一步了解什么？

[定义规则](defining-a-rule.md)

[批模式规则](batch-mode-rules.md)

[预定义的规则](predefined-rules.md)

[推导出的依赖项和规则](inferred-dependents-and-rules.md)

[推理规则中的优先级](precedence-in-inference-rules.md)

## <a name="see-also"></a>请参阅

[NMAKE 参考](nmake-reference.md)
