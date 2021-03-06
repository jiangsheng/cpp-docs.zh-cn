---
title: "_emit Pseudoinstruction | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_emit"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_emit pseudoinstruction"
  - "字节定义（内联程序集）"
ms.assetid: 004c48f3-364c-4e82-9a51-e326f9cc7b2b
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# _emit Pseudoinstruction
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

## Microsoft 专用  
 **\_emit** 伪指令在当前文本段落的当前位置定义一个字节。  **\_emit** 伪命令类似于 MASM 的 [DB](../../assembler/masm/db.md) 指令。  
  
 以下片段将字节 0x4A、0x43 和 0x4B 放入代码中：  
  
```  
#define randasm __asm _emit 0x4A __asm _emit 0x43 __asm _emit 0x4B  
 .  
 .  
 .  
__asm {  
     randasm  
     }  
```  
  
> [!CAUTION]
>  如果 `_emit` 生成了修改寄存器的指令，并且您在编译应用程序时进行了优化，则编译器无法确定受到影响的寄存器。  例如，如果 `_emit` 生成修改 **rax** 寄存器的指令，编译器将不知道 **rax** 已更改。  在内联汇编程序代码执行后，编译器随后可能会对该寄存器中的值做出错误假设。  因此，在应用程序运行时，它可能展示出不可预知的行为。  
  
 **结束 Microsoft 专用**  
  
## 请参阅  
 [在 \_\_asm 块中使用汇编语言](../../assembler/inline/using-assembly-language-in-asm-blocks.md)