---
title: "omp_test_lock |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: omp_test_lock
dev_langs: C++
helpviewer_keywords: omp_test_lock OpenMP function
ms.assetid: 314ca85e-0749-4c16-800f-b0f36fed256d
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 052b552cab9d8fb0ff6b969e85a7108ca232b572
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2017
---
# <a name="omptestlock"></a>omp_test_lock
尝试设置锁，但不会阻止线程执行。  
  
## <a name="syntax"></a>语法  
  
```  
int omp_test_lock(  
   omp_lock_t *lock  
);  
```  
  
## <a name="remarks"></a>备注  
 其中，  
  
 `lock`  
 类型的变量的[omp_lock_t](../../../parallel/openmp/reference/omp-lock-t.md)初始化与[omp_init_lock](../../../parallel/openmp/reference/omp-init-lock.md)。  
  
## <a name="remarks"></a>备注  
 有关详细信息，请参阅[3.2.5 omp_test_lock 和 omp_test_nest_lock 函数](../../../parallel/openmp/3-2-5-omp-test-lock-and-omp-test-nest-lock-functions.md)。  
  
## <a name="example"></a>示例  
  
```  
// omp_test_lock.cpp  
// compile with: /openmp  
#include <stdio.h>  
#include <omp.h>  
  
omp_lock_t simple_lock;                   
  
int main() {  
    omp_init_lock(&simple_lock);  
  
    #pragma omp parallel num_threads(4)  
    {  
        int tid = omp_get_thread_num();  
  
        while (!omp_test_lock(&simple_lock))  
            printf_s("Thread %d - failed to acquire simple_lock\n",  
                     tid);  
  
        printf_s("Thread %d - acquired simple_lock\n", tid);  
  
        printf_s("Thread %d - released simple_lock\n", tid);  
        omp_unset_lock(&simple_lock);  
    }  
  
    omp_destroy_lock(&simple_lock);  
}  
```  
  
```Output  
Thread 1 - acquired simple_lock  
Thread 1 - released simple_lock  
Thread 0 - failed to acquire simple_lock  
Thread 3 - failed to acquire simple_lock  
Thread 0 - failed to acquire simple_lock  
Thread 3 - failed to acquire simple_lock  
Thread 2 - acquired simple_lock  
Thread 0 - failed to acquire simple_lock  
Thread 3 - failed to acquire simple_lock  
Thread 0 - failed to acquire simple_lock  
Thread 3 - failed to acquire simple_lock  
Thread 2 - released simple_lock  
Thread 0 - failed to acquire simple_lock  
Thread 3 - failed to acquire simple_lock  
Thread 0 - acquired simple_lock  
Thread 3 - failed to acquire simple_lock  
Thread 0 - released simple_lock  
Thread 3 - failed to acquire simple_lock  
Thread 3 - acquired simple_lock  
Thread 3 - released simple_lock  
```  
  
## <a name="see-also"></a>另请参阅  
 [函数](../../../parallel/openmp/reference/openmp-functions.md)