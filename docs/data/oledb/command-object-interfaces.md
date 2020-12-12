---
description: 了解详细信息：命令对象接口
title: Command 对象接口
ms.date: 10/24/2018
helpviewer_keywords:
- command object interfaces [C++]
- command objects [OLE DB]
- OLE DB [C++], command object interfaces
ms.assetid: dacff5ae-252c-4f20-9ad7-4e602cc48536
ms.openlocfilehash: 07dce6a71e7afd3a47c63942d48dd78d758103f8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97307517"
---
# <a name="command-object-interfaces"></a>Command 对象接口

Command 对象使用 `IAccessor` 接口指定参数绑定。 使用者调用 `IAccessor::CreateAccessor` ，并向其传递一个 `DBBINDING` 结构数组。 `DBBINDING` 包含有关列绑定 (如类型和长度) 的信息。 提供程序接收结构并确定应如何传输数据以及是否需要进行转换。

`ICommandText`接口提供一种方法来指定文本命令。 `ICommandProperties`接口处理所有命令属性。

## <a name="see-also"></a>请参阅

[OLE DB 提供程序模板体系结构](../../data/oledb/ole-db-provider-template-architecture.md)<br/>
