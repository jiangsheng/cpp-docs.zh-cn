---
title: "编译器错误 C2673 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2673"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2673"
ms.assetid: 780230c0-619b-4a78-b01d-ff5886306741
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 编译器错误 C2673
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

“function”: 全局函数没有“this”指针  
  
 某全局函数尝试访问 `this`。  
  
 下面的示例生成 C2673：  
  
```  
// C2673.cpp  
int main() {  
   this = 0;   // C2673  
}  
```