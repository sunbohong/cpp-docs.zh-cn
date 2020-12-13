---
description: 了解详细信息：支持 IDispatch 和 IErrorInfo
title: 支持 IDispatch 和 IErrorInfo
ms.date: 11/04/2016
helpviewer_keywords:
- ISupportErrorInfoImpl method
- IErrorInfo class suppor in ATL
- IDispatchImpl class
- IDispatch class support in ATL
ms.assetid: 7db2220f-319d-4ce9-9382-d340019f14f7
ms.openlocfilehash: 4622c8811fafc9512400345e5876dd24c466bc93
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97138445"
---
# <a name="supporting-idispatch-and-ierrorinfo"></a>支持 IDispatch 和 IErrorInfo

您可以使用模板类 [IDispatchImpl](../atl/reference/idispatchimpl-class.md) 来提供 `IDispatch Interface` 对象上任何双重接口部分的默认实现。

如果对象使用 `IErrorInfo` 接口将错误报告回客户端，则您的对象必须支持 `ISupportErrorInfo Interface` 接口。 模板类 [ISupportErrorInfoImpl](../atl/reference/isupporterrorinfoimpl-class.md) 提供了一种简单的方法来实现此目标，前提是只有单个接口在对象上生成错误。

## <a name="see-also"></a>请参阅

[ATL COM 对象的基本知识](../atl/fundamentals-of-atl-com-objects.md)
