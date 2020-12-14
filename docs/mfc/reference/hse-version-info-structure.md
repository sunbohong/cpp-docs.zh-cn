---
description: 了解详细信息： HSE_VERSION_INFO 结构
title: HSE_VERSION_INFO 结构
ms.date: 11/04/2016
f1_keywords:
- HSE_VERSION_INFO
helpviewer_keywords:
- HSE_VERSION_INFO structure [MFC]
ms.assetid: 4837312d-68c8-4d05-9afa-1934d7d49b20
ms.openlocfilehash: fe03f3c4e00f9af62398993838927ce75410f17b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97219624"
---
# <a name="hse_version_info-structure"></a>HSE_VERSION_INFO 结构

此结构由成员函数中的 *pVer* 参数指向 `CHttpServer::GetExtensionVersion` 。 它提供 ISA 的 ISA 版本号和文本说明。

## <a name="syntax"></a>语法

```
typedef struct _HSE_VERSION_INFO {
    DWORD dwExtensionVersion;
    CHAR lpszExtensionDesc[HSE_MAX_EXT_DLL_NAME_LEN];
} HSE_VERSION_INFO, *LPHSE_VERSION_INFO;
```

#### <a name="parameters"></a>parameters

*dwExtensionVersion*<br/>
ISA 的版本号。

*lpszExtensionDesc*<br/>
ISA 的文本说明。 默认实现提供占位符文本；重写 `CHttpServer::GetExtensionVersion` 可提供您自己的说明。

## <a name="requirements"></a>要求

**标头：** httpext

## <a name="see-also"></a>请参阅

[结构、样式、回调和消息映射](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)
