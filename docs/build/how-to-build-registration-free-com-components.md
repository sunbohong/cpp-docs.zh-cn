---
description: 详细了解：操作说明：生成免注册的 COM 组件
title: 如何：生成免注册的 COM 组件
ms.date: 11/04/2016
helpviewer_keywords:
- COM components, registration-free
ms.assetid: 7e585d6a-0314-45b2-8f1b-cae9ac4df037
ms.openlocfilehash: ddcb378989878749d170705b4808d8302523a73a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97162711"
---
# <a name="how-to-build-registration-free-com-components"></a>如何：生成免注册的 COM 组件

免注册的 COM 组件是在 DLL 中内置了清单的 COM 组件。

### <a name="to-build-manifests-into-com-components"></a>将清单生成到 COM 组件中

1. 打开 COM 组件的项目属性页。

1. 展开“配置属性”节点，然后展开“清单工具”节点   。

1. 选择“输入和输出”属性页，然后将“嵌入清单”属性设置为“是”    。

1. 单击 **“确定”** 。

1. 生成解决方案。

## <a name="see-also"></a>请参阅

[如何：生成独立应用程序以使用 COM 组件](how-to-build-isolated-applications-to-consume-com-components.md)
