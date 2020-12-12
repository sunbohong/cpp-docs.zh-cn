---
description: 了解详细信息：演练：创建 Image-Processing 网络
title: 演练：创建图像处理网络
ms.date: 04/25/2019
helpviewer_keywords:
- image-processing networks, creating [Concurrency Runtime]
- creating image-processing networks [Concurrency Runtime]
ms.assetid: 78ccadc9-5ce2-46cc-bd62-ce0f99d356b8
ms.openlocfilehash: 1cdd94d6cad6ee76c02b7eb2cf8b4ca38a53fa96
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97169302"
---
# <a name="walkthrough-creating-an-image-processing-network"></a>演练：创建图像处理网络

本文档演示如何创建执行图像处理的异步消息块网络。

网络根据其特征确定要对映像执行哪些操作。 此示例使用 *数据流* 模型通过网络来路由图像。 在数据流模型中，程序的独立组件之间通过发送消息进行通信。 当组件收到消息时，它可以执行某些操作，然后将该操作的结果传递到另一个组件。 将此与 *控制流* 模型进行比较，在此模型中，应用程序使用控制结构（例如，条件语句、循环等）控制程序中操作的顺序。

基于数据流的网络创建任务 *管道* 。 管道的每个阶段都同时执行整个任务的一部分。 这就好比是汽车制造装配线。 每辆车通过组装行时，一个工作站组装帧，另一个站安装引擎，依此类推。 通过启用多个车辆同时进行组合，程序集线提供的吞吐量比一次组装一个完整车辆提供更好的吞吐量。

## <a name="prerequisites"></a>先决条件

在开始本演练之前，请阅读以下文档：

- [异步消息块](../../parallel/concrt/asynchronous-message-blocks.md)

- [如何：使用消息块筛选器](../../parallel/concrt/how-to-use-a-message-block-filter.md)

- [演练：创建数据流代理](../../parallel/concrt/walkthrough-creating-a-dataflow-agent.md)

在开始本演练之前，我们还建议你了解 GDI + 的基本知识。

## <a name="sections"></a><a name="top"></a> 个

本演练包含以下各节：

- [定义图像处理功能](#functionality)

- [创建图像处理网络](#network)

- [完整示例](#complete)

## <a name="defining-image-processing-functionality"></a><a name="functionality"></a> 定义图像处理功能

本部分介绍图像处理网络用于处理从磁盘读取的图像的支持函数。

以下函数 `GetRGB` 和 `MakeColor` 分别提取和合并给定颜色的各个组件。

[!code-cpp[concrt-image-processing-filter#2](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_1.cpp)]

以下函数 `ProcessImage` 调用给定的 [std：： function](../../standard-library/function-class.md) 对象，以转换 gdi + [位图](/windows/win32/api/gdiplusheaders/nl-gdiplusheaders-bitmap) 对象中每个像素的颜色值。 `ProcessImage`函数使用[concurrency：:p arallel_for](reference/concurrency-namespace-functions.md#parallel_for)算法并行处理位图的每一行。

[!code-cpp[concrt-image-processing-filter#3](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_2.cpp)]

以下函数（ `Grayscale` 、、 `Sepiatone` `ColorMask` 和 `Darken` ）调用 `ProcessImage` 函数来转换对象中每个像素的颜色值 `Bitmap` 。 其中每个函数都使用 lambda 表达式来定义一个像素的颜色转换。

[!code-cpp[concrt-image-processing-filter#4](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_3.cpp)]

下面的函数 `GetColorDominance` 还调用 `ProcessImage` 函数。 但是，此函数不会更改每个颜色的值，而是使用 [concurrency：：可组合](../../parallel/concrt/reference/combinable-class.md) 对象计算红色、绿色或蓝色分量是否支配图像。

[!code-cpp[concrt-image-processing-filter#5](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_4.cpp)]

下面的函数 `GetEncoderClsid` 检索编码器的给定 MIME 类型的类标识符。 应用程序使用此函数检索位图的编码器。

[!code-cpp[concrt-image-processing-filter#6](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_5.cpp)]

[[顶部](#top)]

## <a name="creating-the-image-processing-network"></a><a name="network"></a> 创建图像处理网络

本部分介绍如何创建异步消息块网络，这些消息块在给定目录中的每个 JPEG ( .jpg) 图像上执行图像处理。 网络执行以下图像处理操作：

1. 对于 Tom 创作的任何图像，将转换为灰度。

1. 对于具有红色作为基准颜色的任何图像，请删除绿色和蓝色分量，然后使其变暗。

1. 对于任何其他图像，应用棕色色调。

网络仅应用与其中一个条件相匹配的第一个图像处理操作。 例如，如果图像由 Tom 创作并且具有红色作为其基准颜色，则该图像只转换为灰度。

网络执行每个图像处理操作后，会将映像作为位图保存到磁盘 () 文件。

以下步骤说明如何创建一个函数来实现此图像处理网络，并将该网络应用于给定目录中的每个 JPEG 图像。

#### <a name="to-create-the-image-processing-network"></a>创建图像处理网络

1. 创建一个函数， `ProcessImages` 该函数采用磁盘上的目录的名称。

   [!code-cpp[concrt-image-processing-filter#7](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_6.cpp)]

1. 在 `ProcessImages` 函数中，创建一个 `countdown_event` 变量。 `countdown_event`此演练稍后将演示类。

   [!code-cpp[concrt-image-processing-filter#8](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_7.cpp)]

1. 创建一个 [std：： map](../../standard-library/map-class.md) 对象，该对象将 `Bitmap` 对象与其原始文件名关联。

   [!code-cpp[concrt-image-processing-filter#9](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_8.cpp)]

1. 添加以下代码以定义图像处理网络的成员。

   [!code-cpp[concrt-image-processing-filter#10](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_9.cpp)]

1. 添加以下代码以连接到网络。

   [!code-cpp[concrt-image-processing-filter#11](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_10.cpp)]

1. 添加以下代码，以将目录中每个 JPEG 文件的完整路径发送到网络的开头。

   [!code-cpp[concrt-image-processing-filter#12](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_11.cpp)]

1. 等待 `countdown_event` 变量达到零。

   [!code-cpp[concrt-image-processing-filter#13](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_12.cpp)]

下表描述了网络的成员。

|成员|描述|
|------------|-----------------|
|`load_bitmap`|一个 [concurrency：：变压器](../../parallel/concrt/reference/transformer-class.md) 对象，它 `Bitmap` 从磁盘加载对象，并向对象添加一个条目， `map` 以将该图像与其原始文件名关联。|
|`loaded_bitmaps`|[Concurrency：： unbounded_buffer](reference/unbounded-buffer-class.md)对象，它将加载的图像发送到图像处理筛选器。|
|`grayscale`|一个 `transformer` 对象，它将由 Tom 创作的图像转换为灰度。 它使用图像的元数据来确定其作者。|
|`colormask`|一个 `transformer` 对象，该对象从红色作为主导色的图像中删除绿色和蓝色组件。|
|`darken`|一个 `transformer` 对象，它使具有红色的图像变暗为主导色。|
|`sepiatone`|一个 `transformer` 对象，该对象将棕褐色调应用于不是由 Tom 创作的图像，而不是主要的红色。|
|`save_bitmap`|将 `transformer` 处理的保存到磁盘的对象保存 `image` 为位图。 `save_bitmap` 从对象中检索原始文件名 `map` ，并将其文件扩展名更改为 .bmp。|
|`delete_bitmap`|`transformer`释放图像内存的对象。|
|`decrement`|一个 [concurrency：： call](../../parallel/concrt/reference/call-class.md) 对象，充当网络中的终端节点。 它会递减 `countdown_event` 对象，以向主应用程序发送图像已处理的信号。|

`loaded_bitmaps`消息缓冲区很重要，因为作为 `unbounded_buffer` 对象，它将对象提供 `Bitmap` 给多个接收方。 当目标块接受对象时 `Bitmap` ，该 `unbounded_buffer` 对象不会 `Bitmap` 为任何其他目标提供该对象。 因此，将对象链接到对象的顺序非常 `unbounded_buffer` 重要。 `grayscale`、 `colormask` 和 `sepiatone` 消息块均使用筛选器来仅接受某些 `Bitmap` 对象。 `decrement`消息缓冲区是消息缓冲区的重要目标， `loaded_bitmaps` 因为它接受 `Bitmap` 其他消息缓冲区拒绝的所有对象。 `unbounded_buffer`需要对象才能按顺序传播消息。 因此，在将 `unbounded_buffer` 新的目标块链接到该目标块之前，对象将被阻止，并且如果当前目标块未接受该消息，则接受该消息。

如果你的应用程序需要多个消息块处理消息，而不是只使用第一条接受消息的消息块，则可以使用另一种消息块类型，如 `overwrite_buffer` 。 `overwrite_buffer`类一次只保存一条消息，但会将该消息传播到其每个目标。

下图显示图像处理网络：

![图像处理网络](../../parallel/concrt/media/concrt_imageproc.png "图像处理网络")

`countdown_event`在此示例中，对象使图像处理网络可以在处理完所有图像后通知主应用程序。 `countdown_event`当计数器值达到零时，类使用[concurrency：： event](../../parallel/concrt/reference/event-class.md)对象进行信号。 主应用程序每次向网络发送文件名时都会递增计数器的值。 在处理每个图像后，网络的终端节点会递减计数器。 在主应用程序遍历指定的目录后，它会等待 `countdown_event` 对象通知其计数器已达到零。

下面的示例演示了 `countdown_event` 类：

[!code-cpp[concrt-image-processing-filter#14](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_13.cpp)]

[[顶部](#top)]

## <a name="the-complete-example"></a><a name="complete"></a> 完整的示例

以下代码显示完整示例。 `wmain`函数管理 GDI + 库，并调用 `ProcessImages` 函数来处理目录中的 JPEG 文件 `Sample Pictures` 。

[!code-cpp[concrt-image-processing-filter#15](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_14.cpp)]

下图显示了示例输出。 每个源图像都高于其相应的已修改映像。

![示例的示例输出](../../parallel/concrt/media/concrt_imageout.png "示例的示例输出")

`Lighthouse` 由 Tom Alphin 创作，因此转换为灰度。 `Chrysanthemum`、 `Desert` 、 `Koala` 和 `Tulips` 具有红色作为主导颜色，因此会删除蓝色和绿色颜色组件并使其变暗。 `Hydrangeas`、 `Jellyfish` 和 `Penguins` 匹配默认条件，因此为棕色 toned。

[[顶部](#top)]

### <a name="compiling-the-code"></a>编译代码

复制代码示例并将其粘贴到 Visual Studio 项目中，或粘贴到一个名为的文件中， `image-processing-network.cpp` 然后在 Visual Studio 命令提示符窗口中运行以下命令。

**cl.exe/DUNICODE/EHsc image-processing-network/link gdiplus**

## <a name="see-also"></a>请参阅

[并发运行时演练](../../parallel/concrt/concurrency-runtime-walkthroughs.md)
