---
title: "编译器错误 C2792 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2792
dev_langs: C++
helpviewer_keywords: C2792
ms.assetid: 392cf748-4f5e-4e62-a364-3118d5658408
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 16a07fcc43ffde40a4ac540d3e5dbaa8891ea48e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2792"></a>编译器错误 C2792
super： 此关键字的后面必须跟::  
  
 可以按照关键字的唯一令牌`__super`是`::`。  
  
 下面的示例生成 C2792:  
  
```  
// C2792.cpp  
struct B {  
   void mf();  
};  
  
struct D : B {  
   void mf() {  
      __super.();   // C2792  
  
      // try the following line instead  
      // __super::mf();  
   }  
};  
```