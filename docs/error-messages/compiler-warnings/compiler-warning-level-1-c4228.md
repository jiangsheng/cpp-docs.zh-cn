---
title: "编译器警告（等级 1）C4228 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4228"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4228"
ms.assetid: 9301d660-d601-464e-83f5-7ed844a3c6dc
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 编译器警告（等级 1）C4228
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

使用了非标准扩展 : 忽略声明符列表中逗号后面的限定符  
  
 声明变量时在逗号后面使用诸如 **const** 或 `volatile` 的限定符是一种 Microsoft 扩展 \([\/Ze](../../build/reference/za-ze-disable-language-extensions.md)\)。  
  
## 示例  
  
```  
// C4228.cpp  
// compile with: /W1  
int j, const i = 0;  // C4228  
int k;  
int const m = 0;  // ok  
int main()  
{  
}  
```