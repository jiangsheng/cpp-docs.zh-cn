---
title: "编译器错误 C2436 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2436
dev_langs: C++
helpviewer_keywords: C2436
ms.assetid: ca4cc813-bc1d-4c0a-9a2c-3a5fe673d084
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: ca7f9a160675009e1462b1e7c5c1b110180e10c5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2436"></a>编译器错误 C2436
identifier： 成员函数或构造函数初始值设定项列表中的嵌套的类  
  
 无法初始化成员函数或构造函数初始值设定项列表中的本地类。  
  
 下面的示例生成 C2436:  
  
```  
// C2436.cpp  
struct S{  
   int f();  
   struct Inner{  
      int i;  
   };  
   S():f(10), Inner(0){}   // C2436  
};  
```