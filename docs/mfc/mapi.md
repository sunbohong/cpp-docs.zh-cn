---
description: 了解有关以下内容的详细信息： MAPI
title: MAPI
ms.date: 11/04/2016
helpviewer_keywords:
- messaging [MFC], client applications
- enabling applications for MAPI [MFC]
- MAPI support in MFC
- e-mail [MFC], enabling
- mail [MFC], enabling your application
- MAPI, MFC
- enabling applications for mail [MFC]
ms.assetid: 193449f7-b131-4ab0-9301-8d4f6cd1e7c4
ms.openlocfilehash: 634d5d0b2dbbc8a262f624be2b7e294ef6069b96
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97280802"
---
# <a name="mapi"></a>MAPI

本文介绍面向客户端消息应用程序开发人员的 Microsoft 消息处理应用程序编程接口 (MAPI)。 MFC 为类中的 MAPI 子集提供支持， `CDocument` 但不封装整个 API。 有关详细信息，请参阅 [MFC 中的 MAPI 支持](mapi-support-in-mfc.md)。

MAPI 是一组函数，由启用了邮件的应用程序和邮件感知应用程序用于创建、操作、传输和存储电子邮件。 它为应用程序开发人员提供了定义电子邮件的目的和内容的工具，并使他们能够灵活管理存储的电子邮件。 MAPI 还提供了公共接口，供应用程序开发人员用于独立于基础的邮件系统创建启用了邮件的应用程序和邮件感知应用程序。

消息客户端为了与 Microsoft Windows 邮件系统 (WMS) 交互提供了一个人体学接口。 此交互通常包括从与 MAPI 相容的提供程序处（如消息存储和通讯簿）请求服务。

有关 MAPI 的详细信息，请参阅 Win32 消息 (MAPI) 的 Windows SDK 中的文章。

## <a name="in-this-section"></a>本节内容

[MFC 中的 MAPI 支持](mapi-support-in-mfc.md)

## <a name="see-also"></a>请参阅

[CDocument：： OnFileSendMail](reference/cdocument-class.md#onfilesendmail)<br/>
[CDocument：： OnUpdateFileSendMail](reference/cdocument-class.md#onupdatefilesendmail)<br/>
[COleDocument：： OnFileSendMail](reference/coledocument-class.md#onfilesendmail)
