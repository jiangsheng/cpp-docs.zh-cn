---
title: "编译器错误 C3032 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3032
dev_langs:
- C++
helpviewer_keywords:
- C3032
ms.assetid: 6a92bd8e-319f-4a99-aef4-a9021f6f9928
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 2bc15f7f1989a7cec11506a445b985fa6e863ba2
ms.contentlocale: zh-cn
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3032"></a>编译器错误 C3032
“var”: “clause”子句中的变量不能是不完整的“类型”类型  
  
 传递给某些子句的类型必须对编译器完全可见。  
  
 下面的示例生成 C3032:  
  
```  
// C3032.cpp  
// compile with: /openmp /link vcomps.lib  
#include "omp.h"  
  
struct Incomplete;  
extern struct Incomplete inc;  
  
int main() {  
   int i = 9;  
   #pragma omp parallel private(inc)   // C3032  
      ;  
  
   #pragma omp parallel private(i)     // OK  
      ;  
  
}  
```
