---
description: 了解详细信息：为 BSTR 分配和释放内存
title: 为 BSTR 分配和释放内存
ms.date: 11/04/2016
f1_keywords:
- bstr
helpviewer_keywords:
- BSTRs, memory allocation
- memory deallocation, string memory
- memory [C++], releasing
- memory allocation, BSTRs
- memory deallocation, BSTR memory
- strings [C++], releasing
ms.assetid: 98041e29-3442-4a02-b425-7a4a13e9cc84
ms.openlocfilehash: 2b027bdc5615578bc785075ae7e8709e2b3a7ea5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97142658"
---
# <a name="allocating-and-releasing-memory-for-a-bstr"></a>为 BSTR 分配和释放内存

当你创建 `BSTR` 并在 COM 对象之间传递这些对象时，必须小心处理它们使用的内存，以避免内存泄漏。 如果在 `BSTR` 接口中保持不变，则必须在完成后释放其内存。 但是，当 `BSTR` 传入接口时，接收对象负责处理其内存管理。

通常，分配和释放分配给的内存的规则如下所示 `BSTR` ：

- 当调入需要参数的函数时 `BSTR` ，必须在调用前分配的内存， `BSTR` 然后再释放它。 例如：

   [!code-cpp[NVC_ATLMFC_Utilities#192](../atl-mfc-shared/codesnippet/cpp/allocating-and-releasing-memory-for-a-bstr_1.cpp)]

   [!code-cpp[NVC_ATLMFC_Utilities#193](../atl-mfc-shared/codesnippet/cpp/allocating-and-releasing-memory-for-a-bstr_2.cpp)]

- 当调用返回的函数时 `BSTR` ，必须自行释放字符串。 例如：

   [!code-cpp[NVC_ATLMFC_Utilities#194](../atl-mfc-shared/codesnippet/cpp/allocating-and-releasing-memory-for-a-bstr_3.cpp)]

   [!code-cpp[NVC_ATLMFC_Utilities#195](../atl-mfc-shared/codesnippet/cpp/allocating-and-releasing-memory-for-a-bstr_4.cpp)]

- 在实现返回的函数时 `BSTR` ，请分配字符串，但不要释放它。 接收函数会释放内存。 例如：

   [!code-cpp[NVC_ATLMFC_Utilities#196](../atl-mfc-shared/codesnippet/cpp/allocating-and-releasing-memory-for-a-bstr_5.cpp)]

## <a name="see-also"></a>请参阅

[ATL/MFC (字符串) ](../atl-mfc-shared/strings-atl-mfc.md)<br/>
[CStringT：： AllocSysString](../atl-mfc-shared/reference/cstringt-class.md#allocsysstring)<br/>
[SysAllocString](/windows/win32/api/oleauto/nf-oleauto-sysallocstring)<br/>
[SysFreeString](/windows/win32/api/oleauto/nf-oleauto-sysfreestring)
