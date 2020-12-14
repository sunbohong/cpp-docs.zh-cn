---
description: 了解详细信息：项目生成错误 PRJ0033
title: 项目生成错误 PRJ0033
ms.date: 11/04/2016
f1_keywords:
- PRJ0033
helpviewer_keywords:
- PRJ0033
ms.assetid: 84d4a052-0586-4b78-9315-81c1e8386c1e
ms.openlocfilehash: 7faf69cd9aaed6f90d9c546c4fc2383fd6808419
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97241126"
---
# <a name="project-build-error-prj0033"></a>项目生成错误 PRJ0033

文件 "file" 的自定义生成步骤的 "附加依赖项" 属性包含 "宏"，其计算结果为 "macro_expansion"。

文件上的自定义生成步骤在其附加依赖项中包含错误可能是由宏计算问题引起的。 此错误还可能意味着路径格式不正确，包含文件路径中非法字符或字符的组合。

若要解决此错误，请修复宏或修复路径规范。 计算的路径是项目目录中的绝对路径。
