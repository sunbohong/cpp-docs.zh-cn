---
description: 了解详细信息：项目生成错误 PRJ0032
title: 项目生成错误 PRJ0032
ms.date: 11/04/2016
f1_keywords:
- PRJ0032
helpviewer_keywords:
- PRJ0032
ms.assetid: bc6acbea-4041-4237-8b5a-f0434705d89f
ms.openlocfilehash: 25c8f9480e63a8afee23c880912e17632111a4c2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97241139"
---
# <a name="project-build-error-prj0032"></a>项目生成错误 PRJ0032

项目级自定义生成步骤的 "输出" 属性包含计算结果为 "macro_expansion" 的 "宏"。

项目上的自定义生成步骤出现错误的输出可能是由于宏计算问题所致。 此错误还可能意味着路径格式不正确，包含文件路径中非法字符或字符的组合。

若要解决此错误，请修复宏或修复路径规范。 计算的路径是项目目录中的绝对路径。
