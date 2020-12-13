---
description: 了解详细信息： DCOMCNFG.EXE
title: DCOMCNFG
ms.date: 11/04/2016
helpviewer_keywords:
- DCOMCNFG utility
- DCOM, configuring in ATL
ms.assetid: 5a8126e9-ef27-40fb-a66e-9dce8d1a7e80
ms.openlocfilehash: d99b0018d63cedbccaf57ec4cadeb649f390dcf1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97153156"
---
# <a name="dcomcnfg"></a>DCOMCNFG

DCOMCNFG.EXE 是一种 Windows NT 4.0 实用程序，可用于在注册表中配置各种 DCOM 特定设置。 DCOMCNFG.EXE 窗口包含三个页面：默认安全性、默认属性和应用程序。 在 Windows 2000 下，有第四页（默认协议）。

## <a name="default-security-page"></a>默认安全页

您可以使用 "默认安全" 页来指定系统上对象的默认权限。 默认的 "安全" 页包含三个部分： "访问"、"启动" 和 "配置"。 若要更改节的默认值，请单击相应的 " **编辑默认值** " 按钮。 这些默认安全设置存储在下的注册表中 `HKEY_LOCAL_MACHINE\Software\Microsoft\OLE` 。

## <a name="default-protocols-page"></a>"默认协议" 页

此页列出了可用于此计算机上的 DCOM 的网络协议集。 顺序反映了它们将使用的优先级;列表中的第一个具有最高优先级。 可以在此页中添加或删除协议。

## <a name="default-properties-page"></a>默认属性页

如果希望其他计算机上的客户端访问在此计算机上运行的 COM 对象，则必须在 "默认属性" 页上选中 "在 **此计算机上启用分布式 COM** " 复选框。 选择此选项会将 `HKEY_LOCAL_MACHINE\Software\Microsoft\OLE\EnableDCOM` 值设置为 `Y` 。

## <a name="applications-page"></a>应用程序页面

您可以使用 "应用程序" 页更改特定对象的设置。 只需从列表中选择应用程序，然后单击 " **属性** " 按钮。 属性窗口包含五个页面：

- "常规" 页确认正在处理的应用程序。

- 使用 "位置" 页，可以指定客户端调用相关 CLSID 时应运行应用程序的位置 `CoCreateInstance` 。 如果选中 "在 **下列计算机上运行应用程序** " 复选框并输入计算机名称，则 `RemoteServerName` 会在该应用程序的 AppID 下添加一个值。 清除 " **在此计算机上运行应用程序** " 复选框会将值重命名 `LocalService` 为， `_LocalService` 从而禁用它。

- "安全性" 页类似于 "DCOMCNFG.EXE" 窗口中的 "默认安全性" 页，只不过这些设置仅应用于当前应用程序。 同样，设置存储在该对象的 AppID 下。

- 标识页面标识了用于运行应用程序的用户。

- "终结点" 页列出了可供所选 DCOM 服务器的客户端使用的协议和终结点的集合。

## <a name="see-also"></a>请参阅

[服务](../atl/atl-services.md)
