---
description: 了解详细信息： ASP、ATL Active Server Page 组件向导
title: ASP，ATL Active Server Page 组件向导
ms.date: 11/04/2016
f1_keywords:
- vc.codewiz.class.atl.asp.asp
helpviewer_keywords:
- ATL Active Server Page Component Wizard, ASP
ms.assetid: 4d8cafd6-5e12-4461-8911-29288896af3c
ms.openlocfilehash: e9cc11cf60c3a87d6891c98a72eb240729d1a739
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97165532"
---
# <a name="asp-atl-active-server-page-component-wizard"></a>ASP，ATL Active Server Page 组件向导

使用 ATL Active Server Page 组件向导的此页可以指定用于处理与 ASP 组件相关的信息和状态的可选设置。

- **可选方法**

   将可选的 ASP 方法 **OnStartPage** 和 **OnEndPage** 添加到对象。 必须选择此选项以设置任何活动服务器页内部对象。 默认情况下，此选项处于选中状态。

- **OnStartPage/OnEndPage**

   第一次尝试访问对象时，将调用[OnStartPage](/previous-versions//ms691624\(v=vs.85\)) 。 当对象处理完脚本后，将调用 **OnEndPage** 。

- **内部对象**

   您必须选择 **OnStartPage/OnEndPage** 选项来设置任何 ASP 内部对象。

|选项|描述|
|------------|-----------------|
|**请求**|提供对 Active Server Pages 内部 **请求** 对象的访问权限。 Request 对象用于传递 HTTP 请求。|
|**响应**|提供对 Active Server Pages 内部 **响应** 对象的访问。 响应请求时，响应对象会将信息发送到浏览器以向用户显示信息。|
|**会话**|提供对 Active Server Pages 内部 **会话** 对象的访问权限。 **Session** 对象维护有关当前用户会话的信息，包括存储和检索状态信息。|
|**应用程序**|提供对 Active Server Pages 内部 **应用程序** 对象的访问。 **应用程序** 对象管理跨多个 ASP 对象共享的状态。|
|**服务器**|提供对 Active Server Pages 固有 **服务器** 对象的访问权限。 **服务器** 对象允许您创建其他 ASP 对象。|

## <a name="see-also"></a>请参阅

[ATL Active Server Page 组件向导](../../atl/reference/atl-active-server-page-component-wizard.md)<br/>
[ATL Active Server Page 组件](../../atl/reference/adding-an-atl-active-server-page-component.md)
