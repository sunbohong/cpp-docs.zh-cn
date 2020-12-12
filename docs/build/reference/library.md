---
description: 了解详细信息：库
title: LIBRARY
ms.date: 11/04/2016
f1_keywords:
- LIBRARY
helpviewer_keywords:
- LIBRARY .def file statement
ms.assetid: 1d7ccc92-e088-4ef7-9ef0-25c3862cc051
ms.openlocfilehash: 3d8c63f323568949cf2fb30935d2557755346422
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97199527"
---
# <a name="library"></a>LIBRARY

指示链接创建一个 DLL。 同时，LINK 创建导入库，除非在生成中使用 exp 文件。

```
LIBRARY [library][BASE=address]
```

## <a name="remarks"></a>备注

*Library* 参数指定 DLL 的名称。 你还可以使用 [/out](out-output-file-name.md) 链接器选项来指定 DLL 的输出名称。

BASE =*address* 参数设置操作系统用于加载 DLL 的基址。 此参数将重写0x10000000 的默认 DLL 位置。 有关基址的详细信息，请参阅 [/base](base-base-address.md) 选项的说明。

生成 DLL 时，请记住使用 [/DLL](dll-build-a-dll.md) 链接器选项。

## <a name="see-also"></a>请参阅

[Module-Definition 语句的规则](rules-for-module-definition-statements.md)
