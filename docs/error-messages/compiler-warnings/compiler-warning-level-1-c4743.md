---
description: 了解详细信息：编译器警告 (等级 1) C4743
title: 编译器警告（等级 1）C4743
ms.date: 05/13/2019
f1_keywords:
- C4743
helpviewer_keywords:
- C4743
ms.assetid: 2ee76ea3-77f3-4c2f-9a57-0751823c89fd
ms.openlocfilehash: a8c8bcd4ef0e4d7084da34e033be4194da11727f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97228477"
---
# <a name="compiler-warning-level-1-c4743"></a>编译器警告（等级 1）C4743

"*type*" 在 "*file1*" 和 "*file2*" 中具有不同的大小： *数字* 和 *数字* 字节

在两个文件中引用或定义的外部变量在这些文件中具有不同的类型，并且编译器确定 *file1* 中变量的大小与 *file2* 中变量的大小不同。

## <a name="remarks"></a>备注

对于 c + +，可以发出此警告。 如果在两个不同的文件中声明相同的类型（如果这些声明包含虚函数），并且如果声明不相同，则编译器可能会为虚函数表发出警告 C4744。 之所以出现此警告是因为同一类型有两个不同大小的虚拟函数表，并且链接器必须选择其中一个以合并到可执行文件中。  可能会导致程序调用错误的虚拟函数。

若要解决此警告，请使用相同的类型定义或对类型或变量使用不同的名称。

## <a name="example"></a>示例

下面的示例生成 C4743。 若要对其进行编译，请将这两个文件放在同一个文件夹中，然后运行  

```cmd
cl /EHsc /W1 /GL /O2 C4743a.cpp C4743b.cpp
```

```cpp
// C4743a.cpp
class C {
public:
    virtual void f1(void);
    virtual void f2(void);
    virtual void f3(void);
};

void C::f1(void) {}
void C::f2(void) {}
void C::f3(void) {}
C q;
```

```cpp
// C4743b.cpp
class C {
public:
    virtual void f1(void);
    virtual void f2(void);
    virtual void f3(void);
    virtual void f4(void);
    virtual void f5(void);
};

void C::f4(void) {}
void C::f5(void) {}
C x;

int main() {}
```
