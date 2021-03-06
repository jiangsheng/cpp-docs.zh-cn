---
title: "编译器错误 C2600 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2600
dev_langs:
- C++
helpviewer_keywords:
- C2600
ms.assetid: cce11943-ea01-4bee-a7b0-b67d24ec6493
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 1fe5383e17212b21c11394c6b987e92aacbe637e
ms.contentlocale: zh-cn
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2600"></a>编译器错误 C2600
function： 不能定义 （必须在声明类第一次） 的编译器生成的特殊成员函数  
  
 在为类定义成员函数（如构造函数或析构函数）之前，必须在类中声明它们。 如果没有在类中声明，则编译器会生成默认的构造函数和析构函数（称为特殊成员函数）。 但是，如果在类中定义这些函数中没有匹配声明的函数，则编译器将检测到冲突。  
  
 若要修复此错误，请在类声明中，声明你在类声明以外定义的每个成员函数。  
  
 以下示例生成 C2600：  
  
```  
// C2600.cpp  
// compile with: /c  
class C {};  
C::~C() {}   // C2600  
  
class D {  
   D::~D();  
};  
  
D::~D() {}  
```
