---
title: "编译器错误 C2835 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2835
dev_langs: C++
helpviewer_keywords: C2835
ms.assetid: 41c70630-983f-4da2-8342-513cf48b0519
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 08a09c0ea495fcaff01527b0c4af720f2a831db5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2835"></a>编译器错误 C2835
用户定义的转换 type 不采用任何形式的参数  
  
 用户定义类型转换不能采用形参。  
  
 下面的示例生成 C2835:  
  
```  
// C2835.cpp  
class A {  
public:  
   char v_char;  
  
   A() {   
      v_char = 'A';   
   };  
   operator char(char a) {   // C2835  
   // try the following line instead  
   // operator char() {     
      return v_char + 1;   
   };  
};  
  
int main() {  
   A a;  
}  
```