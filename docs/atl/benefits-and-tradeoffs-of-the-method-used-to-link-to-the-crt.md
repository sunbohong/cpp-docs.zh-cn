---
description: 了解更多相关信息：用于链接到 CRT 的方法的优点和折衷
title: 用于链接到 CRT 的方法的优点和折衷
ms.date: 05/06/2019
helpviewer_keywords:
- _ATL_MIN_CRT macro
ms.assetid: 49b485f7-9487-49e4-b12a-0f710b620e2b
ms.openlocfilehash: 763332de9615e978d84902f67f2c97efd0767c89
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97148520"
---
# <a name="benefits-and-tradeoffs-of-the-method-used-to-link-to-the-crt"></a>用于链接到 CRT 的方法的优点和折衷

你的项目可以动态或静态地链接到 CRT。 下表概述了选择使用哪种方法时所涉及的优点和利弊。

|方法|好处|最佳|
|------------|-------------|--------------|
|静态链接到 CRT<br /><br />  (**运行时库** 设置为 **单线程**) |CRT DLL 在运行映像的系统上不是必需的。|将25K 启动代码添加到映像，大大增加其大小。|
|动态链接到 CRT<br /><br />  (**运行时库** 设置为 **多线程**) |您的图像不需要 CRT 启动代码，因此它要小得多。|CRT DLL 必须在运行该映像的系统上。|

在 [ATL 项目中链接到 crt](../atl/linking-to-the-crt-in-your-atl-project.md) 的主题讨论如何选择链接到 crt 的方式。

## <a name="see-also"></a>请参阅

[用 ATL 和 C Run-Time 代码编程](../atl/programming-with-atl-and-c-run-time-code.md)<br/>
[DLL 和 Visual C++ 运行时库行为](../build/run-time-library-behavior.md)<br/>
[CRT 库功能](../c-runtime-library/crt-library-features.md)
