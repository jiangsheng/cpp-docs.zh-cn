---
title: "编译器错误 C3421 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3421
dev_langs: C++
helpviewer_keywords: C3421
ms.assetid: b52050c6-17a4-424a-8894-337b0cec7010
caps.latest.revision: "3"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: c70d062f90410f6af170af45e8213c65777d3977
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3421"></a>编译器错误 C3421
“type”: 由于该类的终结器不可访问或不存在，因此无法调用它  
  
 终结器属于隐式专用，因此无法从其封闭类型外调用它。  
  
 有关详细信息，请参阅[析构函数和终结器中如何： 定义和使用类和结构 (C + + /cli CLI)](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers)。  
  
## <a name="example"></a>示例  
 下面的示例生成 C3421。  
  
```  
// C3421.cpp  
// compile with: /clr  
ref class A {};  
  
ref class B {   
   !B() {}  
  
public:  
   ~B() {}  
};  
  
int main() {  
   A a;  
   a.!A();   // C3421  
  
   B b;  
   b.!B();   // C3421  
}  
```