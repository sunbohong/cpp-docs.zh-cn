---
description: 了解更多： OpenMP 库参考
title: OpenMP 库参考
ms.date: 12/02/2019
ms.assetid: a25188c6-edde-43d0-84b5-780e797b08fc
ms.openlocfilehash: fa1f654835afef94b0e00f52bebb0b7300d205be
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97342356"
---
# <a name="openmp-library-reference"></a>OpenMP 库参考

提供 OpenMP API 中使用的构造的链接。

OpenMP 标准的 Visual C++ 实现包括以下构造。

|构造|描述|
|---------------|-----------------|
|[指令](openmp-directives.md)|提供 OpenMP API 中使用的指令的链接。|
|[子句](openmp-clauses.md)|提供 OpenMP API 中使用的子句的链接。|
|[函数](openmp-functions.md)|提供 OpenMP API 中使用的函数的链接。|
|[环境变量](openmp-environment-variables.md)|提供 OpenMP API 中使用的环境变量的链接。|

Visual C++ OpenMP 运行时库函数包含在以下库中。

|OpenMP 运行时库|特征|
|------------------------------|---------------------|
|VCOMP.LIB|多线程、动态链接 (VCOMP140.DLL) 的导入库。|
|VCOMPD.LIB|多线程、动态链接 (VCOMP140D.DLL 的导入库)  (调试) |

如果 _DEBUG 是在编译中定义的，并且 `#include <omp.h>` 是在源代码中，则为 VCOMPD。LIB 将是默认的 lib，否则为 VCOMP。将使用 LIB。

可以使用 [/NODEFAULTLIB (忽略库) ](../../../build/reference/nodefaultlib-ignore-libraries.md) 删除默认的 lib，并使用所选的 lib 显式链接。

OpenMP Dll 位于 Visual C++ 可再发行目录中，需要与使用 OpenMP 的应用程序一起分发。

## <a name="see-also"></a>请参阅

[OpenMP](../../../parallel/openmp/openmp-in-visual-cpp.md)
