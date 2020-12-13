---
description: '了解详细信息：强名称程序集 (程序集签名)  (c + +/CLI) '
title: 强名称程序集（程序集签名）(C++/CLI)
ms.date: 11/04/2016
helpviewer_keywords:
- assemblies [C++]
- signing assemblies
- .NET Framework [C++], assembly signing
- assemblies [C++], signing
- linker [C++], assembly signing
- strong-named assemblies [C++]
ms.assetid: c337cd3f-e5dd-4c6f-a1ad-437e85dba1cc
ms.openlocfilehash: 9fc08df759fa384ed13dbe3d8c3eb2d843183517
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97335314"
---
# <a name="strong-name-assemblies-assembly-signing-ccli"></a>强名称程序集（程序集签名）(C++/CLI)

本主题讨论如何对程序集进行签名，通常称为为程序集提供强名称。

## <a name="remarks"></a>备注

使用 Visual C++ 时，请使用链接器选项对程序集进行签名，以避免与用于程序集签名的 CLR 特性相关的问题：

- <xref:System.Reflection.AssemblyDelaySignAttribute>

- <xref:System.Reflection.AssemblyKeyFileAttribute>

- <xref:System.Reflection.AssemblyKeyNameAttribute>

不使用属性的原因包括密钥名称在程序集元数据中可见，如果文件名包含机密信息，这可能会带来安全风险。 此外，如果你使用 CLR 特性为程序集提供强名称，然后在程序集上运行类似于 mt.exe 的后期处理工具，则 Visual C++ 开发环境使用的生成过程将使程序集签名无效。

如果在命令行中生成，请使用链接器选项对程序集进行签名，然后运行 (如 mt.exe) 的后期处理工具，你将需要使用 sn.exe 对程序集进行重新签名。 或者，您可以生成并延迟对程序集的签名，并在运行后处理工具之后完成签名。

如果在开发环境中生成时使用签名特性，则可以通过在生成后事件中显式调用 sn.exe ([Sn.exe (强名称工具) ](/dotnet/framework/tools/sn-exe-strong-name-tool)) 来成功对程序集进行签名。 有关详细信息，请参阅[指定生成事件](../build/specifying-build-events.md)。 与使用链接器选项相比，如果使用属性和生成后事件，则生成时间可能更少。

以下链接器选项支持程序集签名：

- [/DELAYSIGN (对程序集进行部分签名) ](../build/reference/delaysign-partially-sign-an-assembly.md)

- [/KEYFILE (指定密钥或密钥对以对程序集进行签名) ](../build/reference/keyfile-specify-key-or-key-pair-to-sign-an-assembly.md)

- [/KEYCONTAINER (指定用于对程序集进行签名的密钥容器) ](../build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly.md)

有关强程序集的详细信息，请参阅 [创建和使用 Strong-Named 程序集](/dotnet/framework/app-domains/create-and-use-strong-named-assemblies)。

## <a name="see-also"></a>请参阅

[用 c + +/CLI (Visual C++ 的 .NET 编程) ](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)
