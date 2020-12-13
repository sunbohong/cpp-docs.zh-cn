---
description: 了解详细信息：调用脚本
title: " (ATL) 调用脚本"
ms.date: 11/04/2016
helpviewer_keywords:
- StringRegister method
- scripts, invoking registry in ATL
ms.assetid: eabd41ee-586b-4266-9e92-5aaad04b73a4
ms.openlocfilehash: 48fc49118d93893b5cd60462fbaecfdb73d747c3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97152654"
---
# <a name="invoking-scripts"></a>调用脚本

[使用注册器的预处理器 (可替换参数)](../atl/using-replaceable-parameters-the-registrar-s-preprocessor.md) 讨论替换映射，并提及注册器方法 **AddReplacement**。 注册机构有8个特定于脚本编写的其他方法，下表介绍了所有这些方法。

|方法|语法/Description|
|------------|-------------------------|
|**ResourceRegister**|**HRESULT ResourceRegister ( LPCOLESTR***resFileName* **，UINT** `nID` **，LPCOLESTR** `szType` **) ;**      <br /><br /> 注册模块资源中包含的脚本。 *resFileName* 指示模块本身的 UNC 路径。 *nID* 和 *szType* 分别包含资源的 ID 和类型。|
|**ResourceUnregister**|**HRESULT ResourceUnregister ( LPCOLESTR***resFileName* **，UINT** `nID` **，LPCOLESTR** `szType` **) ;**      <br /><br /> 取消注册模块资源中包含的脚本。 *resFileName* 指示模块本身的 UNC 路径。 *nID* 和 *szType* 分别包含资源的 ID 和类型。|
|**ResourceRegisterSz**|**HRESULT ResourceRegisterSz ( LPCOLESTR***resFileName* **、LPCOLESTR***szID* **、LPCOLESTR** `szType` **) ;**      <br /><br /> 注册模块资源中包含的脚本。 *resFileName* 指示模块本身的 UNC 路径。 *szID* 和 *szType* 分别包含资源的字符串标识符和类型。|
|**ResourceUnregisterSz**|**HRESULT ResourceUnregisterSz ( LPCOLESTR***resFileName* **、LPCOLESTR***szID* **、LPCOLESTR** `szType` **) ;**      <br /><br /> 取消注册模块资源中包含的脚本。 *resFileName* 指示模块本身的 UNC 路径。 *szID* 和 *szType* 分别包含资源的字符串标识符和类型。|
|**FileRegister**|**HRESULT FileRegister ( LPCOLESTR***fileName* **) ;**    <br /><br /> 在文件中注册脚本。 *fileName* 是包含 (或) 资源脚本的文件的 UNC 路径。|
|**FileUnregister**|**HRESULT FileUnregister ( LPCOLESTR***fileName* **) ;**    <br /><br /> 注销文件中的脚本。 *fileName* 是包含 (或) 资源脚本的文件的 UNC 路径。|
|**StringRegister**|**HRESULT StringRegister ( LPCOLESTR**  *数据*  **) ;**<br /><br /> 将脚本注册到字符串中。 *数据* 包含脚本本身。|
|**StringUnregister**|**HRESULT StringUnregister ( LPCOLESTR**  *数据*  **) ;**<br /><br /> 取消注册字符串中的脚本。 *数据* 包含脚本本身。|

**ResourceRegisterSz** 和 **ResourceUnregisterSz** 类似于 **ResourceRegister** 和 **ResourceUnregister**，但允许指定字符串标识符。

如果你不想在资源中使用该脚本，或者想要将该脚本放在其自己的文件中，则 **FileRegister** 和 **FileUnregister** 方法非常有用。 方法 **StringRegister** 和 **StringUnregister** 允许将 .rgs 文件存储在动态分配的字符串中。

## <a name="see-also"></a>请参阅

[创建注册器脚本](../atl/creating-registrar-scripts.md)
