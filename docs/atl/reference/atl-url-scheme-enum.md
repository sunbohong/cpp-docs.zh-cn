---
description: 了解详细信息： ATL_URL_SCHEME
title: ATL_URL_SCHEME 枚举
ms.date: 11/04/2016
helpviewer_keywords:
- ATLUTIL/ATL::ATL_URL_SCHEME
ms.assetid: f4131046-8ba0-4ec1-8209-84203f05d20e
ms.openlocfilehash: 72c149345a0e1edd41bfc9b32d1e94ab6477d488
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97165129"
---
# <a name="atl_url_scheme"></a>ATL_URL_SCHEME

此枚举的成员为 [曲线](curl-class.md)理解的方案提供常数。

## <a name="syntax"></a>语法

```cpp
enum ATL_URL_SCHEME{
   ATL_URL_SCHEME_UNKNOWN = -1,
   ATL_URL_SCHEME_FTP     = 0,
   ATL_URL_SCHEME_GOPHER  = 1,
   ATL_URL_SCHEME_HTTP    = 2,
   ATL_URL_SCHEME_HTTPS   = 3,
   ATL_URL_SCHEME_FILE    = 4,
   ATL_URL_SCHEME_NEWS    = 5,
   ATL_URL_SCHEME_MAILTO  = 6,
   ATL_URL_SCHEME_SOCKS   = 7
};
```

## <a name="requirements"></a>要求

**标头：** atlutil

## <a name="see-also"></a>请参阅

[概念](../active-template-library-atl-concepts.md)<br/>
[卷曲：： SetScheme](curl-class.md#setscheme)<br/>
[卷曲：： GetScheme](curl-class.md#getscheme)
