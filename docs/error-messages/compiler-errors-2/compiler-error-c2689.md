---
title: "编译器错误 C2689 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2689
dev_langs:
- C++
helpviewer_keywords:
- C2689
ms.assetid: b5216fba-524d-4194-9168-26e9dc5210ce
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: faea544c9e2328521c5d302bbb2af935c94201c6
ms.contentlocale: zh-cn
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2689"></a>编译器错误 C2689
function： 友元函数不能定义内的本地类  
  
 你可以声明，但不是在本地类中定义友元函数。  
  
 下面的示例生成 C2689:  
  
```  
// C2689.cpp  
// compile with: /c  
void g() {  
   void f2();  
   class X {  
      friend void f2(){}   // C2689  
      friend void f2();   // OK  
   };  
}  
```
