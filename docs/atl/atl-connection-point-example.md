---
description: 了解详细信息： ATL 连接点示例
title: ATL 连接点示例
ms.date: 11/04/2016
helpviewer_keywords:
- connection points [C++], examples
- examples [ATL]
ms.assetid: a49721b7-f308-43de-8868-f662a94bc81a
ms.openlocfilehash: 6416720b5366838f9687f31947cac9a6824da058
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97165805"
---
# <a name="atl-connection-point-example"></a>ATL 连接点示例

此示例显示了一个对象，该对象支持 [IPropertyNotifySink](/windows/win32/api/ocidl/nn-ocidl-ipropertynotifysink) 作为输出接口：

[!code-cpp[NVC_ATL_Windowing#84](../atl/codesnippet/cpp/atl-connection-point-example_1.h)]

指定 `IPropertyNotifySink` 为传出接口时，可以使用类 [IPropertyNotifySinkCP](../atl/reference/ipropertynotifysinkcp-class.md) 而不是 `IConnectionPointImpl` 。 例如：

[!code-cpp[NVC_ATL_Windowing#85](../atl/codesnippet/cpp/atl-connection-point-example_2.h)]

## <a name="see-also"></a>请参阅

[连接点](../atl/atl-connection-points.md)
