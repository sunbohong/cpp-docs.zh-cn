---
description: 详细了解：地址存储
title: 地址存储
ms.date: 11/04/2016
helpviewer_keywords:
- storage [C++], addresses
- addresses [C++], storage of
ms.assetid: 423b2402-b847-4788-ad70-943b7c9c5c8b
ms.openlocfilehash: 8f0b51370659d7a23739d75f53492d171c17e422
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97296688"
---
# <a name="storage-of-addresses"></a>地址存储

地址所需的存储量和该地址的含义取决于编译器的实现。 指向不同类型的指针不能保证具有相同的长度。 因此，sizeof(char \*)  不必与 sizeof(int \*)  相等。

**Microsoft 专用**

对于 Microsoft C 编译器，sizeof(char \*)  与 sizeof(int \*)  相等。

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[指针声明](../c-language/pointer-declarations.md)
