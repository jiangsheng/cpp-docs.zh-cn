---
title: "A.17   Using Nestable Locks | Microsoft Docs"
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
ms.assetid: 8ef386ed-ddc4-4d40-80aa-cc39f0fb5e4b
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# A.17   Using Nestable Locks
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

下面的示例 \(对于第 41 页\) 的 [第3.2部分](../../parallel/openmp/3-2-lock-functions.md) 演示可套上的锁如何使用同步更新到整个结构和给它的成员之一。  
  
```  
#include <omp.h>  
typedef struct {int a,b; omp_nest_lock_t lck;} pair;  
  
void incr_a(pair *p, int a)  
{  
    // Called only from incr_pair, no need to lock.  
    p->a += a;  
}  
  
void incr_b(pair *p, int b)  
{  
    // Called both from incr_pair and elsewhere,  
    // so need a nestable lock.  
  
    omp_set_nest_lock(&p->lck);  
    p->b += b;  
    omp_unset_nest_lock(&p->lck);  
}  
  
void incr_pair(pair *p, int a, int b)  
{  
    omp_set_nest_lock(&p->lck);  
    incr_a(p, a);  
    incr_b(p, b);  
    omp_unset_nest_lock(&p->lck);  
}  
  
void f(pair *p)  
{  
    extern int work1(), work2(), work3();  
    #pragma omp parallel sections  
    {  
        #pragma omp section  
            incr_pair(p, work1(), work2());  
        #pragma omp section  
            incr_b(p, work3());  
    }  
}  
```