---
title: "编译器错误 C2574 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2574"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2574"
ms.assetid: 3e1c5c18-ee8b-4dbb-bfc0-d3b8991af71b
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# 编译器错误 C2574
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

“destructor”: 不能声明为静态的  
  
 析构函数和构造函数都不能声明为 `static`。  
  
 下面的示例生成 C2574：  
  
```  
// C2574.cpp  
// compile with: /c  
class A {  
   virtual static ~A();   // C2574  
   //  try the following line instead  
   // virtual ~A();  
};  
```