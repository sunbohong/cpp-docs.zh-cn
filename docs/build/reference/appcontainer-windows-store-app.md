---
description: '了解详细信息：/APPCONTAINER (Microsoft Store 应用) '
title: '/APPCONTAINER (UWP/Microsoft Store 应用) '
ms.date: 11/04/2016
ms.assetid: 9a432db5-7640-460b-ab18-6f61fa7daf6f
ms.openlocfilehash: 4cb78c85aa59ebd7fc0eb82af9497606bc3c431c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97179572"
---
# <a name="appcontainer-microsoft-store-app"></a>/APPCONTAINER (Microsoft Store 应用) 

指定链接器是否创建必须在应用容器中运行的可执行映像。

## <a name="syntax"></a>语法

```
/APPCONTAINER[:NO]
```

## <a name="remarks"></a>备注

默认情况下，/APPCONTAINER 为 off。

此选项修改可执行文件，以指示是否必须在 appcontainer 进程隔离环境中运行应用。 为必须在 APPCONTAINER 环境中运行的应用指定/APPCONTAINER，例如通用 Windows 平台 (UWP) 或 Windows Phone 3.x 应用。  (在使用模板创建通用 Windows 应用时，将在 Visual Studio 中自动设置选项。 ) 对于桌面应用，请指定/APPCONTAINER： NO 或仅省略选项。

Windows 8 中引入了/APPCONTAINER 选项。

### <a name="to-set-this-linker-option-in-visual-studio"></a>在 Visual Studio 中设置此链接器选项

1. 打开项目“属性页”  对话框。 有关详细信息，请参阅[在 Visual Studio 中设置 C++ 编译器和生成属性](../working-with-project-properties.md)。

1. 展开“配置属性”节点。

1. 展开“链接器”节点。

1. 选择 " **命令行** " 属性页。

1. 在 " **其他选项**" 中，输入 `/APPCONTAINER` 或 `/APPCONTAINER:NO` 。

## <a name="see-also"></a>请参阅

[MSVC 链接器参考](linking.md)<br/>
[MSVC 链接器选项](linker-options.md)
