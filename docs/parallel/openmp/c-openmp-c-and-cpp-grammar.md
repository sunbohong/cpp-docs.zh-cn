---
description: 了解详细信息： .C C 和 c + + 语法
title: C. OpenMP C 和 C++ 语法
ms.date: 01/16/2019
ms.assetid: 97a878ce-1533-47f7-a134-66fcbff48524
ms.openlocfilehash: 9543d721afbff1069b5497ba8dc7092089a1b706
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97342499"
---
# <a name="c-openmp-c-and-c-grammar"></a>C. OpenMP C 和 C++ 语法

[C.1 表示法](#c1-notation)<br/>
[C.2 规则](#c2-rules)

## <a name="c1-notation"></a>C.1 表示法

语法规则包含非终端的名称，后跟一个冒号，再后跟单独行的替换替代项。

句法表达式字词<sub>opt</sub> 指示该字词在替换中是可选的。

语法表达式 *术语*<sub>optseq</sub> 等效于 *术语-seq*<sub>opt</sub> ，并具有以下附加规则：

*字词-seq*：  
&nbsp;&nbsp;&nbsp;&nbsp;*二项式*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*字词-seq* *项*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*字词-seq* `,`*术语*   

## <a name="c2-rules"></a>C.2 规则

C 标准的6.1 节中介绍了该表示法。 此语法附录显示 OpenMP C 和 c + + 指令的基本语言语法扩展。

**/\* c + + (ISO/IEC 14882:1998) \*/**

*语句-seq*：<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*statement*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*openmp 指令*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*语句-seq 语句*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*语句-seq openmp-指令*

**/\* in C90 (ISO/IEC 9899:1990) \*/**

statement-list  ：<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*statement*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*openmp 指令*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*语句-list 语句*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*语句列表 openmp-指令*

**/\* in C99 (ISO/IEC 9899:1999) \*/**

*块项*：<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*declaration*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*statement*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*openmp 指令*

**/\* 标准语句 \*/**

*statement*：<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*openmp 构造*

*openmp 构造*：<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*并行构造*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*for 构造*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*节-构造*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*单构造*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*并行构造*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*并行节-构造*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*master 构造*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*关键构造*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*原子构造*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*顺序构造*

*openmp 指令*：<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*关卡-指令*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*flush 指令*

*结构化块*：<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*statement*

*并行构造*：<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*并行指令结构化块*

*并行指令*：<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `# pragma omp parallel`*并行子句*<sub>optseq</sub> 

*并行子句*：<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*unique 并行子句*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*data 子句*

*unique 并行子句*：<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `if (`*表达式*   `)`<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `num_threads (`*表达式*   `)`

*构造*：<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*for 指令迭代语句*

*对于-指令*：<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `# pragma omp for`<sub>optseq</sub> *新行*

*for 子句*：<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*unique-子句*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*data 子句*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `nowait`

*unique-子句*：<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `ordered`<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `schedule (`*计划种类*   `)`<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `schedule (`*计划种类* `,`*表达式*      `)`

*计划类型*：<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `static`<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `dynamic`<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `guided`<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `runtime`

*节-构造*：<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*节-指令部分-范围*

*节-指令*：<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `# pragma omp sections`*sections 子句*<sub>optseq</sub> 

*sections 子句*：<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*data 子句*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `nowait`

*部分范围*：<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*{section 顺序}*

*节顺序*：<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*节指令*<sub>opt</sub> *结构化块*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*节序列部分-指令结构化块*

*部分指令*：<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `# pragma omp section`*新行*

*单构造*：<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*单指令结构化块*

*单指令*：<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `# pragma omp single`*单子句*<sub>optseq</sub> 

*单子句*：<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*data 子句*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `nowait`

*并行构造*：<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*并行指令迭代语句*

*并行指令*：<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `# pragma omp parallel for`*并行子句*<sub>optseq</sub> *新行*

*并行子句*：<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*unique 并行子句*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*unique-子句*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*data 子句*

*并行节-构造*：<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*并行节-指令部分-范围*

*并行节-指令*：<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `# pragma omp parallel sections`*并行节-子句*<sub>optseq</sub> 

*并行节子句*：<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*unique 并行子句*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*data 子句*

*主构造*：<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*主指令结构化块*

*master-指令*：<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `# pragma omp master`*新行*

*关键结构*：<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*关键指令结构化块*

*关键指令*：<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `# pragma omp critical`*区域短语*<sub>可选</sub>*新行*

*区域短语*：<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*(标识符)*

*关卡-指令*：<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `# pragma omp barrier`*新行*

*原子构造*：<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*原子指令表达式语句*

*原子指令*：<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `# pragma omp atomic`*新行*

*刷新指令*：<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `# pragma omp flush`*刷新-var*<sub>可选</sub>*新行*

*flush*：<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*(变量-列表)*

*顺序构造*：<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*有序指令结构化块*

*有序指令*：<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `# pragma omp ordered`*新行*

**/\* 标准声明 \*/**

*declaration*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*threadprivate-指令*

*threadprivate*：<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `# pragma omp threadprivate (`*变量列表* `)`*新行*    

*数据子句*：<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `private (`*变量列表*   `)`<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `copyprivate (`  *变量列表*    `)`<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `firstprivate (`  *变量列表*    `)`<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `lastprivate (`*变量列表*    `)`<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `shared (`*变量列表*   `)`<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `default ( shared )`<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `default ( none )`<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `reduction (`  *缩减运算符* `:`*变量列表*          `)`<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `copyin (`  *变量列表*    `)`

*缩减运算符*：<br/>
&nbsp;&nbsp;&nbsp;&nbsp;以下项之一：   `+ \* - & ^ | && ||`

**/\* 在 C 中 \*/**

*变量列表*：<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*identifier*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*变量列表* `,`*标识符*   

**/\* c + + \*/**

*变量列表*：<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*id-表达式*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*变量列表* `,`*id-表达式*   
