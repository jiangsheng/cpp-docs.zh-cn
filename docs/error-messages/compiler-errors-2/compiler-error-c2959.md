---
title: "编译器错误 C2959 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2959
dev_langs:
- C++
helpviewer_keywords:
- C2959
ms.assetid: d66bb2a8-70c3-4209-a358-b0c47f111a50
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 45f0625bd8f7352d6311fad507b1ee5e71a4da1a
ms.contentlocale: zh-cn
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2959"></a>编译器错误 C2959
泛型类或函数可能不是模板的成员  
  
 有关详细信息，请参阅[Windows 运行时和托管模板](../../windows/windows-runtime-and-managed-templates-cpp-component-extensions.md)和[泛型](../../windows/generics-cpp-component-extensions.md)。  
  
## <a name="example"></a>示例  
 下面的示例生成 C2959。  
  
```  
// C2959.cpp  
// compile with: /clr /c  
template <class T> ref struct S {  
   generic <class U> ref struct GR1;   // C2959  
};  
```
