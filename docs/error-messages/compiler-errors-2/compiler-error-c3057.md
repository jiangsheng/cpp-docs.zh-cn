---
title: "编译器错误 C3057 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3057
dev_langs: C++
helpviewer_keywords: C3057
ms.assetid: b0b2ba88-9c74-4bec-bf60-8fc72eade34c
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 424c4dfb224b3d0778f80148aaac11e11c9ff440
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3057"></a>编译器错误 C3057
“symbol”：当前不支持“threadprivate”符号的动态初始化  
  
 [threadprivate](../../parallel/openmp/reference/threadprivate.md) 子句中所用符号的初始化值在编译时必须已知。  
  
 以下示例生成 C3057：  
  
```  
// C3057.cpp  
// compile with: /openmp /c  
extern int f();  
int x, y = f();  
int a, b;  
#pragma omp threadprivate(x, y)   // C3057  
  
#pragma omp threadprivate(a, b)  
  
int main() {  
   // Delete the following 4 lines to resolve.  
   #pragma omp parallel copyin(x, y)  
   {  
      x = y;  
   }  
  
   #pragma omp parallel copyin(a, b)  
   {  
      a = b;  
   }  
}  
```  
  
 以下示例生成 C3057：  
  
```  
// C3057b.cpp  
// compile with: /openmp /c  
extern int Initialize();  
int main() {  
   #pragma omp parallel  
   {  
      static int var = Initialize();  
      #pragma omp threadprivate(var)   // C3057  
   }  
  
   // OK  
   #pragma omp parallel  
   {  
      static int var2;  
      static bool initialized2;  
      #pragma omp threadprivate(var2, initialized2)  
      if (!initialized2) {  
         var2 = Initialize();  
         initialized2 = true;  
      }  
   }  
}  
```