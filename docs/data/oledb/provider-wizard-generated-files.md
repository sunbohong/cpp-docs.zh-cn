---
description: 了解详细信息：提供程序 Wizard-Generated 文件
title: 提供程序向导生成的文件
ms.date: 05/09/2019
helpviewer_keywords:
- OLE DB providers, wizard-generated files
ms.assetid: 6e1ac94b-eb90-4abf-82b3-06944b947ebc
ms.openlocfilehash: 95c9641f10acef4a55b8de15752eb125e75d874a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97316890"
---
# <a name="provider-wizard-generated-files"></a>提供程序向导生成的文件

::: moniker range="msvc-160"

ATL OLE DB 提供程序向导不适用于 Visual Studio 2019 及更高版本。

::: moniker-end

::: moniker range="<=msvc-150"

ATL OLE DB 提供程序向导生成以下文件。 下面的主题使用短名称“Custom”，但确切文件名具体视你在创建提供程序时所做的选择而定。

|文件名|说明|
|---------------|-----------------|
|CustomRS.cpp|包含命令帮助程序 `Execute` 方法和提供程序列映射。|
|CustomDS.h|实现数据源对象。 此头文件包含数据源属性的属性映射。|
|CustomRS.h|实现命令和行集对象。 此头文件包含行集和命令属性的属性映射。|
|CustomSess.h|实现会话对象。 此头文件包含会话属性的属性映射。|
|Custom.rgs|包含 OLE DB 提供程序向导生成的已注册对象。|

::: moniker-end

## <a name="see-also"></a>请参阅

[创建 OLE DB 提供程序](../../data/oledb/creating-an-ole-db-provider.md)<br/>
