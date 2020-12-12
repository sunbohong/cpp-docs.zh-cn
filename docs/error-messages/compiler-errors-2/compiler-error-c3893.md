---
description: 了解更多：编译器错误 C3893
title: 编译器错误 C3893
ms.date: 11/04/2016
f1_keywords:
- C3893
helpviewer_keywords:
- C3893
ms.assetid: 90d52eae-6ef2-4db1-b7ad-92f9e8b140fb
ms.openlocfilehash: 975e2e356bc4b98a25a80e8ae4cc152c3b9b3207
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97119913"
---
# <a name="compiler-error-c3893"></a>编译器错误 C3893

"var"： initonly 数据成员的左值只允许在类 "type_name" 的实例构造函数中使用

静态 [initonly](../../dotnet/initonly-cpp-cli.md) 数据成员只能在静态构造函数中采用其地址。

实例 (非静态) initonly 数据成员只能在 (非静态) 构造函数的实例中采用其地址。

下面的示例生成 C3893：

```cpp
// C3893.cpp
// compile with: /clr
ref struct Y1 {
   Y1() : data_var(0) {
      int% i = data_var;   // OK
   }
   initonly int data_var;
};

int main(){
   Y1^ y= gcnew Y1;
   int% i = y->data_var;   // C3893
}
```
