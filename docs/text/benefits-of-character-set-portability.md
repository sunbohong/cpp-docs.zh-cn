---
description: 了解更多相关信息：字符集可移植性的优点
title: 字符集可迁移性的好处
ms.date: 11/04/2016
helpviewer_keywords:
- character sets [C++], benefits
- portability [C++], character sets
ms.assetid: bd60b925-1498-4e4f-897b-4c8ce66edcf7
ms.openlocfilehash: 32d78e6a230d664970e819f766d70beb1df52a88
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97187619"
---
# <a name="benefits-of-character-set-portability"></a>字符集可迁移性的好处

即使您当前不打算国际化您的应用程序，您也可以从使用 MFC 和 C 运行时可移植性功能中获益：

- 编码移植使基本代码变得灵活。 稍后可以轻松地将其移动到 Unicode 或 MBCS。

- 使用 Unicode 使应用程序更有效。 由于 Windows 使用 Unicode，因此必须转换向操作系统传递的非 Unicode 字符串，这会产生开销。

## <a name="see-also"></a>请参阅

[Unicode 和 MBCS](../text/unicode-and-mbcs.md)<br/>
[支持 Unicode](../text/support-for-unicode.md)
