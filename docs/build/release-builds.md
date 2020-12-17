---
description: 详细了解：发行版本
title: C++ 发布版本 - Visual Studio
ms.date: 12/10/2018
helpviewer_keywords:
- debugging [C++], release builds
- release builds
- debug builds, converting to release build
ms.assetid: fa9a78fa-f4b5-4722-baf4-aec655c4ff0f
ms.openlocfilehash: 7168fd50421835edc82d0599b22deb9214e28869
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97273782"
---
# <a name="release-builds"></a>发行版本

发布版本使用优化。 使用优化创建发布版本时，编译器将不会生成符号调试信息。 由于缺少符号调试信息并且未为 TRACE 和 ASSERT 调用生成代码，这意味着可执行文件的大小会减小，因此速度会更快。

## <a name="in-this-section"></a>本节内容

[创建发行版本时遇到的常见问题](common-problems-when-creating-a-release-build.md)<br/>
[修复发行版本问题](fixing-release-build-problems.md)<br/>
[使用 VERIFY 代替 ASSERT](using-verify-instead-of-assert.md)<br/>
[使用调试版本检查内存改写](using-the-debug-build-to-check-for-memory-overwrite.md)<br/>
[如何：调试发行版本](how-to-debug-a-release-build.md)<br/>
[检查内存改写](checking-for-memory-overwrites.md)<br/>
[优化代码](optimizing-your-code.md)

## <a name="see-also"></a>请参阅

[C/C++ 生成参考](reference/c-cpp-building-reference.md)
