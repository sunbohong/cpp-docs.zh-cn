---
description: 了解更多：编译器错误 C2220
title: 编译器错误 C2220
ms.date: 11/04/2016
f1_keywords:
- C2220
helpviewer_keywords:
- C2220
ms.assetid: d610802c-64d7-40ad-a2a6-0ed0b6815a6c
ms.openlocfilehash: f45a34d0cdaa5e82c3f5e6c051126c6df4eb2005
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97245429"
---
# <a name="compiler-error-c2220"></a>编译器错误 C2220

警告被视为错误-没有生成对象文件

[/Wx](../../build/reference/compiler-option-warning-level.md) 通知编译器将所有警告视为错误。 由于发生了错误，未生成对象或可执行文件。

仅当设置了 **/wx** 标志并在编译期间出现警告时，才会出现此错误。 若要纠正此错误，必须消除项目中的每个警告。

### <a name="to-fix-use-one-of-the-following-techniques"></a>若要纠正错误，请使用以下方法之一

- 解决导致项目中出现警告的问题。

- 以较低的警告等级进行编译-例如，使用 **/W3** 而不是 **/W4**。

- 使用 [警告](../../preprocessor/warning.md) 杂注禁用或取消显示特定警告。

- 不要使用 **/wx** 进行编译。
