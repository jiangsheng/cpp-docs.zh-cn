---
title: "编译器错误 C2422 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2422
dev_langs:
- C++
helpviewer_keywords:
- C2422
ms.assetid: ef0ec302-4028-4778-b134-0b8cea4bcad9
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 65412576c3c1a5e6b8205652d826d0eca6d222e6
ms.contentlocale: zh-cn
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2422"></a>编译器错误 C2422
操作数中的非法段重写  
  
 内联程序集代码错误地使用操作数段重写运算符 （冒号）。  可能的原因包括：  
  
-   该运算符前面寄存器不段寄存器。  
  
-   该运算符前面寄存器不是操作数中的唯一段寄存器。  
  
-   段重写运算符将显示在间接寻址运算符 （括号）。  
  
-   跟后面段重写运算符的表达式不是即时操作数或内存操作数。  
  
 下面的示例生成 C2422:  
  
```  
// C2422.cpp  
// processor: x86  
int main() {  
   _asm {  
      mov AX, [BX:ES]   // C2422  
      mov AX, ES   // OK  
   }  
}  
```
