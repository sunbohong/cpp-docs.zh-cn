---
description: 了解详细信息：register 存储类说明符
title: register 存储类说明符
ms.date: 11/04/2016
helpviewer_keywords:
- register variables
- register storage class
ms.assetid: 7577bf48-88ec-4191-873c-ef4217a4034e
ms.openlocfilehash: a7e062f72191f6ee6d678d18b902ea184d362714
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97120752"
---
# <a name="register-storage-class-specifier"></a>register 存储类说明符

**Microsoft 专用**

Microsoft C/C++ 编译器不会按照用户请求来使用寄存器变量。 不过，为了确保可移植性，编译器将遵循与 `register` 关键字关联的其他所有语义。 例如，无法对寄存器对象应用一元取址运算符 (&)，也无法对数组使用 `register` 关键字。

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[内部级别声明的存储类说明符](../c-language/storage-class-specifiers-for-internal-level-declarations.md)
