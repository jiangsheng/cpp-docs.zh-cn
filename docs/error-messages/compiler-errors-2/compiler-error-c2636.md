---
title: "编译器错误 C2636 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2636
dev_langs:
- C++
helpviewer_keywords:
- C2636
ms.assetid: 379873ec-8d05-49f8-adf1-b067bc07bdb8
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: b9aa491ec27c59a6fdc336a9ab148806e468a4aa
ms.contentlocale: zh-cn
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2636"></a>编译器错误 C2636
identifier： 指向引用成员的指针是非法的  
  
 未声明指向引用成员的指针。  
  
 下面的示例生成 C2636:  
  
```  
// C2636.cpp  
struct S {};  
int main() {  
   int &S::*prs;   // C2636  
   int S::*prs1;   // OK  
   int *S::*prs2;   // OK  
}  
```
