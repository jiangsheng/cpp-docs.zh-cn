---
title: "编译器错误 C2277 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2277
dev_langs: C++
helpviewer_keywords: C2277
ms.assetid: 15a83b07-8731-4524-810b-267f65a7844f
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 7cf9c78716e7bbb671965c7e15abb110c4064eb2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2277"></a>编译器错误 C2277
identifier： 不能采用该成员函数的地址  
  
 不能采用成员函数的地址。  
  
 下面的示例生成 C2277:  
  
```  
// C2277.cpp  
class A {  
public:  
   A();  
};  
(*pctor)() = &A::A;   // C2277   
```