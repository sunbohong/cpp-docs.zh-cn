---
title: /kernel（创建内核模式二进制）
description: Microsoft C/c + + 编译器/kernel 选项用于构建和链接内核模式执行的项目。
ms.date: 09/28/2020
f1_keywords:
- /kernel
- /kernel-
ms.assetid: 6d7fdff0-c3d1-4b78-9367-4da588ce8b05
ms.openlocfilehash: 8a8c02a6f102a52afbc52c154ce215ede3f38f74
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/29/2020
ms.locfileid: "91509350"
---
# <a name="kernel-create-kernel-mode-binary"></a>/kernel（创建内核模式二进制）

创建可在 Windows 内核中执行的二进制文件。 当前项目中的代码通过使用一组特定于在内核模式下运行的代码的简单 c + + 语言功能进行编译和链接。

## <a name="syntax"></a>语法

> **`/kernel`**

## <a name="remarks"></a>备注

指定 **`/kernel`** 选项将告知编译器和链接器对在内核模式下允许的语言功能进行仲裁，并确保您有足够的表现力能力，以避免对内核模式 c + + 唯一的运行时不稳定。 这是通过禁止使用在内核模式下中断的 c + + 语言功能来实现的。 编译器会为可能会中断但无法禁用的 c + + 语言功能生成警告。

**`/kernel`** 选项适用于生成的编译器和链接器阶段，并在项目级别设置。 传递开关，以 **`/kernel`** 指示编译器在链接后应将生成的二进制文件加载到 Windows 内核中。 编译器会将 C++ 语言功能的范围缩小为与内核兼容的子集。

下表列出了在指定时编译器行为中的更改 **`/kernel`** 。

| 行为类型 | **`/kernel`** 操作 |
|--|--|
| C++ 异常处理 | 已禁用。 **`throw`** **`try`** 除) 异常规范外，和关键字的所有实例都会发出编译器错误 (`throw()` 。 **`/EH`** 除了之外，没有与兼容的选项 **`/kernel`** **`/EH-`** 。 |
| RTTI | 已禁用。 **`dynamic_cast`** **`typeid`** 除非静态使用，否则和关键字的所有实例都会发出编译器错误 **`dynamic_cast`** 。 |
| `new` 和 `delete` | 必须显式定义 `new()` or `delete()` 运算符。 编译器和运行时不提供默认定义。 |

使用选项时，允许使用自定义调用约定、 [`/GS`](gs-buffer-security-check.md) 生成选项和所有优化 **`/kernel`** 。 内联很大程度上不受影响 **`/kernel`** ，但编译器遵循相同的语义。 如果要确保 **`__forceinline`** 内联限定符是有效的，则必须确保启用了警告 [C4714](../../error-messages/compiler-warnings/compiler-warning-level-4-c4714.md) ，以便了解特定 **`__forceinline`** 函数何时不内联。

没有 `#pragma` 等效项来控制此选项。

当编译器传递到开关时 **`/kernel`** ，它将预定义一个名为的预处理器宏，其 `_KERNEL_MODE` 值为 **1**。 您可以使用此宏根据执行环境是处于用户模式还是内核模式下按条件编译代码。 例如，下面的代码指定在 `MyNonPagedClass` 为内核模式执行进行编译时，该类应位于不可分页的内存段中。

```cpp
#ifdef _KERNEL_MODE
#define NONPAGESECTION __declspec(code_seg("$kerneltext$"))
#else
#define NONPAGESECTION
#endif

class NONPAGESECTION MyNonPagedClass
{
   // ...
};
```

以下目标体系结构和选项的一些组合 **`/arch`** 会在与一起使用时产生错误 **`/kernel`** ：

- **`/arch:SSE`****`/arch:SSE2`** **`/arch:AVX`** **`/arch:AVX2`** x86 不支持、、、和 **`/arch:AVX512`** 。 **`/arch:IA32`** X86 上仅支持 **`/kernel`** 。

- **`/arch:AVX`****`/arch:AVX2`** **`/arch:AVX512`** x64 上不支持、和 **`/kernel`** 。

生成时 **`/kernel`** 也会传递 **`/kernel`** 到链接器。 下面是该选项对链接器行为的影响：

- 禁用了增量链接。 如果将添加 **`/incremental`** 到命令行，链接器会发出此错误：

   **错误 LNK1295： "/INCREMENTAL" 与 "/KERNEL" 规范不兼容;不带 "/INCREMENTAL" 的链接**

- 链接器将检查每个对象文件 (或静态库中包含的任何存档成员) ，以查看它是否可以通过使用选项进行编译，但不是 **`/kernel`** 。 如果任何实例都满足此标准，链接器仍然会成功链接，但可能发出警告，如下表所示。

   | Command | **`/kernel`** obj | 非 **`/kernel`** obj、MASM obj 或 cvtres obj | 混合的 **`/kernel`** 和非 **`/kernel`** obj |
   |--|--|--|--|
   | **`link /kernel`** | 是 | 是 | 是，但出现警告 LNK4257 |
   | **`link`** | 是 | 是 | 是 |

   **未用/KERNEL 编译的 LNK4257 链接对象;映像可能无法运行**

**`/kernel`** 选项和 **`/driver`** 选项独立运行。 它们不会有任何影响。

### <a name="to-set-the-kernel-compiler-option-in-visual-studio"></a>在 Visual Studio 中设置 /kernel 编译器选项

1. 打开项目的“属性页”  对话框。 有关详细信息，请参阅[在 Visual Studio 中设置 C++ 编译器和生成属性](../working-with-project-properties.md)。

1. 选择 "**配置属性**" "  >  **c/c + +**  >  **命令行**" 属性页。

1. 在 " **附加选项** " 框中，添加 *`/kernel`* 。 选择 **"确定" 或 "** **应用** " 保存更改。

## <a name="see-also"></a>请参阅

[MSVC 编译器选项](compiler-options.md)\
[MSVC 编译器命令行语法](compiler-command-line-syntax.md)
