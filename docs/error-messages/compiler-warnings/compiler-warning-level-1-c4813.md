---
title: "编译器警告 （等级 1） C4813 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4813
dev_langs:
- C++
helpviewer_keywords:
- C4813
ms.assetid: c30bf877-ab04-4fe4-897e-8162092426f0
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 30a288d4ed32d8908a41c8eeef5f5c2aca2b34c9
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-level-1-c4813"></a>编译器警告（等级 1）C4813
“function”：局部类的友元函数必须之前已经声明  
  
 内部类中的友元函数未在外部类中声明。  
  
 以下示例生成 C4813：  
  
```  
// C4813.cpp  
// compile with: /W1 /LD  
void MyClass()  
{  
   // void func();  
   class InnerClass  
   {  
      friend void func();   // C4813 uncomment declaration above  
   };  
}  
```
