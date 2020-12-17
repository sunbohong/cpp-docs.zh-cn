---
description: 详细了解：位域的存储
title: 位域的存储
ms.date: 11/04/2016
ms.assetid: 4816a241-1580-4d1c-82ed-13d359733959
ms.openlocfilehash: 43066fe648bc380a8278168f336ebcf10cbbbdf5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97205299"
---
# <a name="storage-of-bit-fields"></a>位域的存储

**ANSI 3.5.2.1** int 内的位域的分配顺序

在整数中按照从最高有效位到最低有效位的顺序来分配位域。 在以下代码中

```
struct mybitfields
{
   unsigned a : 4;
   unsigned b : 5;
   unsigned c : 7;
} test;

int main( void )
{
   test.a = 2;
   test.b = 31;
   test.c = 0;
}
```

这些位将按如下所示排列：

```
00000001 11110010
cccccccb bbbbaaaa
```

由于 80x86 处理器将整数值的低字节存储在高字节之前，因此上面的整数 0x01F2 将按 0xF2 后跟 0x01 的形式存储在物理内存中。

## <a name="see-also"></a>请参阅

[结构、联合、枚举和位域](../c-language/structures-unions-enumerations-and-bit-fields.md)
