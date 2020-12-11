---
description: 了解详细信息：项目生成错误 PRJ0030
title: 项目生成错误 PRJ0030
ms.date: 11/04/2016
f1_keywords:
- PRJ0030
helpviewer_keywords:
- PRJ0030
ms.assetid: c48b3727-e166-46e7-bcd7-3e5b2ac5c1d4
ms.openlocfilehash: a8fdb99e7444383f3634730b3053b00b81661aed
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97160280"
---
# <a name="project-build-error-prj0030"></a>项目生成错误 PRJ0030

宏扩展错误。 对于 $ (宏) ，计算超过32级别的递归。

此错误是由宏中的递归导致的。 例如，如果您设置了 **中间目录** 属性 (请参阅 [ (Project)](../../build/reference/general-property-page-project.md)) 到 $ (IntDir) 的 "常规属性" 页，您将获得递归。

若要解决此错误，请不要使用宏或属性来定义它们。
