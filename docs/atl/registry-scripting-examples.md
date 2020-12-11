---
description: 了解更多：注册表脚本示例
title: 注册表脚本示例
ms.date: 11/04/2016
helpviewer_keywords:
- scripting, examples
- registrar scripts [ATL]
- scripts, Registrar scripts
- registry, Registrar
ms.assetid: b6df80e1-e08b-40ee-9243-9b381b172460
ms.openlocfilehash: 716aa69ed95c784079e72f9b785fedd8c07b0563
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97157537"
---
# <a name="registry-scripting-examples"></a>注册表脚本示例

本主题中的脚本示例演示了如何将密钥添加到系统注册表，如何注册注册器 COM 服务器，以及如何指定多个分析树。

## <a name="add-a-key-to-hkey_current_user"></a>向 HKEY_CURRENT_USER 添加密钥

以下分析树说明了一个简单的脚本，该脚本将一个键添加到系统注册表中。 具体而言，该脚本会将项添加 `MyVeryOwnKey` 到 `HKEY_CURRENT_USER` 。 它还将的默认字符串值分配 `HowGoesIt` 给新密钥：

```rgs
HKEY_CURRENT_USER
{
    'MyVeryOwnKey' = s 'HowGoesIt'
}
```

可以轻松扩展此脚本以定义多个子项，如下所示：

```rgs
HKCU
{
    'MyVeryOwnKey' = s 'HowGoesIt'
    {
        'HasASubkey'
        {
            'PrettyCool' = d '55'
            val 'ANameValue' = s 'WithANamedValue'
        }
    }
}
```

现在，该脚本会将子项添加 `HasASubkey` 到 `MyVeryOwnKey` 。 对于此子项，它会添加 `PrettyCool` 默认值为 55) 的子项 (`DWORD` ，并 `ANameValue` 使用) 字符串值 (的命名值 `WithANamedValue` 。

## <a name="register-the-registrar-com-server"></a><a name="_atl_register_the_registrar_com_server"></a> 注册注册机构 COM 服务器

下面的脚本注册注册器 COM 服务器本身。

```rgs
HKCR
{
    ATL.Registrar = s 'ATL Registrar Class'
    {
        CLSID = s '{44EC053A-400F-11D0-9DCD-00A0C90391D3}'
    }
    NoRemove CLSID
    {
        ForceRemove {44EC053A-400F-11D0-9DCD-00A0C90391D3} = s 'ATL Registrar Class'
        {
            ProgID = s 'ATL.Registrar'
            InprocServer32 = s '%MODULE%'
            {
                val ThreadingModel = s 'Apartment'
            }
        }
    }
}
```

在运行时，此分析树将 `ATL.Registrar` 键添加到中 `HKEY_CLASSES_ROOT` 。 为此新密钥，则：

- 指定 `ATL Registrar Class` 为键的默认字符串值。

- 添加 `CLSID` 为子项。

- `{44EC053A-400F-11D0-9DCD-00A0C90391D3}`为指定 `CLSID` 。  (此值是要用于的注册器 CLSID `CoCreateInstance` 。 ) 

由于 `CLSID` 是共享的，因此不应在取消注册模式下将其删除。 语句 `NoRemove CLSID` 通过指示 `CLSID` 应在注册模式下打开并在取消注册模式中忽略，来执行此。

`ForceRemove`语句提供了一项内务处理功能，方法是在重新创建密钥之前删除密钥及其所有子项。 如果子项的名称已更改，这会很有用。 在此脚本示例中， `ForceRemove` 将检查以确定是否 `{44EC053A-400F-11D0-9DCD-00A0C90391D3}` 已存在。 如果是，则 `ForceRemove` ：

- 递归删除及其 `{44EC053A-400F-11D0-9DCD-00A0C90391D3}` 所有子项。

- 重新创建 `{44EC053A-400F-11D0-9DCD-00A0C90391D3}` 。

- 添加 `ATL Registrar Class` 为的默认字符串值 `{44EC053A-400F-11D0-9DCD-00A0C90391D3}` 。

分析树现在将两个新子项添加到 `{44EC053A-400F-11D0-9DCD-00A0C90391D3}` 中。 第一个键 `ProgID` 获取作为 ProgID 的默认字符串值。 第二个键 `InprocServer32` 获取默认字符串值， `%MODULE%` 这是本文的 [使用可替换参数 (注册器的预处理器) ](../atl/using-replaceable-parameters-the-registrar-s-preprocessor.md)部分中介绍的预处理器值。 `InprocServer32` 还获取一个 `ThreadingModel` 具有字符串值的命名值 `Apartment` 。

## <a name="specify-multiple-parse-trees"></a>指定多个分析树

若要在一个脚本中指定多个分析树，只需将一个树置于另一个树的末尾即可。 例如，下面的脚本将键添加 `MyVeryOwnKey` 到和的分析树中 `HKEY_CLASSES_ROOT` `HKEY_CURRENT_USER` ：

```rgs
HKCR
{
    'MyVeryOwnKey' = s 'HowGoesIt'
}
HKEY_CURRENT_USER
{
    'MyVeryOwnKey' = s 'HowGoesIt'
}
```

> [!NOTE]
> 在注册器脚本中，4K 是最大标记大小。  (标记是语法中的任何可识别元素。 ) 在前面的脚本示例中，、、 `HKCR` `HKEY_CURRENT_USER` `'MyVeryOwnKey'` 和 `'HowGoesIt'` 都是所有标记。

## <a name="see-also"></a>请参阅

[创建注册器脚本](../atl/creating-registrar-scripts.md)
