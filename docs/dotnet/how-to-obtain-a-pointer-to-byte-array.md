---
description: 了解详细信息：如何：获取指向字节数组的指针
title: 如何：获取字节数组的指针
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- pointers, to Byte array
- Byte arrays
ms.assetid: aea18073-3341-47f4-9f0e-04e03327037e
ms.openlocfilehash: d76aa9040be5b908edac3a87ae6f0698f6d6a5dc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97286379"
---
# <a name="how-to-obtain-a-pointer-to-byte-array"></a>如何：获取字节数组的指针

<xref:System.Byte>通过获取第一个元素的地址并将其分配给指针，可以获取指向数组中的数组块的指针。

## <a name="example"></a>示例

```cpp
// pointer_to_Byte_array.cpp
// compile with: /clr
using namespace System;
int main() {
   Byte bArr[] = {1, 2, 3};
   Byte* pbArr = &bArr[0];

   array<Byte> ^ bArr2 = gcnew array<Byte>{1,2,3};
   interior_ptr<Byte> pbArr2 = &bArr2[0];
}
```

## <a name="see-also"></a>请参阅

[使用 c + + 互操作 (隐式 PInvoke) ](../dotnet/using-cpp-interop-implicit-pinvoke.md)
