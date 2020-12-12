---
description: 了解更多： ATL 服务
title: ATL 服务
ms.date: 11/04/2016
helpviewer_keywords:
- CServiceModule class
- COM objects, ATL
- services, ATL
- ATL services
ms.assetid: 8c09d1a8-7548-4d2c-947c-9d795a81659b
ms.openlocfilehash: 1cb1f526434cefe57dc4675d592f836e04a6cdb6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97148598"
---
# <a name="atl-services"></a>ATL 服务

若要创建 ATL COM 对象，使其在服务中运行，只需从 ATL 项目向导中的服务器选项列表中选择 "Service (EXE) 。 然后，该向导将创建一个派生自的类 `CAtlServiceModuleT` 来实现该服务。

当 ATL COM 对象构建为服务时，它将只注册为本地服务器，并且它不会显示在 "控制面板" 中的 "服务" 列表中。 这是因为，将服务作为本地服务器而不是服务进行调试更为容易。 若要将其安装为服务，请在命令提示符下运行以下命令：

`YourEXE` `.exe /Service`

若要卸载它，请运行以下内容：

`YourEXE` `.exe /UnregServer`

本部分中的前四个主题讨论在成员函数执行过程中发生的操作 `CAtlServiceModuleT` 。 这些主题的显示顺序与通常调用函数的顺序相同。 为了改进您对这些主题的理解，最好使用 ATL 项目向导生成的源代码作为参考。 以下四个主题为：

- [CAtlServiceModuleT：： Start 函数](../atl/reference/catlservicemodulet-class.md#start)

- [CAtlServiceModuleT：： ServiceMain 函数](../atl/reference/catlservicemodulet-class.md#servicemain)

- [CAtlServiceModuleT：： Run 函数](../atl/reference/catlservicemodulet-class.md#run)

- [CAtlServiceModuleT：： Handler 函数](../atl/reference/catlservicemodulet-class.md#handler)

最后三个主题讨论与开发服务相关的概念：

- ATL 服务的[注册表项](../atl/registry-entries.md)

- [DCOMCNFG](../atl/dcomcnfg.md)

- ATL 服务的[调试提示](../atl/debugging-tips.md)

## <a name="see-also"></a>请参阅

[概念](../atl/active-template-library-atl-concepts.md)
