---
description: 了解详细信息： BSCMAKE 错误 BK1503
title: BSCMAKE 错误 BK1503
ms.date: 11/04/2016
f1_keywords:
- BK1503
helpviewer_keywords:
- BK1503
ms.assetid: e6582344-b91e-486f-baf3-4f9028d83c3b
ms.openlocfilehash: 0e789aa54241df5245f4c3a02a9307a97d51730c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97322994"
---
# <a name="bscmake-error-bk1503"></a>BSCMAKE 错误 BK1503

无法写入文件 "filename" [： reason]

BSCMAKE 将在编译过程中生成的 .sbr 文件与一个浏览器数据库组合在一起。 如果生成的浏览器数据库超过 64 MB，或输入 ( .sbr) 文件数超过4092，则会发出此错误。

如果此问题是由超过4092个 .sbr 文件引起的，则必须减少输入文件的数量。 在 Visual Studio 中，这可以通过 [/fr](../../build/reference/fr-fr-create-dot-sbr-file.md) 整个项目来实现，然后按文件重新检查文件。

如果此问题是由于 .bsc 文件大于64MB 所致，则将 .sbr 文件的数目减少为输入会减小生成的 .bsc 文件的大小。 此外，还可以通过使用/Em (排除宏展开符号) 、/El (排除本地变量) 和/Es (排除系统文件) 来减少浏览信息量。

## <a name="see-also"></a>请参阅

[BSCMAKE 选项](../../build/reference/bscmake-options.md)
