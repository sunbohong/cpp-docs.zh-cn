---
description: 了解详细信息：编译器警告 (等级 1) C4910
title: 编译器警告（等级 1）C4910
ms.date: 11/04/2016
f1_keywords:
- C4910
helpviewer_keywords:
- C4910
ms.assetid: 67963560-fbca-4ca7-93db-06beaf7055f0
ms.openlocfilehash: 4798ba8ae8005239c9cf83e109bdb0f9e4c01928
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97291449"
---
# <a name="compiler-warning-level-1-c4910"></a>编译器警告（等级 1）C4910

" \<identifier> "： "__declspec (dllexport) " 和 "extern" 在显式实例化上不兼容

名为的显式模板实例化 *\<identifier>* 由 `__declspec(dllexport)` 和关键字进行修改 **`extern`** 。 但是，这些关键字互斥。 `__declspec(dllexport)`关键字表示实例化模板类，而 **`extern`** 关键字表示不要自动实例化模板类。

## <a name="see-also"></a>请参阅

[显式实例化](../../cpp/explicit-instantiation.md)<br/>
[dllexport、dllimport](../../cpp/dllexport-dllimport.md)<br/>
[一般规则和限制](../../cpp/general-rules-and-limitations.md)
