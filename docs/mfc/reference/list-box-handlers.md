---
description: 了解详细信息：列表框处理程序
title: 列表框处理程序
ms.date: 11/04/2016
f1_keywords:
- ON_LBN_DBLCLK
- ON_LBN_ERRSPACE
- ON_LBN_SETFOCUS
- ON_LBN_SELCHANGE
- ON_LBN_KILLFOCUS
helpviewer_keywords:
- list boxes [MFC], list box handlers
- ON_LBN_KILLFOCUS
- ON_LBN_ERRSPACE
- ON_LBN_SELCHANGE
- ON_LBN_SETFOCUS
- ON_LBN_DBLCLK
ms.assetid: e4e54412-2167-436a-883b-5dcad01820b8
ms.openlocfilehash: 190833fed725009729a5895f3b302da4c897fb51
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97219416"
---
# <a name="list-box-handlers"></a>列表框处理程序

以下映射项具有对应的函数原型。

|映射条目|函数原型|
|---------------|------------------------|
|ON_LBN_DBLCLK ( \<id> ， \<memberFxn> ) |afx_msg void memberFxn ( ) ;|
|ON_LBN_ERRSPACE ( \<id> ， \<memberFxn> ) |afx_msg void memberFxn ( ) ;|
|ON_LBN_KILLFOCUS ( \<id> ， \<memberFxn> ) |afx_msg void memberFxn ( ) ;|
|ON_LBN_SELCHANGE ( \<id> ， \<memberFxn> ) |afx_msg void memberFxn ( ) ;|
|ON_LBN_SETFOCUS ( \<id> ， \<memberFxn> ) |afx_msg void memberFxn ( ) ;|

## <a name="see-also"></a>请参阅

[消息映射](../../mfc/reference/message-maps-mfc.md)
