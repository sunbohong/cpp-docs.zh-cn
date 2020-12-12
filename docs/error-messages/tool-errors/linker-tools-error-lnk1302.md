---
description: 了解详细信息：链接器工具错误 LNK1302
title: 链接器工具错误 LNK1302
ms.date: 11/04/2016
f1_keywords:
- LNK1302
helpviewer_keywords:
- LNK1302
ms.assetid: aea3c753-c2c4-4249-bbc3-f2d4f0164b5e
ms.openlocfilehash: 33e9a406cde7910c7340fdfe256711c47eee45cf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97193690"
---
# <a name="linker-tools-error-lnk1302"></a>链接器工具错误 LNK1302

只支持链接安全的 .netmodule；无法链接文件 .netmodule

使用 **/LN**) 编译的 .netmodule (已传递给链接器，用户尝试调用 MSIL 链接。  C + + 模块对于使用 **/clr： safe** 编译的 MSIL 链接有效。

若要更正此错误，请使用 **/clr： safe** 进行编译，以启用 MSIL 链接，或将 **/clr** 或 **/clr： pure** 文件传递到链接器而不是模块。

有关详细信息，请参阅

- [/LN (创建 MSIL 模块) ](../../build/reference/ln-create-msil-module.md)

- [作为链接器输入的 .netmodule 文件](../../build/reference/netmodule-files-as-linker-input.md)
