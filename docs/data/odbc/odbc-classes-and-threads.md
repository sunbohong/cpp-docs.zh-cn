---
description: 了解更多： ODBC 类和线程
title: ODBC 类和线程
ms.date: 11/04/2016
helpviewer_keywords:
- ODBC classes, and threads
- ODBC, multithreaded applications
- threading [MFC], ODBC support
ms.assetid: 16543926-7331-41a6-ba50-72288f2a61b7
ms.openlocfilehash: bff5ef5a53543b2e0ffa7888f469ed4ce1e54a37
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97161073"
---
# <a name="odbc-classes-and-threads"></a>ODBC 类和线程

从 MFC 4.2 开始，为 MFC ODBC 类提供多线程支持。 但请注意，MFC 不为 DAO 类提供多线程支持。

对 ODBC 类的多线程支持有一些限制。 由于这些类包装了 ODBC API，因此它们被限制为对其生成的组件的多线程支持。 例如，许多 ODBC 驱动程序不是线程安全的;因此，如果将 MFC ODBC 类与其中一个驱动程序一起使用，则它们不是线程安全的。 你应验证特定驱动程序是否是线程安全的。

创建多线程应用程序时，应非常小心地使用多个线程来处理相同的对象。 例如， `CRecordset` 如果在两个线程中使用同一对象，则在检索数据时可能会导致问题; 一个线程中的提取操作可能会覆盖在另一个线程中提取的数据。 在单独的线程中，MFC ODBC 类更常见的用法是在 `CDatabase` 各个线程之间共享一个打开的对象，以使用同一 ODBC 连接， `CRecordset` 每个线程中有一个单独的对象。 请注意，不应将未打开的 `CDatabase` 对象传递给 `CRecordset` 另一个线程中的对象。

> [!NOTE]
> 如果必须有多个线程处理同一个对象，则应实现适当的同步机制，如关键部分。 请注意，某些操作（如 `Open` ）不受保护。 应确保不会从单独的线程同时调用这些操作。

有关创建多线程应用程序的详细信息，请参阅 [多线程主题](../../parallel/multithreading-support-for-older-code-visual-cpp.md)。

## <a name="see-also"></a>请参阅

[ODBC)  (打开数据库连接 ](../../data/odbc/open-database-connectivity-odbc.md)<br/>
[MFC/ATL (的数据访问编程) ](../../data/data-access-programming-mfc-atl.md)
