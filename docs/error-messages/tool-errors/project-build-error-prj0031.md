---
description: 了解详细信息：项目生成错误 PRJ0031
title: 项目生成错误 PRJ0031
ms.date: 11/04/2016
f1_keywords:
- PRJ0031
helpviewer_keywords:
- PRJ0031
ms.assetid: b42435c6-e570-4f8e-9ad5-12a7ea69ccb2
ms.openlocfilehash: 9b7d9a030cd590a750a5ad2da0329a4bf48960a3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97241152"
---
# <a name="project-build-error-prj0031"></a>项目生成错误 PRJ0031

文件 "file" 的自定义生成步骤的 "输出" 属性包含 "宏"，其计算结果为 "macro_expansion"。

文件上的自定义生成步骤出现错误的输出可能是由于宏计算问题所致。 此错误还可能意味着路径格式不正确，包含文件路径中非法字符或字符的组合。

若要解决此错误，请修复宏或修复路径规范。 计算的路径是项目目录中的绝对路径。
