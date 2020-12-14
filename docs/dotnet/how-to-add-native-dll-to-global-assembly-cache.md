---
description: 了解有关详细信息，请参阅如何：向全局程序集缓存添加本机 DLL
title: 如何：向全局程序集缓存添加本机 DLL
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- DLLs [C++], native
- GAC (global assembly cache), loading native DLLs
- native DLLs [C++]
ms.assetid: 25e8d78a-b197-4269-b4e9-237a544ab3c8
ms.openlocfilehash: 267bc2f08fdd40da03b71222c48786ab7cc150fd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97335410"
---
# <a name="how-to-add-native-dll-to-global-assembly-cache"></a>如何：向全局程序集缓存添加本机 DLL

可以将本机 DLL (非 COM) 添加到全局程序集缓存中。

## <a name="example"></a>示例

**/ASSEMBLYLINKRESOURCE** 使你能够将本机 DLL 嵌入到程序集中。

有关详细信息，请参阅 [/ASSEMBLYLINKRESOURCE (链接到 .NET Framework 资源) ](../build/reference/assemblylinkresource-link-to-dotnet-framework-resource.md)。

```
/ASSEMBLYLINKRESOURCE:MyComponent.dll
```

## <a name="see-also"></a>请参阅

[使用 c + + 互操作 (隐式 PInvoke) ](../dotnet/using-cpp-interop-implicit-pinvoke.md)
