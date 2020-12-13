---
description: 了解更多相关信息： Windows 套接字：数据报套接字
title: Windows 套接字：数据报套接字
ms.date: 11/04/2016
helpviewer_keywords:
- sockets [MFC], datagram
- Windows Sockets [MFC], bi-directional data flow
- datagram sockets [MFC]
- Windows Sockets [MFC], datagram
- sockets [MFC], bi-directional data flow
ms.assetid: bec16a1c-74c0-4ff9-8c18-c2d87897d264
ms.openlocfilehash: 8de374d6e96348504d4b1fc126c1607c029cd6c9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97132972"
---
# <a name="windows-sockets-datagram-sockets"></a>Windows 套接字：数据报套接字

本文介绍了数据报套接字，其中一种是可用的两种 Windows 套接字类型。  (另一种类型是 [流套接字](../mfc/windows-sockets-stream-sockets.md)。 ) 

数据报套接字支持双向数据流，此数据流不保证得到排序或无重复。 数据报也不一定是可靠的;它们可能无法送达。 数据报数据可能不按顺序到达并可能重复，但只要记录小于接收方的内部大小限制，就会保留数据中的记录边界。 你负责管理顺序和可靠性。  (的可靠性往往在本地网络 [LAN] 上很好，但在广域网 [WAN] （如 Internet）上更少。 ) 

数据报为 "无连接"，即未建立显式连接;将数据报消息发送到指定的套接字，可以从指定的套接字接收消息。

数据报套接字的一个示例是使网络上的系统时钟保持同步的应用程序。 这说明了至少部分设置中的数据报套接字的附加功能：将消息广播到大量网络地址。

数据报套接字优于面向记录的数据的流套接字。 有关数据报套接字的详细信息，请参阅 Windows SDK 中提供的 Windows 套接字规范。

## <a name="see-also"></a>请参阅

[MFC 中的 Windows 套接字](../mfc/windows-sockets-in-mfc.md)<br/>
[Windows 套接字：背景](../mfc/windows-sockets-background.md)
