---
title: "1.3 Execution Model | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 85ae8bc4-5bf0-45e0-a45f-02de9adaf716
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 1.3 Execution Model
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

OpenMP 使用并行执行分叉联接模型。  尽管分叉联接模型可用于解决各种问题，为某些对于大型基于数组的应用程序会剪裁。  OpenMP 预期要正确执行以并行编程的支持系统 \(执行多个线程，并完整的 OpenMP 支持库\) 和作为连续程序 \(指令忽略的和一个简单的 OpenMP 存根库\)。  但是，开发不正常运行，以便按顺序执行的程序可能允许。  此外，不同的并行度可能会产生不同的数值结果因数字操作关联的更改。  例如，序列化析取减少比并行断开可以将关联的一个架构。  这些不同的关联可更改浮点添加的结果。  
  
 程序编写与 OpenMP C\/C\+\+ API 开始执行，单个执行线程调用主 *线程*。  主线程在串行区域执行，直到第一个并行构造遇到。  在 OpenMP C\/C\+\+ API， **并行** 指令组合并行构造。  当并行构造遇到时，主线程创建的线程团队，这样，母版成为团队的重要信息。  在团队的每个线程执行在并行区域的动态区域的语句，只不过的工作划分构造。  必须由团队的所有线程遇到的工作划分构造的顺序，因此，在关联的中的语句构造块由一个或多个线程上执行。  关卡表示在的工作划分构造结束时，没有 `nowait` 子句由团队的所有线程上执行。  
  
 如果线程修改共享对象，则会影响不仅自己执行环境，因此，而且这些过程中的其他线程。  ，仅当对象声明为的变量，修改确保已完成，从其他线程之一的角度来看，在下面一系列点 \(如基本语言定义\)。  否则，修改确保已完成，先修改的线程，其他然后 \(或同时\) 后线程，遇到指定对象的 **刷新** 指令 \(隐式或显式\)。  请注意，当由其他 OpenMP 指令提示的 **刷新** 指令不足以保证所需排序副作用，由程序员负责提供此外，显式 **刷新** 指令。  
  
 在完成了并行构造后，在团队的线程同步。隐式障碍，因此，仅主线程继续执行。  任意数量的并行构造在单个程序可以指定。  因此，程序可以在执行时分叉和联接多次。  
  
 OpenMP C\/C\+\+ API 函数允许程序员使用指令从并行构造内。  未出现在并行构造的词法区域，但指令在该动态区域可以在调用 *隔离的* 指令。  隔离的指令使程序员能够执行其过程的大部分与顺序程序的最小更改并行。  此功能，用户可以代码并行构造过程中的顶级调用树并使用指令控件在执行任何调用的函数。  
  
 不同步调用 C 和 C\+\+ 到同一文件中写入可能导致输出不同的线程编写的数据按不确定的顺序显示的输出函数。  同样，不同步调用从同一文件读取可以读取数据按不确定的顺序的输入函数。  为 I\/O，这样的不同步使用每个线程访问不同的文件，生成结果和 I\/O 功能相同的序列化执行。