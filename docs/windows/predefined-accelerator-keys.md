---
title: " (c + +) 的快捷键"
ms.date: 02/14/2019
helpviewer_keywords:
- accelerator keys
- keyboard shortcuts
- keyboard shortcuts [C++], predefined
- menus [C++], shortcut keys
- keyboard shortcuts [C++], menu association
ms.assetid: f234c5f2-4ec3-4c9e-834a-b5dd297625b9
ms.openlocfilehash: 4f838caa8ca9e4a996fa4cb8018d663c6c7aecea
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/29/2020
ms.locfileid: "91504291"
---
# <a name="accelerator-keys-c"></a> (c + +) 的快捷键

## <a name="predefined-accelerator-keys"></a>预定义快捷键

有多个预定义快捷键，它们可能是 Windows 应用程序项目的一部分。 部分虚拟键适用于 Windows 环境。 其他支持浏览器或 Unicode 应用程序。 你可以在任何快捷键中使用这些键。

|键|说明|
|---------|-----------------|
|VK_ACCEPT|) 接受 (IME|
|VK_BROWSER_BACK| (Windows) 浏览器， **后退** 键|
|VK_BROWSER_FAVORITES| (Windows) 浏览器， **收藏夹** 键|
|VK_BROWSER_FORWARD| (Windows) 浏览器， **前进** 键|
|VK_BROWSER_HOME| (Windows) Browser、 **Start** 和 **Home** 键|
|VK_BROWSER_REFRESH| (Windows) 浏览器， **刷新** 键|
|VK_BROWSER_SEARCH| (Windows) Browser， **搜索** 键|
|VK_BROWSER_STOP| (Windows) 浏览器， **停止** 键|
|VK_CONVERT|) 转换 (IME|
|VK_FINAL|) 最终模式下 (IME|
|VK_HANGUEL| (IME) Hanguel 模式 (保持兼容性，请使用 VK_HANGUL) |
|VK_HANGUL|) 朝鲜语模式下的 (IME|
|VK_HANJA|) 朝鲜语汉字模式 (IME|
|VK_JUNJA| (IME) Junja 模式|
|VK_KANA| (IME) 假名模式|
|VK_KANJI| (IME) 汉字模式|
|VK_LAUNCH_APP1| (Windows) **启动应用程序 1** 键|
|VK_LAUNCH_APP2| (Windows) **启动应用程序 2** 键|
|VK_LAUNCH_MAIL| (Windows) **启动邮件** 密钥|
|VK_LAUNCH_MEDIA_SELECT| (Windows) **选择媒体** 密钥|
|VK_LCONTROL|**左 Ctrl** 键|
|VK_LMENU|**左菜单** 键|
|VK_LSHIFT|**左 Shift** 键|
|VK_MEDIA_NEXT_TRACK| (Windows) **下一曲目** 键|
|VK_MEDIA_PLAY_PAUSE| (Windows) **播放/暂停媒体** 密钥|
|VK_MEDIA_PREV_TRACK| (Windows) **上一个曲目** 键|
|VK_MEDIA_STOP| (Windows) **停止媒体** 密钥|
|VK_MODECHANGE| (IME) 模式更改请求|
|VK_NONCONVERT| (IME) nonconvert|
|VK_OEM_1| (美国标准键盘的 Windows) ，则 **为;：** 键|
|VK_OEM_102| (Windows) RT 102 键键盘上的尖括号键或反斜杠键|
|VK_OEM_2|为美国标准键盘 (Windows) ， **/？** key|
|VK_OEM_3| (美国标准键盘的 Windows) ， **`~** 键|
|VK_OEM_4| (美国标准键盘的 Windows) ， **[{** key|
|VK_OEM_5| (美国标准键盘的 Windows) ， ** \\&#124;** 键|
|VK_OEM_6| (美国标准键盘的 Windows) ，则为 **]}** 键|
|VK_OEM_7| (美国标准键盘的 Windows) ，"单引号/双引号" 键|
|VK_OEM_COMMA| (适用于任何国家/地区的 Windows) ， **，** 密钥|
|VK_OEM_MINUS| (适用于任何国家/地区的 Windows) ， **-** 密钥|
|VK_OEM_PERIOD| (适用于任何国家/地区的 Windows) ， **。** key|
|VK_OEM_PLUS| (适用于任何国家/地区的 Windows) ， **+** 密钥|
|VK_PACKET| (Windows) 用于将 Unicode 字符作为击键传递。|
|VK_RCONTROL|**右 Ctrl** 键|
|VK_RMENU|**右菜单** 键|
|VK_RSHIFT|**右移** 键|
|VK_SLEEP|**计算机睡眠** 键|
|VK_VOLUME_DOWN| (Windows) **音量降低** 键|
|VK_VOLUME_MUTE| (Windows) **音量静音** 键|
|VK_VOLUME_UP| (Windows) **Volume Up** 键|
|VK_XBUTTON1| (Windows) **X1** 鼠标按钮|
|VK_XBUTTON2| (Windows) **X2** 鼠标按钮|

## <a name="accelerator-key-association"></a>加速键关联

很多时候，你希望某一菜单项和某一键盘组合可以发出相同的程序命令。 要执行此操作，可将)  (ID 的相同资源标识符分配给菜单项，并分配给应用程序的快捷键对应表中的条目。 接着你可以编辑该菜单项的标题，以显示快捷键的名称。 有关菜单项和快捷键的详细信息，请参阅 [菜单命令](./menu-command-properties.md)。

## <a name="requirements"></a>要求

Win32

## <a name="see-also"></a>请参阅

[快捷键编辑器](../windows/accelerator-editor.md)<br/>
