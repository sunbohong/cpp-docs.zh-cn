---
description: '了解有关以下内容的详细信息：/NOLOGO (取消)  (链接器的启动标题) '
title: /NOLOGO（取消显示启动版权标志）（链接器）
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.SuppressStartupBanner
- /nologo
helpviewer_keywords:
- suppress startup banner linker option
- -NOLOGO linker option
- /NOLOGO linker option
- copyright message
- version numbers, preventing linker display
- banners, suppressing startup
- NOLOGO linker option
ms.assetid: 3b20dddd-eca6-4545-a331-9f70bf720197
ms.openlocfilehash: 48edea691e254f0754d29ab5ea4d8055221c4b69
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97196550"
---
# <a name="nologo-suppress-startup-banner-linker"></a>/NOLOGO（取消显示启动版权标志）（链接器）

```
/NOLOGO
```

## <a name="remarks"></a>备注

/NOLOGO 选项禁止显示版权消息和版本号。

此选项还会取消命令文件的回显。 有关详细信息，请参阅 [链接命令文件](linking.md)。

默认情况下，链接器会将此信息发送到 "输出" 窗口。 在命令行中，将其发送到标准输出，并可重定向到文件。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此链接器选项

1. 此选项只能在命令行中使用。

### <a name="to-set-this-linker-option-programmatically"></a>以编程方式设置此链接器选项

1. 不能以编程方式更改此链接器选项。

## <a name="see-also"></a>请参阅

[MSVC 链接器参考](linking.md)<br/>
[MSVC 链接器选项](linker-options.md)
