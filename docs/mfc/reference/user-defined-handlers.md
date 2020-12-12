---
description: 了解详细信息： User-Defined 处理程序
title: 用户定义的处理程序
ms.date: 11/04/2016
helpviewer_keywords:
- ON_REGISTERED_MESSAGE macro [MFC]
- ON_MESSAGE macro [MFC]
- user-defined handlers [MFC]
ms.assetid: 99478294-bef0-4ba7-a369-25a6abdcdb62
ms.openlocfilehash: 8a3b7389d7388fb54ae39d3b1805594b64556652
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97218519"
---
# <a name="user-defined-handlers"></a>用户定义的处理程序

以下映射项对应于函数原型。

|映射条目|函数原型|
|---------------|------------------------|
|ON_MESSAGE ( \<message> ， \<memberFxn> ) |afx_msg LRESULT memberFxn ( WPARAM，LPARAM ) ;|
|ON_REGISTERED_MESSAGE ( \<nMessageVariable> ， \<memberFxn> ) |afx_msg LRESULT memberFxn ( WPARAM，LPARAM ) ;|
|ON_THREAD_MESSAGE ( \<message> ， \<memberFxn> ) |afx_msg void memberFxn ( WPARAM、LPARAM ) ;|
|ON_REGISTERED_THREAD_MESSAGE ( \<nMessageVariable> ， \<memberFxn> ) |afx_msg void memberFxn ( WPARAM、LPARAM ) ;|

## <a name="see-also"></a>请参阅

[消息映射](../../mfc/reference/message-maps-mfc.md)<br/>
[WM_ 消息的处理程序](../../mfc/reference/handlers-for-wm-messages.md)
