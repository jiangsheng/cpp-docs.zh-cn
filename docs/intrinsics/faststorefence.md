---
title: "__faststorefence | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__faststorefence_cpp"
  - "__faststorefence"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__faststorefence intrinsic"
  - "sfence instruction"
ms.assetid: 6c6eb973-3cf0-4306-b3af-cfde9b0210a5
caps.latest.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 16
---
# __faststorefence
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 专用**  
  
 保证每个以前的内存引用（包括加载和存储内存引用）在任何后续的内存引用之前全局可见。  
  
## 语法  
  
```  
void __faststorefence();  
```  
  
## 要求  
  
|内部函数|体系结构|  
|----------|----------|  
|`__faststorefence`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **头文件** \<intrin.h\>  
  
## 备注  
 生成完整的内存屏障指令序列，以保证在此内部函数之前发出的加载和存储操作在执行继续之前全局可见。  效果相当于所有 x64 平台上的 `_mm_mfence` 内部函数，但是速度更快。  
  
 在 AMD64 平台上，此例程会生成一个指令，该指令是比 `sfence` 指令更快的存储隔离。  对于时间关键型代码，仅在 AMD64 平台上使用此内部函数而不是 `_mm_sfence`。  在 Intel x64 平台上，`_mm_sfence` 指令速度更快。  
  
 此例程仅可用作内部函数。  
  
## 结束 Microsoft 专用  
  
## 请参阅  
 [编译器内部函数](../intrinsics/compiler-intrinsics.md)