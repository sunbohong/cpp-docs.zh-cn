---
description: '了解详细信息：模板 ref 类 (c + +/CX) '
title: 模板 ref 类 (C++/CX)
ms.date: 01/22/2017
ms.assetid: a24d5f45-8dbb-4540-958f-c76c90d8ed93
ms.openlocfilehash: c8f3e668dddd80a2ce05f10f9a5d2ada30096c3e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97307621"
---
# <a name="template-ref-classes-ccx"></a>模板 ref 类 (C++/CX)

C++ 模板没有发布到元数据，因此你的程序中不能具有公共或受保护的可访问性。 当然，你可在程序内部使用标准 C++ 模板。 此外，你可将私有 ref 类定义为模板，并可将显式专用模板 ref 类声明为公共 ref 类中的私有成员。

## <a name="authoring-ref-class-templates"></a>创作 ref 类模板

下面的示例演示如何将私有 ref 类声明为模板，如何声明标准 C++ 模板，以及如何将二者同时声明为公共 ref 类中的成员。 请注意，标准 c + + 模板可通过 Windows 运行时类型（在此示例中为 Platform：： String ^）来专用化。

[!code-cpp[cx_templates#01](../cppcx/codesnippet/CPP/templatedemo/class1.h#01)]

## <a name="see-also"></a>请参阅

[类型系统 (C++/CX)](../cppcx/type-system-c-cx.md)<br/>
[C + +/CX 语言参考](../cppcx/visual-c-language-reference-c-cx.md)<br/>
[命名空间引用](../cppcx/namespaces-reference-c-cx.md)
