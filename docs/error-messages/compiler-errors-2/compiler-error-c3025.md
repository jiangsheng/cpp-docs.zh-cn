---
title: "编译器错误 C3025 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3025
dev_langs: C++
helpviewer_keywords: C3025
ms.assetid: 4442f5a3-d9ea-4873-b1fb-e7e5bd3cbe5e
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 96211bf47a286a6de9a59042749b8aa2f9a3292f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3025"></a>编译器错误 C3025
“clause”：应为整型表达式  
  
 子句需要整型表达式，但提供了非整型表达式。  
  
## <a name="example"></a>示例  
 下面的示例生成 C3025。  
  
```  
// C3025.cpp  
// compile with: /openmp /link vcomps.lib  
#include <stdio.h>  
#include "omp.h"  
  
float f = 2.0F;  
  
int main()   
{  
    int i = 0;  
  
    // OK  
    puts("Test with int");  
    #pragma omp parallel for num_threads(i)  
    for (i = 1; i <= 2; ++i)  
        printf_s("Hello World - thread %d - iteration %d\n",  
                 omp_get_thread_num(), i);  
  
    puts("Test with float");  
    #pragma omp parallel for num_threads(f)   // C3025  
    for (i = 1; i <= 2; ++i)  
        printf_s("Hello World - thread %d - iteration %d\n",  
                 omp_get_thread_num(), i);  
}  
```