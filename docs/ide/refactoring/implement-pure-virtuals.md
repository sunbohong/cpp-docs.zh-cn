---
description: 详细了解：实现纯虚方法
title: 实现纯虚方法
ms.date: 11/16/2016
ms.assetid: ea9b4719-34a3-474a-b4ec-05b1859f80f1
ms.openlocfilehash: b35ebba556ed9bae6ded649caca000b7d3554480
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97318749"
---
# <a name="implement-pure-virtuals"></a>实现纯虚方法

功能：让你可以立即生成实现类中所有纯虚方法所需的代码。

时间：想要从具有纯虚函数的类中继承时使用该功能。

原因：可以手动逐一实现所有纯虚函数，但此功能可自动生成所有方法签名。

方法：

1. 将文本或鼠标光标置于想要在其中实现基类的纯虚函数的类上。

   ![突出显示的代码](images/virtuals_highlight.png)

1. 接下来，执行以下操作之一：
   * **键盘**
     * 按“Ctrl+.” 触发“快捷操作和重构”菜单并从上下文菜单选择“实现 "ClassName" 类的所有纯虚方法”，其中 ClassName 是所选类的名称 ****。
   * **鼠标**
     * 右键单击并选择“快捷操作和重构”菜单并从上下文菜单选择“实现 "ClassName" 类的所有纯虚方法”，其中 ClassName 是所选类的名称 ****。

1. 将自动创建纯虚方法签名，以供实现。

   ![实现纯虚方法结果](images/virtuals_result.png)
