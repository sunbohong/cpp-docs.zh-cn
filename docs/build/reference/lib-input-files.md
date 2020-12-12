---
description: 了解有关以下内容的详细信息： LIB 输入文件
title: LIB 输入文件
ms.date: 11/04/2016
helpviewer_keywords:
- input files, LIB
ms.assetid: e1236f0d-cd90-446b-b900-f311f456085c
ms.openlocfilehash: f40cba91f0772e0073daca20a8f2093f3eec8aec
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97199540"
---
# <a name="lib-input-files"></a>LIB 输入文件

LIB 所需的输入文件取决于其使用的模式，如下表所示。

|“模式”|输入|
|----------|-----------|
|默认 (生成或修改库) |COFF 对象 ( .obj) 文件，COFF 库 ( .lib) ，32位对象模型格式 (OMF) 对象 ( 文件|
|使用/EXTRACT 提取成员|COFF 库 ( .lib) |
|使用/DEF 生成导出文件和导入库|模块定义 ( .def) file，COFF object ( .obj) 文件，COFF 库 (，32位 OMF 对象) 文件 (|

> [!NOTE]
> 不能将由16位版本的 LIB 创建的 OMF 库用作32位版本的 LIB 的输入。

## <a name="see-also"></a>请参阅

[LIB 概述](overview-of-lib.md)
