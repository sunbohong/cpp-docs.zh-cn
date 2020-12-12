---
description: 了解更多： WinInet 基础知识
title: WinInet 基础知识
ms.date: 11/04/2016
helpviewer_keywords:
- OnStatusCallback method [MFC]
- WinInet classes [MFC], displaying progress
- WinInet classes [MFC], about WinInet classes
ms.assetid: 665de5ac-e80d-427d-8d91-2ae466885940
ms.openlocfilehash: 1ba8f9b898476849ca9bbb39b7850bbce3605154
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97172773"
---
# <a name="wininet-basics"></a>WinInet 基础知识

您可以使用 WinInet 添加 FTP 支持，以便从您的应用程序内下载和上传文件。 你可以重写 [OnStatusCallback](../mfc/reference/cinternetsession-class.md#onstatuscallback) ，并使用 *dwContext* 参数向用户提供搜索和下载文件的进度信息。

本文包含以下主题：

- [创建一个非常简单的浏览器](#_core_create_a_very_simple_browser)

- [下载网页](#_core_download_a_web_page)

- [FTP 文件](#_core_ftp_a_file)

- [检索 Gopher 目录](#_core_retrieve_a_gopher_directory)

- [传输文件时显示进度信息](#_core_display_progress_information_while_transferring_files)

下面的代码摘录演示了如何创建简单的浏览器、下载网页、FTP 文件以及搜索 gopher 文件。 它们不是作为完整的示例，并且不是全部都包含异常处理。

有关 WinInet 的其他信息，请参阅 [Win32 Internet 扩展 (WinInet) ](../mfc/win32-internet-extensions-wininet.md)。

## <a name="create-a-very-simple-browser"></a><a name="_core_create_a_very_simple_browser"></a> 创建一个非常简单的浏览器

[!code-cpp[NVC_MFCWinInet#1](../mfc/codesnippet/cpp/wininet-basics_1.cpp)]

## <a name="download-a-web-page"></a><a name="_core_download_a_web_page"></a> 下载网页

[!code-cpp[NVC_MFCWinInet#2](../mfc/codesnippet/cpp/wininet-basics_2.cpp)]

## <a name="ftp-a-file"></a><a name="_core_ftp_a_file"></a> FTP 文件

[!code-cpp[NVC_MFCWinInet#3](../mfc/codesnippet/cpp/wininet-basics_3.cpp)]

## <a name="retrieve-a-gopher-directory"></a><a name="_core_retrieve_a_gopher_directory"></a> 检索 Gopher 目录

[!code-cpp[NVC_MFCWinInet#4](../mfc/codesnippet/cpp/wininet-basics_4.cpp)]

## <a name="use-onstatuscallback"></a>使用 OnStatusCallback

使用 WinInet 类时，可以使用应用程序的[CInternetSession](../mfc/reference/cinternetsession-class.md)对象的[OnStatusCallback](../mfc/reference/cinternetsession-class.md#onstatuscallback)成员来检索状态信息。 如果你派生自己的 `CInternetSession` 对象、重写 `OnStatusCallback` 和启用状态回调，则 MFC 将调用你 `OnStatusCallback` 的函数，其中包含有关该 Internet 会话中所有活动的进度信息。

由于单个会话可能支持多个连接 (在这些连接的生存期内，可能会执行许多不同的不同操作) ， `OnStatusCallback` 需要一种机制来识别使用特定连接或事务的每个状态更改。 该机制由为 WinInet 支持类中的许多成员函数提供的上下文 ID 参数提供。 此参数始终为 **DWORD** 类型并且始终命名为 *dwContext*。

分配给特定 Internet 对象的上下文仅用于标识对象成员中的对象导致的活动 `OnStatusCallback` `CInternetSession` 。 对的调用会 `OnStatusCallback` 接收多个参数; 这些参数一起工作，告诉您的应用程序对哪个事务和连接进行了何种进度。

创建 `CInternetSession` 对象时，可以为构造函数指定 *dwContext* 参数。 `CInternetSession` 本身不使用上下文 ID;相反，它将上的上下文 ID 传递到任何 **InternetConnection** 派生的对象，这些对象不会显式获取自己的上下文 id。 反过来， `CInternetConnection` `CInternetFile` 如果未显式指定不同的上下文 id，则这些对象会将上下文 ID 连同它们所创建的对象一起传递给它们。 另一方面，如果你确实指定了自己的特定上下文 ID，则该对象及其执行的所有工作都将与该上下文 ID 相关联。 可以使用上下文 Id 来识别函数中提供的状态信息 `OnStatusCallback` 。

## <a name="display-progress-information-while-transferring-files"></a><a name="_core_display_progress_information_while_transferring_files"></a> 传输文件时显示进度信息

例如，如果您编写一个应用程序，该应用程序创建一个与 FTP 服务器的连接以读取文件并连接到 HTTP 服务器以获取网页，则您将获得一个 `CInternetSession` 对象， (两个对象都是一个，另一个则 `CInternetConnection` `CFtpSession` 是 `CHttpSession`) ，两个 `CInternetFile` 对象 (每个连接) 两个对象。 如果你使用了 *dwContext* 参数的默认值，则将无法区分 `OnStatusCallback` 指示 FTP 连接的进度的调用和指示 HTTP 连接进度的调用。 如果你指定 *dwContext* ID，你稍后可以在中对其进行测试 `OnStatusCallback` ，你将知道哪个操作生成了回调。

## <a name="see-also"></a>请参阅

[MFC Internet 编程基础知识](../mfc/mfc-internet-programming-basics.md)<br/>
[ (WinInet) 的 Win32 Internet 扩展 ](../mfc/win32-internet-extensions-wininet.md)
