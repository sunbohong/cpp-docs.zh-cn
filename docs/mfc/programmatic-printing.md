---
description: 了解详细信息：编程打印
title: 以编程方式打印
ms.date: 11/04/2016
helpviewer_keywords:
- printing [MFC], active documents
- active documents [MFC], printing
- printing [MFC], programmatic
- IPrint interface
- printing [MFC]
ms.assetid: 3db0945b-5e13-4be4-86a0-6aecdae565bd
ms.openlocfilehash: c97a3938a97970e1479add4f62b68250845ba7e1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97154690"
---
# <a name="programmatic-printing"></a>以编程方式打印

OLE 提供了唯一标识持久文档 (`GetClassFile`) 并将它们加载到其关联代码中的方法 (`CoCreateInstance` 、 `QueryInterface(IID_IPersistFile)` 、 `QueryInterface(IID_IPersistStorage)` 、 `IPersistFile::Load` 和 `IPersistStorage::Load`) 。 为了进一步启用打印文档，活动文档包容（使用最初未随 OLE 2.0 一起提供的现有 OLE 设计）引入了一个基本标准的打印接口 `IPrint`（通常可以通过任何能够加载文档类型的持久状态的对象获取）。 活动文档的每个视图都可以选择支持 `IPrint` 接口以提供这些功能。

`IPrint` 接口定义如下：

```
interface IPrint : IUnknown
    {
    HRESULT SetInitialPageNum([in] LONG nFirstPage);
    HRESULT GetPageInfo(
        [out] LONG *pnFirstPage,
        [out] LONG *pcPages);
    HRESULT Print(
        [in] DWORD grfFlags,
        [in,out] DVTARGETDEVICE **pptd,
        [in,out] PAGESET ** ppPageSet,
        [in,out] STGMEDIUM **ppstgmOptions,
        [in] IContinueCallback* pCallback,
        [in] LONG nFirstPage,
        [out] LONG *pcPagesPrinted,
        [out] LONG *pnPageLast);
    };
```

仅 `IPrint::Print` 当加载文档、指定打印控制标志、目标设备、要打印的页面以及附加选项时，客户端和容器才会使用指示文档自行打印。 客户端还可以通过 `IContinueCallback` 接口来控制打印的继续（如下所示）。

此外， `IPrint::SetInitialPageNum` 支持通过对页面进行无缝编码来打印一系列文档，这显然是活动文档容器（如 Office 活页夹）的一个优点。 `IPrint::GetPageInfo` 通过允许调用方检索之前传递到 `SetInitialPageNum` (或文档的内部默认起始页码) 和文档中的页数，使显示分页信息变得简单。

支持 `IPrint` 的对象在注册表中使用存储在该对象的 CLSID 下的“Printable”注册表项标记：

HKEY_CLASSES_ROOT\CLSID\\ {...}\Printable

通常在支持 `IPrint` 或 `IPersistFile` 的相同对象上实现 `IPersistStorage`。 调用方通过查看注册表中的“Printable”注册表项，可以了解到以编程方式打印某些类的持久状态的能力。 目前，"可打印" 指示至少支持 `IPrint` ; 可能会在将来定义其他接口，其中 `QueryInterface` 只是 `IPrint` 表示支持的基本级别。

在打印过程中，您可能希望启动打印的客户端或容器控制打印是否应继续。 例如，容器可以支持应尽快终止打印作业的“停止打印”命令。 若要支持此功能，可打印对象的客户端可以使用 `IContinueCallback` 接口实现一个小的通知接收器对象：

```
interface IContinueCallback : IUnknown
    {
    HRESULT FContinue(void);
    HRESULT FContinuePrinting(
        [in] LONG cPagesPrinted,
        [in] LONG nCurrentPage,
        [in] LPOLESTR pszPrintStatus);
    };
```

此接口旨在用作一般的延续回调函数，该函数采用 Win32 API (中的各种继续过程，例如 `AbortProc` 用于打印的和 `EnumMetafileProc` 用于图元文件枚举) 的。 因此，在各种耗时的过程中，此接口设计都非常有用。

在最常见的情况下， `IContinueCallback::FContinue` 任何冗长的进程都将定期调用此函数。 Sink 对象将返回 S_OK 以继续操作，并 S_FALSE 尽快停止该过程。

`FContinue`但是，在的上下文中未使用 `IPrint::Print` ; 而是使用打印 `IContinueCallback::FContinuePrint` 。 任何打印对象应定期调用 `FContinuePrinting` 传递已打印的页数、要打印的页面的数量，以及描述客户端可以选择显示给 (用户的打印状态的其他字符串，如 "第5页，共19页" ) 。

## <a name="see-also"></a>请参阅

[活动文档容器](../mfc/active-document-containers.md)
