---
description: 了解详细信息： _com_ptr_t 类
title: _com_ptr_t 类
ms.date: 11/04/2016
f1_keywords:
- _com_ptr_t
helpviewer_keywords:
- _com_ptr_t class
ms.assetid: 3753a8a0-03d4-4cfd-8a9a-74872ea53971
ms.openlocfilehash: a68b522806cec14baffe7857c71ac171ed0407f9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97295609"
---
# <a name="_com_ptr_t-class"></a>_com_ptr_t 类

**Microsoft 专用**

**_Com_ptr_t** 对象封装 com 接口指针，并且称为 "智能" 指针。 此模板类通过对成员函数的函数调用来管理资源分配和释放 `IUnknown` ： `QueryInterface` 、 `AddRef` 和 `Release` 。

智能指针通常由 _COM_SMARTPTR_TYPEDEF 宏提供的 typedef 定义引用。 此宏采用接口名称和 IID，并声明使用接口名称加上后缀的 **_com_ptr_t** 的专用化 `Ptr` 。 例如：

```cpp
_COM_SMARTPTR_TYPEDEF(IMyInterface, __uuidof(IMyInterface));
```

声明 **_com_ptr_t** 特殊化 `IMyInterfacePtr` 。

一组 [函数模板](../cpp/relational-function-templates.md)而不是此模板类的成员，它支持与比较运算符右侧的智能指针进行比较。

### <a name="construction"></a>建筑

| 名称 | 描述 |
|-|-|
|[_com_ptr_t](../cpp/com-ptr-t-com-ptr-t.md)|构造一个 **_com_ptr_t** 对象。|

### <a name="low-level-operations"></a>低级别运算

| 名称 | 描述 |
|-|-|
|[AddRef](../cpp/com-ptr-t-addref.md)|`AddRef` `IUnknown` 在封装的接口指针上调用的成员函数。|
|[附加](../cpp/com-ptr-t-attach.md)|封装此智能指针的类型的原始接口指针。|
|[CreateInstance](../cpp/com-ptr-t-createinstance.md)|在给定或的情况创建对象的新 `CLSID` 实例 `ProgID` 。|
|[分离](../cpp/com-ptr-t-detach.md)|提取并返回封装的接口指针。|
|[GetActiveObject](../cpp/com-ptr-t-getactiveobject.md)|附加到给定或的对象的现有实例 `CLSID` `ProgID` 。|
|[GetInterfacePtr](../cpp/com-ptr-t-getinterfaceptr.md)|返回封装的接口指针。|
|[QueryInterface](../cpp/com-ptr-t-queryinterface.md)|`QueryInterface` `IUnknown` 在封装的接口指针上调用的成员函数。|
|[版本](../cpp/com-ptr-t-release.md)|`Release` `IUnknown` 在封装的接口指针上调用的成员函数。|

### <a name="operators"></a>运算符

| 名称 | 描述 |
|-|-|
|[operator =](../cpp/com-ptr-t-operator-equal.md)|将新值分配给现有的 **_com_ptr_t** 对象。|
|[运算符 = =、！ =、 \<, > 、 \<=, >=](../cpp/com-ptr-t-relational-operators.md)|将智能指针对象与另一个智能指针、原始接口指针或 NULL 进行比较。|
|[Extractors](../cpp/com-ptr-t-extractors.md)|提取封装的 COM 接口指针。|

**结束 Microsoft 专用**

## <a name="requirements"></a>要求

**标头：**\<comip.h>

**Lib：** comsuppw.lib 或 comsuppwd.lib (参阅 [/zc： Wchar_t (Wchar_t 是本机类型)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md) 有关详细信息) 

## <a name="see-also"></a>请参阅

[编译器 COM 支持类](../cpp/compiler-com-support-classes.md)
