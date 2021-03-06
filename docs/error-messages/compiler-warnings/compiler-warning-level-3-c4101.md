---
title: "编译器警告 （等级 3） C4101 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4101
dev_langs: C++
helpviewer_keywords: C4101
ms.assetid: d98563cd-9dce-4aae-8f12-bd552a4ea677
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: edd99402978a41a115afa2d96f86abd63d72afa4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-3-c4101"></a>编译器警告 （等级 3） C4101
identifier： 未引用的本地变量  
  
 永远不会使用的本地变量。 明显的情况下将出现此警告：  
  
```  
// C4101a.cpp  
// compile with: /W3  
int main() {  
int i;   // C4101  
}  
```  
  
 但是，此警告将在调用时也发生**静态**通过类的实例的成员函数：  
  
```  
// C4101b.cpp  
// compile with:  /W3  
struct S {  
   static int func()  
   {  
      return 1;  
   }  
};  
  
int main() {  
   S si;   // C4101, si is never used  
   int y = si.func();  
   return y;  
}  
```  
  
 在此情况下，编译器所使用的有关的信息`si`访问**静态**函数，但类的实例时不需要调用**静态**函数; 因此警告。 若要解决此警告，你可以：  
  
-   添加一个构造函数，编译器将在其中使用的实例`si`对的调用中`func`。  
  
-   删除**静态**关键字的定义从`func`。  
  
-   调用**静态**函数显式： `int y = S::func();`。