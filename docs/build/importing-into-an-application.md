---
description: 详细了解：导入到应用程序中
title: 导入到应用程序中
ms.date: 11/04/2016
helpviewer_keywords:
- DLLs [C++], importing
- importing DLLs [C++], applications
- applications [C++], importing into
ms.assetid: 9d646466-e12e-4710-8ad9-c819c0375fcc
ms.openlocfilehash: e82f16d9a82f196ff3bb59cc6a7c165d71395a65
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97162529"
---
# <a name="importing-into-an-application"></a>导入到应用程序中

可以使用两种方法将函数导入应用程序：

- 在主应用程序的函数定义中使用关键字 `__declspec(dllimport)`

- 结合使用模板定义 (.def) 文件和 `__declspec(dllimport)`

## <a name="what-do-you-want-to-do"></a>你希望做什么？

- [使用 __declspec(dllimport) 导入到应用程序中](importing-into-an-application-using-declspec-dllimport.md)

- [使用 __declspec(dllimport) 导入函数调用](importing-function-calls-using-declspec-dllimport.md)

- [使用 __declspec(dllimport) 导入数据](importing-data-using-declspec-dllimport.md)

- [使用 DEF 文件导入](importing-using-def-files.md)

## <a name="see-also"></a>请参阅

[导入和导出](importing-and-exporting.md)
