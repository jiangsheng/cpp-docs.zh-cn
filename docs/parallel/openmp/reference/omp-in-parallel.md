---
title: "omp_in_parallel | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "omp_in_parallel"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "omp_in_parallel OpenMP function"
ms.assetid: 1f01a1b4-78c5-496a-afb7-a43ecdad83d6
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# omp_in_parallel
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

返回非零，则调用从并行区域内。  
  
## 语法  
  
```  
int omp_in_parallel( );  
```  
  
## 备注  
 有关更多信息，请参见 [3.1.6 omp\_in\_parallel Function](../../../parallel/openmp/3-1-6-omp-in-parallel-function.md)。  
  
## 示例  
  
```  
// omp_in_parallel.cpp  
// compile with: /openmp  
#include <stdio.h>  
#include <omp.h>  
  
int main( )   
{  
    omp_set_num_threads(4);  
    printf_s("%d\n", omp_in_parallel( ));  
  
    #pragma omp parallel  
        #pragma omp master  
        {  
            printf_s("%d\n", omp_in_parallel( ));  
        }  
}  
```  
  
  **0**  
**1**   
## 请参阅  
 [Functions](../../../parallel/openmp/reference/openmp-functions.md)