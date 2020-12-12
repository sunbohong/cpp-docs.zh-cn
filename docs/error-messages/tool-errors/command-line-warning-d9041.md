---
description: 了解详细信息： Command-Line 警告 D9041
title: 命令行警告 D9041
ms.date: 11/04/2016
f1_keywords:
- D9041
helpviewer_keywords:
- D9041
ms.assetid: ada8815f-4246-4e25-b57d-a7f16fa107cc
ms.openlocfilehash: d6226d4e5dd89176c0ed3722a9fd24e1244cacac
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97119757"
---
# <a name="command-line-warning-d9041"></a>命令行警告 D9041

> "/*选项-name*" 的值 "*option-value*" 无效;假设 "*假定值*";指定此警告时将 "/analyze" 添加到命令行选项

代码分析警告编号已添加到 **`/wd`** 、 **`/we`** 、 **`/wo`** 或 **`/wl`** 命令行选项，并且未指定 **`/analyze`** 命令行选项。 若要更正此错误，请添加 **`/analyze`** 命令行选项，或从相应的命令行选项中删除无效的警告编号 **`/w`** 。

## <a name="example"></a>示例

以下命令行示例生成警告 D9041：

```cmd
cl /EHsc /LD /wd6001 filename.cpp
```

若要修复此警告，请添加 **`/analyze`** 命令行选项。 如果 **`/analyze`** 编译器的版本不支持，请从选项中删除无效的警告编号 **`/wd`** 。

## <a name="see-also"></a>请参阅

[命令行错误 D8000 到 D9999](../../error-messages/tool-errors/command-line-errors-d8000-through-d9999.md)<br/>
[MSVC 编译器选项](../../build/reference/compiler-options.md)
