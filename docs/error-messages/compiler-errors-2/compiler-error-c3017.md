---
title: "编译器错误 C3017 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3017
dev_langs: C++
helpviewer_keywords: C3017
ms.assetid: 12ab2c2a-d0d2-4900-9cbf-39be0af590dd
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: a575db4ea80c4939722cc89124fd69742f96b4f2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3017"></a>编译器错误 C3017
OpenMP“for”语句中的终止测试格式不正确  
  
 必须完全或显式指定 OpenMP 语句中的 `for` 循环。  
  
 下面的示例生成 C3017：  
  
```  
// C3017.cpp  
// compile with: /openmp  
int main()  
{  
   int i = 0, j = 10;  
  
   #pragma omp parallel  
   {  
      #pragma omp for  
      for (i = 0; i; ++i)   // C3017  
      // Try the following line instead:  
      // for (i = 0; i < 10; ++i)  
         ;  
   }  
}  
```