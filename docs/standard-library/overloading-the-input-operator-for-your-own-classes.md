---
description: 了解详细信息：重载 &gt; &gt; 你自己的类的运算符
title: 为自己的类重载 &gt;&gt; 运算符
ms.date: 11/04/2016
helpviewer_keywords:
- operator>>
- operator>>, overloading for your own classes
- operator >>, overloading for your own classes
ms.assetid: 40dab4e0-3f97-4745-9cc8-b86e740fa246
ms.openlocfilehash: 4de7c16dd1c42f85f169da50f11a514eb245b47c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340848"
---
# <a name="overloading-the-gtgt-operator-for-your-own-classes"></a>为自己的类重载 &gt;&gt; 运算符

输出流使用标准类型的提取 (`>>`) 运算符。 你可以为自己的类型编写相似的提取运算符；成功与否取决于对空格的精确使用。

下面是前文中列举的 `Date` 类的一个提取运算符示例：

```cpp
istream& operator>> (istream& is, Date& dt)
{
    is>> dt.mo>> dt.da>> dt.yr;
    return is;
}
```

## <a name="see-also"></a>请参阅

[输入流](../standard-library/input-streams.md)
