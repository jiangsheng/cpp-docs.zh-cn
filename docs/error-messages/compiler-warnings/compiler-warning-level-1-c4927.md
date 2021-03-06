---
title: "编译器警告（等级 1）C4927 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4927"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4927"
ms.assetid: 7009e740-a2ef-4130-96ba-482e092f717a
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 编译器警告（等级 1）C4927
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

转换非法；隐式应用了多个用户定义的转换  
  
 多个用户定义的转换被隐式应用于单个值——编译器没有找到显式转换，但确实找到了它使用的一个转换。  
  
 下面的示例生成 C4927：  
  
```  
// C4927.cpp  
// compile with: /W1  
struct B  
{  
   operator int ()  
   {  
      return 0;  
   }  
};  
  
struct A  
{  
   A(int i)  
   {  
   }  
  
   /*  
   // uncomment this constructor to resolve  
   A(B b)  
   {  
   }  
   */  
};  
  
A f1( B& b)  
{  
   return A(b);  
}  
  
B& f2( B& b)  
{  
   return b;  
}  
  
A f()  
{  
   B b;  
   return A(b);   // ok  
   return f1(b);  // ok  
   return b;      // C4927  
   return B(b);   // C4927  
   return f2(b);  // C4927  
}  
  
int main()  
{  
   B b;  
   A a = b;  
   A a2(b);  
}  
```