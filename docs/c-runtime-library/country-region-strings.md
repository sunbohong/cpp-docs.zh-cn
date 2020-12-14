---
description: 了解详细信息：国家/地区字符串
title: 国家-地区字符串
ms.date: 11/04/2016
helpviewer_keywords:
- country/region strings
ms.assetid: 5baf0ccf-0d9b-40dc-83bd-323705287930
ms.openlocfilehash: d865c3a6a8f505eea7878df379db30224511d51c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97195692"
---
# <a name="countryregion-strings"></a>Country/Region Strings

可以将国家和地区字符串与语言字符串结合使用，以便创建 `setlocale`、 `_wsetlocale`、 `_create_locale`和 `_wcreate_locale` 函数的区域设置规范。 有关各种 Windows 操作系统版本支持的国家/地区名称的列表，请参阅 [附录 A：产品行为](/openspecs/windows_protocols/ms-lcid/a9eac961-e77d-41a6-90a5-ce1a8b0cdb9c)（MS-LCID）中表的 **语言**、**位置** 和 **语言标记** 列 \[ ： Windows 语言代码标识符 (LCID) 引用。 有关枚举可用区域设置名称和相关值的代码示例，请参阅 [NLS：基于名称的 API 示例](/windows/win32/intl/nls--name-based-apis-sample)。

## <a name="additional-supported-country-and-region-strings"></a>其他受支持的国家和地区字符串

Microsoft C 运行时库实现还支持以下其他国家/地区字符串和缩写：

|国家/地区字符串|缩写|等效区域设置名称|
|----------------------------|------------------|----------------------------|
|america|美国|en-US|
|britain|GBR|en-GB|
|china|CHN|zh-CN|
|捷克|CZE|cs-CZ|
|england|GBR|en-GB|
|great britain|GBR|en-GB|
|holland|NLD|nl-NL|
|hong-kong|HKG|zh-HK|
|new-zealand|NZL|en-NZ|
|nz|NZL|en-NZ|
|pr china|CHN|zh-CN|
|pr-china|CHN|zh-CN|
|puerto-rico|PRI|es-PR|
|斯洛伐克|SVK|sk-SK|
|south africa|ZAF|af-ZA|
|south korea|KOR|ko-KR|
|south-africa|ZAF|af-ZA|
|south-korea|KOR|ko-KR|
|trinidad & tobago|TTO|en-TT|
|uk|GBR|en-GB|
|united-kingdom|GBR|en-GB|
|united-states|美国|en-US|
|us|美国|en-US|

## <a name="see-also"></a>请参阅

[区域设置名称、语言和国家/地区字符串](../c-runtime-library/locale-names-languages-and-country-region-strings.md)<br/>
[语言字符串](../c-runtime-library/language-strings.md)<br/>
[setlocale、_wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)<br/>
[_create_locale、_wcreate_locale](../c-runtime-library/reference/create-locale-wcreate-locale.md)
