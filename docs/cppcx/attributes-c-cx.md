---
description: '了解详细信息： (c + +/CX 的特性) '
title: 特性 (C++/CX)
ms.date: 12/30/2016
ms.assetid: 4438e03c-4de3-433d-abcc-31aa863bc0e0
ms.openlocfilehash: 82299db6b5c11521584b8dd400b401ec0df78c72
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97302772"
---
# <a name="attributes-ccx"></a>特性 (C++/CX)

特性是一种特殊的 ref 类，可在方括号中预置，以便 Windows 运行时类型和方法来指定元数据创建中的某些行为。 一些预定义的属性（例如，  [Windows：： Foundation：： Metadata：： WebHostHidden](/uwp/api/windows.foundation.metadata.webhosthiddenattribute)）通常在 c + +/cx 代码中使用。 此示例演示如何将特性应用于类：

[!code-cpp[cx_attributes#01](../cppcx/codesnippet/CPP/cx_attributes/class1.h#01)]

## <a name="custom-attributes"></a>自定义特性

还可以定义自定义特性。 自定义属性必须符合以下 Windows 运行时规则：

- 自定义特性只能包含公共字段。

- 自定义特性字段可在将特性应用于类时初始化。

- 字段可属于下列类型之一：

  - int32 (int)

  - uint32 (unsigned int)

  - bool

  - Platform::String^

  - Windows::Foundation::HResult

  - Platform::Type^

  - 公共枚举类（包括用户定义的枚举）

下一个示例演示如何定义自定义特性，并在你使用它时进行初始化。

[!code-cpp[cx_attributes#02](../cppcx/codesnippet/CPP/cx_attributes/class1.h#02)]

## <a name="see-also"></a>请参阅

[类型系统 (C++/CX)](../cppcx/type-system-c-cx.md)<br/>
[C + +/CX 语言参考](../cppcx/visual-c-language-reference-c-cx.md)<br/>
[命名空间引用](../cppcx/namespaces-reference-c-cx.md)
