---
title: "编译器错误 C2256 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2256
dev_langs:
- C++
helpviewer_keywords:
- C2256
ms.assetid: 171fa2bc-8c72-49cd-afe5-d723b7acd3c5
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 54802178136f02d0b334203ebcedf020942f0ed9
ms.contentlocale: zh-cn
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2256"></a>编译器错误 C2256
function 上的友元说明符非法使用  
  
 析构函数或构造函数不能指定为[友元](../../cpp/friend-cpp.md)。  
  
 下面的示例生成 C2256:  
  
```  
// C2256.cpp  
// compile with: /c  
class C {  
public:  
   friend ~C();   // C2256  
   ~C();   // OK  
};  
```
