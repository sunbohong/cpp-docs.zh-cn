---
description: 了解详细信息： iostreams 约定
title: iostreams 约定
ms.date: 11/04/2016
helpviewer_keywords:
- iostream header
- C++ Standard Library, iostreams
ms.assetid: 9fe5ded0-37a1-48d1-9671-c81ffc4760ad
ms.openlocfilehash: 3676c6aa14a5ebac1d39ed50821449caa7313e40
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97231389"
---
# <a name="iostreams-conventions"></a>iostreams 约定

iostreams 标头支持文本和编码格式间的转换，以及支持输入和输出到外部文件：

[\<fstream>](../standard-library/fstream.md)\
[\<iomanip>](../standard-library/iomanip.md)\
[\<ios>](../standard-library/ios.md)\
[\<iosfwd>](../standard-library/iosfwd.md)\
[\<iostream>](../standard-library/iostream.md)\
[\<istream>](../standard-library/istream.md)\
[\<ostream>](../standard-library/ostream.md)\
[\<sstream>](../standard-library/sstream.md)\
[\<streambuf>](../standard-library/streambuf.md)\
[\<strstream>](../standard-library/strstream.md)

最简单的 iostreams 用途只需要包含标头 [\<iostream>](../standard-library/iostream.md) 。 然后可从 [cin](../standard-library/iostream.md#cin) 或 [wcin](../standard-library/iostream.md#wcin) 提取值来读取标准输入。 其操作规则在 [basic_istream 类](../standard-library/basic-istream-class.md) 的说明中有所概述。 还可将值插入 [cout](../standard-library/iostream.md#cout) 或 [wcout](../standard-library/iostream.md#wcout) 来写入标准输出。 其操作规则在 [basic_ostream 类](../standard-library/basic-ostream-class.md) 的说明中有所概述。 提取符和插入符的常规格式控件由 [basic_ios 类](../standard-library/basic-ios-class.md) 管理。 借助提取和插入对象来处理此格式信息是多个操控程序的范围。

您可以使用在中声明的类对按名称打开的文件执行相同的 iostreams 操作 [\<fstream>](../standard-library/fstream.md) 。 若要在类的 iostreams 和对象之间转换 [Basic_string 类](../standard-library/basic-string-class.md)，请使用在中声明的类 [\<sstream>](../standard-library/sstream.md) 。 若要对 C 字符串执行相同操作，请使用中声明的类 [\<strstream>](../standard-library/strstream.md) 。

剩余标头提供支持服务，通常只与 iostreams 类的最高级用户直接相关。

## <a name="see-also"></a>请参阅

[C + + 标准库概述](../standard-library/cpp-standard-library-overview.md)\
[iostream 编程](../standard-library/iostream-programming.md)\
[C + + 标准库中的线程安全](../standard-library/thread-safety-in-the-cpp-standard-library.md)
