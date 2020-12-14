---
description: 了解详细信息：严重错误 C1382
title: 错误 C1382
ms.date: 11/04/2016
f1_keywords:
- C1382
helpviewer_keywords:
- C1382
ms.assetid: 7a100f8c-3179-4927-a2f1-98de4c753850
ms.openlocfilehash: fd2b9f48030d558a880a787114848dd0551b68ad
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97276512"
---
# <a name="fatal-error-c1382"></a>错误 C1382

“obj”生成后，已重新生成 PCH 文件“file”。 请重新生成此对象

当使用 [/ltcg](../../build/reference/ltcg-link-time-code-generation.md)时，编译器检测到一个 .pch 文件，该文件比指向它的 CIL .obj 新。 CIL 文件中的信息已过时。 重新生成对象。

如果用 **/yc** 编译，还会将多个源代码文件传递到编译器，则也会发生 C1382。  若要解决此问题，请不要在将多个源代码文件传递给编译器时使用 **/yc** 。  有关详细信息，请参阅 [/yc (创建预编译头文件) ](../../build/reference/yc-create-precompiled-header-file.md)。
