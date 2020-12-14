---
description: 了解有关以下内容的详细信息： LIB 输出文件
title: LIB 输出文件
ms.date: 11/04/2016
helpviewer_keywords:
- output files, LIB
ms.assetid: e73d2f9b-a42d-402b-b7e3-3a94bebb317e
ms.openlocfilehash: 5a9145f4c75db0c402bc4416cedfd6d63bb23cd4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97191064"
---
# <a name="lib-output-files"></a>LIB 输出文件

LIB 生成的输出文件取决于其使用的模式，如下表所示。

|“模式”|输出|
|----------|------------|
|默认 (生成或修改库) |COFF 库 ( .lib) |
|使用/EXTRACT 提取成员|对象 ( .obj) 文件|
|使用/DEF 生成导出文件和导入库|导入库 ( .lib) 并导出 ( .exp) 文件|

## <a name="see-also"></a>请参阅

[LIB 概述](overview-of-lib.md)
