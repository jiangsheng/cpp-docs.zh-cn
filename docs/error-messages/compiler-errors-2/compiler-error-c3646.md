---
title: "编译器错误 C3646 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3646
dev_langs:
- C++
helpviewer_keywords:
- C3646
ms.assetid: 4391ead2-9637-4ca3-aeda-5a991b18d66d
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 0bc9b2601a57e2be98c3a356cbd2ede69dc7be79
ms.contentlocale: zh-cn
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3646"></a>编译器错误 C3646
specifier： 未知的重写说明符  
  
 编译器在其中它需要查找重写说明符，但令牌不由编译器识别出的位置中找到一个令牌。  
  
 有关详细信息，请参阅[重写说明符](../../windows/override-specifiers-cpp-component-extensions.md)。  
  
 下面的示例生成 C3646:  
  
```  
// C3646.cpp  
// compile with: /clr /c  
ref class C {  
   void f() unknown;   // C3646  
   // try the following line instead  
   // virtual void f() abstract;  
};  
```
