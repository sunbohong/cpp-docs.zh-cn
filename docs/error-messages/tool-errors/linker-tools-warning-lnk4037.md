---
description: 了解详细信息：链接器工具警告 LNK4037
title: 链接器工具警告 LNK4037
ms.date: 10/04/2017
f1_keywords:
- LNK4037
helpviewer_keywords:
- LNK4037
ms.assetid: 9ba02fd3-b04f-4679-bab9-26fa82cf09bb
ms.openlocfilehash: 78fd5ed9f8e2f82221b64053607846f1b8abc00a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97331959"
---
# <a name="linker-tools-warning-lnk4037"></a>链接器工具警告 LNK4037

>"*symbol*" 不存在;掉

由于无法在程序中找到修饰名 *符号* ，因此无法使用 [该方法对](../../build/reference/order-put-functions-in-order.md) 其进行排序。 检查订单响应文件中的 *符号* 。 有关详细信息，请参阅 [/order (按顺序放置函数) ](../../build/reference/order-put-functions-in-order.md) 链接器选项。

> [!NOTE]
> 由于静态函数名称不是公共符号名称，因此 LINK 无法对静态函数进行排序。 指定 **/order** 后，将为顺序响应文件中的每个符号（静态或未找到）生成此链接器警告。
