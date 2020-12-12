---
description: 了解详细信息：预定义规则
title: 预定义的规则
ms.date: 11/04/2016
helpviewer_keywords:
- rules, predefined
- NMAKE program, predefined rules
- predefined rules in NMAKE
ms.assetid: 638cdc3f-4aba-4b4f-96e3-ad65b0364f12
ms.openlocfilehash: 302c649980050764d1bb2f0e9a43b785d0175a09
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97225825"
---
# <a name="predefined-rules"></a>预定义的规则

预定义的推理规则使用 NMAKE 提供的命令和选项宏。

|规则|命令|默认<br /><br /> action|Batch<br /><br /> 规则|平台 nmake 运行于|
|----------|-------------|------------------------|--------------------|----------------------------|
|.asm.exe|$ (如) $ (AFLAGS) $<|ml $<|否|x86|
|.asm .obj|$ (AS) $ (AFLAGS) /c $<|ml/c $<|是|x86|
|.asm.exe|$ (如) $ (AFLAGS) $<|ml64.exe $<|否|X64|
|.asm .obj|$ (AS) $ (AFLAGS) /c $<|ml64.exe/c $<|是|X64|
|.c.exe|$ (CC) $ (CFLAGS) $<|cl $<|否|全部|
|.c .obj|$ (CC) $ (CFLAGS) /c $<|cl/c $<|是|全部|
|.cc.exe|$ (CC) $ (CFLAGS) $<|cl $<|否|全部|
|.obj .obj|$ (CC) $ (CFLAGS) /c $<|cl/c $<|是|全部|
|.cpp.exe|$ (CPP) $ (CPPFLAGS) $<|cl $<|否|全部|
|.cpp .obj|$ (CPP) $ (CPPFLAGS) /c $<|cl/c $<|是|全部|
|.cxx.exe|$ (.CXX) $ (CXXFLAGS) $<|cl $<|否|全部|
|. .cxx|$ (.CXX) $ (CXXFLAGS) /c $<|cl/c $<|是|全部|
|.rc .res|$ (RC) $ (RFLAGS) /r $<|rc/r $<|否|全部|

## <a name="see-also"></a>请参阅

[推理规则](inference-rules.md)
