---
description: 了解详细信息：推断出的依赖项和规则
title: 推导出的依赖项和规则
ms.date: 11/04/2016
helpviewer_keywords:
- rules, inferred
- inferred dependents in NMAKE
- inferred rules in NMAKE
- dependents, inferred
ms.assetid: 9381e74a-53d9-445c-836d-0ff7ef6112d9
ms.openlocfilehash: 9f4c1d14d18c9c693a7bd71f9207ff36aede8e22
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97191272"
---
# <a name="inferred-dependents-and-rules"></a>推导出的依赖项和规则

如果存在适用的推理规则，NMAKE 假定目标的推理依赖项。 规则适用于：

- *toext* 匹配目标的扩展。

- *fromext* 匹配具有目标基名称并且存在于当前目录或指定目录中的文件的扩展名。

- *fromext* 为 [。后缀](dot-directives.md);匹配规则中的其他 *fromext* 没有更高的 **。后缀** 优先级。

- 没有显式依赖项具有更高的 **。后缀** 优先级。

推理依赖项可能会导致意外的副作用。 如果目标的描述块包含命令，NMAKE 会执行这些命令，而不是规则中的命令。

## <a name="see-also"></a>请参阅

[推理规则](inference-rules.md)
