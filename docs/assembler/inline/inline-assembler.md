---
title: "内联汇编程序 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- assembler [C++]
- assembler [C++], inline
- assembly language [C++], inline
- inline assembler [C++]
- inline assembly [C++]
ms.assetid: 7e13f18f-3628-4306-8b81-4a6d09c043fe
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 22f428a21af037b86e063261003baf9849357c9e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2017
---
# <a name="inline-assembler"></a>内联汇编程序
**Microsoft 专用**  
  
 汇编语言用作多种用途，例如提高程序的速度，减少内存需求和控制硬件。 使用内联汇编程序，在没有额外汇编程序和链接步骤的情况下，也可直接在您的 C 和 C++ 源程序中嵌入汇编语言指令。 内联汇编程序生成到该编译器中，因此您不需要一个单独的汇编程序，例如 Microsoft Macro Assembler (MASM)。  
  
> [!NOTE]
>  具有内联汇编代码的程序不能完全移植到其他硬件平台。 如果要针对可移植性进行设计，请避免使用内联汇编程序。  
  
 ARM 和 [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] 处理器不支持内联汇编程序。  以下主题解释如何使用具有 x86 处理器的可视 Visual C/C++ 内联汇编：  
  
-   [内联汇编概述](../../assembler/inline/inline-assembler-overview.md)  
  
-   [内联程序集的优点](../../assembler/inline/advantages-of-inline-assembly.md)  
  
-   [__asm](../../assembler/inline/asm.md)  
  
-   [在 __asm 块中使用汇编语言](../../assembler/inline/using-assembly-language-in-asm-blocks.md)  
  
-   [在 __asm 块中使用 C 或 C++](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md)  
  
-   [在内联汇编程序中使用和保留寄存器](../../assembler/inline/using-and-preserving-registers-in-inline-assembly.md)  
  
-   [跳转到内联程序集中的标签](../../assembler/inline/jumping-to-labels-in-inline-assembly.md)  
  
-   [在内联程序集内调用 C 函数](../../assembler/inline/calling-c-functions-in-inline-assembly.md)  
  
-   [在内联程序集内调用 C++ 函数](../../assembler/inline/calling-cpp-functions-in-inline-assembly.md)  
  
-   [将 __asm 块定义为 C 宏](../../assembler/inline/defining-asm-blocks-as-c-macros.md)  
  
-   [优化内联程序集](../../assembler/inline/optimizing-inline-assembly.md)  
  
 **结束 Microsoft 专用**  
  
## <a name="see-also"></a>另请参阅  
 [编译器内部函数和程序集语言](../../intrinsics/compiler-intrinsics-and-assembly-language.md)   
 [C++ 语言参考](../../cpp/cpp-language-reference.md)