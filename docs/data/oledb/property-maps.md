---
description: 了解详细信息：属性映射
title: 属性映射
ms.date: 10/24/2018
helpviewer_keywords:
- OLE DB providers, properties
- maps, property
- property maps
ms.assetid: 44abde56-90ad-4612-854e-d2fa5426fa80
ms.openlocfilehash: 30b277451d871de45902661f7b7e56cbc7409c97
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97316903"
---
# <a name="property-maps"></a>属性映射

对于 session、rowset 和 optional 命令对象，每个提供程序都支持一个或多个属性。 这些属性是在存储在由 **OLE DB 提供程序向导** 创建的标头文件中的属性映射中定义的。 每个标头文件都包含为该文件中定义的对象或对象定义的 OLE DB 属性组中的属性的映射。 包含数据源对象的标头文件还包含数据源 [属性](/previous-versions/windows/desktop/ms724188(v=vs.85))的属性映射。 `Session.h` 包含 [会话属性](/previous-versions/windows/desktop/ms714221(v=vs.85))的属性映射。 行集和命令对象位于一个名为 " *项目名称* RS .h" 的头文件中。 这些属性是 [行集属性](/previous-versions/windows/desktop/ms711252(v=vs.85)) 组的成员。

## <a name="see-also"></a>请参阅

[OLE DB 提供程序模板体系结构](../../data/oledb/ole-db-provider-template-architecture.md)<br/>
