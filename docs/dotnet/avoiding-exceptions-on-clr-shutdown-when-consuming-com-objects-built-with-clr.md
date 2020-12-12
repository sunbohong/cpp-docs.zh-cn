---
description: 了解更多相关信息：在使用通过/clr 生成的 COM 对象时避免 CLR 关闭异常
title: 避免由-clr 生成的 COM 对象引发的异常
ms.date: 11/04/2016
helpviewer_keywords:
- interop [C++], CLR shutdown exceptions
- /clr compiler option [C++], CLR shutdown exceptions
- mixed assemblies [C++], CLR shutdown exceptions
- /clr compiler option [C++], COM objects
- interoperability [C++], CLR shutdown exceptions
- CLR shutdown exceptions [C++]
ms.assetid: 41249d83-4b51-4e46-866f-27f475f2498c
ms.openlocfilehash: 899f7905aafcf1bff92e37ee70253e74759b3f57
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97282609"
---
# <a name="avoiding-exceptions-on-clr-shutdown-when-consuming-com-objects-built-with-clr"></a>使用以 /clr 生成的 COM 对象时避免 CLR 关闭异常

公共语言运行时 (CLR) 进入关闭模式后，本机函数将对 CLR 服务的访问权限受到限制。 尝试在使用 **/clr** 编译的 COM 对象上调用 Release 时，clr 将转换为本机代码，然后转换回托管代码，以便为在托管代码) 中定义的 IUnknown：： Release (调用提供服务。 CLR 会阻止回调到托管代码，因为它处于关闭模式。

若要解决此问题，请确保从 Release 方法调用的析构函数只包含本机代码。

## <a name="see-also"></a>请参阅

[混合 (本机和托管) 程序集](../dotnet/mixed-native-and-managed-assemblies.md)
