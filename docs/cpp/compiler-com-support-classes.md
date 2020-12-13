---
description: 了解更多：编译器 COM 支持类
title: 编译器 COM 支持类
ms.date: 11/04/2016
helpviewer_keywords:
- cl.exe compiler, COM support
- COM, compiler support
ms.assetid: 6d800d9b-b902-4033-9639-740a30b06f88
ms.openlocfilehash: e2f921e9c3ebe759109d741630afe56f6af30bbc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97344700"
---
# <a name="compiler-com-support-classes"></a>编译器 COM 支持类

**Microsoft 专用**

标准类用于支持某些 COM 类型。 类是在中定义的 \<comdef.h> ，并且是从类型库生成的标头文件。

|类|目标|
|-----------|-------------|
|[_bstr_t](../cpp/bstr-t-class.md)|包装 `BSTR` 类型，以提供有用的运算符和方法。|
|[_com_error](../cpp/com-error-class.md)|定义在大多数失败中由 [_com_raise_error](../cpp/com-raise-error.md) 引发的错误对象。|
|[_com_ptr_t](../cpp/com-ptr-t-class.md)|封装 COM 接口指针，并自动执行对、和所需的调用 `AddRef` `Release` `QueryInterface` 。|
|[_variant_t](../cpp/variant-t-class.md)|包装 `VARIANT` 类型，以提供有用的运算符和方法。|

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[编译器 COM 支持](../cpp/compiler-com-support.md)<br/>
[编译器 COM 全局函数](../cpp/compiler-com-global-functions.md)<br/>
[C++ 语言参考](../cpp/cpp-language-reference.md)
