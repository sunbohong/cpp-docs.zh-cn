---
description: '了解详细信息：输出流操控器，其中一个参数 (int 或 long) '
title: 带有一个自变量（int 或 long）的输出流操控器
ms.date: 11/04/2016
helpviewer_keywords:
- output streams, int or long argument manipulators
ms.assetid: 338f3164-b5e2-4c5a-a605-7d9dc3629ca1
ms.openlocfilehash: e04486f7d207731d9fbf7ba8083ffcb02a82ba8a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340887"
---
# <a name="output-stream-manipulators-with-one-argument-int-or-long"></a>带有一个自变量（int 或 long）的输出流操控器

iostream 类库提供用于创建参数化操控器的一组宏。 使用单个 or 参数的操控器 **`int`** **`long`** 是一种特殊情况。 若要创建接受单个 **`int`** 或参数 (如) 的输出流操控器 **`long`** `setw` ，则必须使用在中定义的 _Smanip 宏 \<iomanip> 。 此示例定义了向流中插入指定数量的空格的 `fillblank` 操控器：

## <a name="example"></a>示例

```cpp
// output_stream_manip.cpp
// compile with: /GR /EHsc
#include <iostream>
#include <iomanip>
using namespace std;

void fb( ios_base& os, int l )
{
   ostream *pos = dynamic_cast<ostream*>(&os);
   if (pos)
   {
      for( int i=0; i < l; i++ )
      (*pos) << ' ';
   };
}

_Smanip<int>
   __cdecl fillblank(int no)
   {
   return (_Smanip<int>(&fb, no));
   }

int main( )
{
   cout << "10 blanks follow" << fillblank( 10 ) << ".\n";
}
```

## <a name="see-also"></a>请参阅

[带参数的自定义操控器](../standard-library/custom-manipulators-with-arguments.md)
