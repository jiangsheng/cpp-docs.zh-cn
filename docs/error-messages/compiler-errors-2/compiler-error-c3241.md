---
title: "编译器错误 C3241 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3241
dev_langs:
- C++
helpviewer_keywords:
- C3241
ms.assetid: 2ca14879-bba0-4a23-b22a-72cfff92d6a4
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: f704b466edc30fe3960ef0e2cedebad692015531
ms.contentlocale: zh-cn
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3241"></a>编译器错误 C3241
method： 引入了此方法不由 interface  
  
 显式重写函数，函数签名必须与要重写的函数的声明完全匹配。  
  
 下面的示例生成 C3241:  
  
```  
// C3241.cpp  
#pragma warning(disable:4199)  
  
__interface IX12A {  
   void mf();  
};  
  
__interface IX12B {  
   void mf(int);  
};  
  
class CX12 : public IX12A, public IX12B { // C3241  
   void IX12A::mf(int);  
};  
```
