---
description: 了解详细信息：/TLS
title: /TLS
ms.date: 11/04/2016
f1_keywords:
- /TLS
helpviewer_keywords:
- /TLS dumpbin option
- -TLS dumpbin option
ms.assetid: 2b3f48f9-cac4-4351-b15c-2833b43bc709
ms.openlocfilehash: a21ef03210a65bb50899ba3907911272ac52b0db
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97229946"
---
# <a name="tls"></a>/TLS

显示可执行文件中的 IMAGE_TLS_DIRECTORY 结构。

## <a name="remarks"></a>备注

/TLS 显示 TLS 结构的字段以及 TLS 回调函数的地址。

如果程序未使用线程本地存储，则其映像将不包含 TLS 结构。  有关详细信息，请参阅 [线程](../../cpp/thread.md) 。

IMAGE_TLS_DIRECTORY 在 winnt 中定义。

## <a name="see-also"></a>请参阅

[DUMPBIN 选项](dumpbin-options.md)
