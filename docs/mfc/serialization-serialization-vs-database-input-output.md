---
description: 了解详细信息：序列化：序列化与数据库输入/输出
title: 序列化：序列化与数据库 Input-Output
ms.date: 11/04/2016
helpviewer_keywords:
- database applications [MFC], file I/O vs. serialization
- serialization [MFC], vs. database I/O
- I/O [MFC], vs. serialization
- databases [MFC], input/output handling
ms.assetid: f1d23d77-4761-4a52-a7ea-54fc92d347ea
ms.openlocfilehash: d2c2c8aa9597e23ac3e6caefcb2adb8b31dc3e93
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97217505"
---
# <a name="serialization-serialization-vs-database-inputoutput"></a>序列化：序列化与数据库输入/输出的对比

本文说明了何时使用文档对象和序列化来处理基于文件的输入/输出 (i/o) 和其他 i/o 方法，因为应用程序会按照每个事务的方式读取和写入数据，与在数据库应用程序中一样。 如果不使用序列化，则不需要文件打开、保存和另存为命令。 涵盖的主题包括：

- [关于处理输入/输出的建议](../mfc/recommendations-for-handling-input-output.md)

- [处理数据库应用程序中的 "文件" 菜单](../mfc/file-menu-in-an-mfc-database-application.md)

## <a name="see-also"></a>请参阅

[序列化](../mfc/serialization-in-mfc.md)
