---
title: 保留字
ms.date: 11/04/2016
f1_keywords:
- code
- CONFORMING
- DISCARDABLE
- Description
- base
- APPLOADER
- Data
- DYNAMIC
- DEV386
helpviewer_keywords:
- .def files [C++], reserved words
- def files [C++], reserved words
- linker [C++], reserved words
- reserved words [C++]
ms.assetid: 9b9f49e5-0739-45ab-a37e-81e3915ceb25
ms.openlocfilehash: 62893d4af1633bc2c89d2d6a0fa71309a0411ad5
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/25/2020
ms.locfileid: "88836837"
---
# <a name="reserved-words"></a>保留字

链接器保留以下单词。 仅当名称括在双引号中时，才可以将这些名称用作 [module 定义语句](module-definition-dot-def-files.md) 中的参数 ( "" ) 。

:::row:::
   :::column span="":::
      **`APPLOADER`**<sup>2</sup>\
      **`BASE`**\
      **`CODE`**\
      **`CONFORMING`**\
      **`DATA`**\
      **`DESCRIPTION`**\
      **`DEV386`**\
      **`DISCARDABLE`**\
      **`DYNAMIC`**\
      **`EXECUTE-ONLY`**\
      **`EXECUTEONLY`**\
      **`EXECUTEREAD`**\
      **`EXETYPE`**\
      **`EXPORTS`**\
      `FIXED`<sup>1</sup>
   :::column-end:::
   :::column span="":::
      **`FUNCTIONS`**<sup>pps-2</sup>\
      **`HEAPSIZE`**\
      **`IMPORTS`**\
      **`IMPURE`**<sup>2</sup>\
      **`INCLUDE`**<sup>pps-2</sup>\
      **`INITINSTANCE`**<sup>pps-2</sup>\
      **`IOPL`**\
      **`LIBRARY`**<sup>2</sup>\
      **`LOADONCALL`**<sup>2</sup>\
      **`LONGNAMES`**<sup>pps-2</sup>\
      **`MOVABLE`**<sup>2</sup>\
      **`MOVEABLE`**<sup>2</sup>\
      **`MULTIPLE`**\
      **`NAME`**\
      `NEWFILES`<sup>2</sup>
   :::column-end:::
   :::column span="":::
      **`NODATA`**<sup>2</sup>\
      **`NOIOPL`**<sup>2</sup>\
      **`NONAME`**\
      **`NONCONFORMING`**<sup>2</sup>\
      **`NONDISCARDABLE`**\
      **`NONE`**\
      **`NONSHARED`**\
      **`NOTWINDOWCOMPAT`**<sup>2</sup>\
      **`OBJECTS`**\
      **`OLD`**<sup>2</sup>\
      **`PRELOAD`**\
      **`PRIVATE`**\
      **`PROTMODE`**<sup>pps-2</sup>\
      **`PURE`**<sup>2</sup>\
      **`READONLY`**
   :::column-end:::
   :::column span="":::
      **`READWRITE`**\
      **`REALMODE`**<sup>2</sup>\
      **`RESIDENT`**\
      **`RESIDENTNAME`**<sup>2</sup>\
      **`SECTIONS`**\
      **`SEGMENTS`**\
      **`SHARED`**\
      **`SINGLE`**\
      **`STACKSIZE`**\
      **`STUB`**\
      **`VERSION`**\
      **`WINDOWAPI`**\
      **`WINDOWCOMPAT`**\
      **`WINDOWS`**
   :::column-end:::
:::row-end:::

<sup>1</sup> 链接器在遇到此字词时发出警告 ( "已忽略" ) 。 但仍保留该单词。

<sup>2</sup> 链接器忽略此词，但不发出警告。

## <a name="see-also"></a>另请参阅

- [MSVC 链接器参考](linking.md)
- [MSVC 链接器选项](linker-options.md)
