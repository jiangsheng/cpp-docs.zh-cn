---
title: "__readcr8 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__readcr8"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__readcr8 内部函数"
ms.assetid: fce16953-87ff-4fbe-8081-7962b97ae46c
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# __readcr8
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 专用**  
  
 读取 CR8 注册并返回其值。  
  
## 语法  
  
```  
unsigned __int64 __readcr8(void);  
```  
  
## 返回值  
 在 CR8 寄存器值。  
  
## 要求  
  
|内部|体系结构|  
|--------|----------|  
|`__readcr8`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **头文件** \<intrin.h\>  
  
## 备注  
 此内部只有在内核模式，并且，实例只能用作内部。  
  
## 关闭 Microsoft 特定  
  
## 请参阅  
 [编译器内部函数](../intrinsics/compiler-intrinsics.md)