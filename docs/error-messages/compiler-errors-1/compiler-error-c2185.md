---
title: "编译器错误 C2185 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2185"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2185"
ms.assetid: 74bc9f64-7b4c-4735-ba13-67c43f8c47db
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 编译器错误 C2185
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

“identifier”: 非法基分配  
  
 寄存器变量或自动（局部）变量被声明为 `__based`。  只有全局变量才能声明为 `__based`。