---
description: 了解详细信息：/ALLOWBIND
title: /ALLOWBIND
ms.date: 11/04/2016
f1_keywords:
- /allowbind_bind
helpviewer_keywords:
- ALLOWBIND editbin option
- /ALLOWBIND editbin option
- -ALLOWBIND editbin option
ms.assetid: eaadbb8c-4339-4281-9a75-3a1ce2352ff8
ms.openlocfilehash: 54f3056240537d765a9212e774a9a313ded49dab
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97179598"
---
# <a name="allowbind"></a>/ALLOWBIND

指定一个 DLL 是否可以绑定。

```

/ALLOWBIND[:NO]
```

## <a name="remarks"></a>备注

**/ALLOWBIND** 选项会在 DLL 的标头中设置一个位，指示 Bind.exe 允许绑定该图像。 当加载程序无需为每个引用的 DLL 实现变基并执行地址修正时，绑定可以使图像加载速度更快。 如果 DLL 已进行数字签名，则您可能不希望对其进行绑定，绑定使签名无效。 如果在支持 ASLR 的 Windows 版本上使用 **/DYNAMICBASE** 为映像启用了地址空间布局随机化 (ASLR) ，则绑定无效。

使用 **/ALLOWBIND： NO** 可防止 Bind.exe 绑定 DLL。

有关详细信息，请参阅 [/ALLOWBIND](allowbind-prevent-dll-binding.md) 链接器选项。

## <a name="see-also"></a>请参阅

[EDITBIN 选项](editbin-options.md)
