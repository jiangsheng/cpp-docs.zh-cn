---
title: "编译器错误 C3833 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3833
dev_langs:
- C++
helpviewer_keywords:
- C3833
ms.assetid: 8152be53-e01e-48cd-9eef-9de38723664c
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 54fcbe6fff8efca4ffc3dd6c5791fc706eaa1191
ms.contentlocale: zh-cn
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3833"></a>编译器错误 C3833
type: pointer_type 的目标类型无效  
  
 [Interior_ptr](../../windows/interior-ptr-cpp-cli.md)或[pin_ptr](../../windows/pin-ptr-cpp-cli.md)未正确声明。  
  
 下面的示例生成 C3833:  
  
```  
// C3833.cpp  
// compile with: /clr  
  
ref class MyClass {  
public:  
   int data;  
   MyClass() : data(35) {}  
};  
  
int main() {  
   interior_ptr<MyClass> p;   // C3833  
  
   // OK  
   MyClass ^ h_MyClass = gcnew MyClass;  
   interior_ptr<int> i = &(h_MyClass->data);  
   System::Console::WriteLine(*i);  
}  
```  
  
 下面的示例生成 C3833:  
  
```  
// C3833b.cpp  
// compile with: /clr /c  
ref class G {  
public:  
   int i;  
};  
  
int main() {  
   G ^ pG = gcnew G;  
   pin_ptr<G> ppG = &pG;   // C3833 can't pin a whole object  
  
   // OK  
   pin_ptr<int> ppG2 = &pG->i;  
   *ppG2 = 54;  
   int * pi = ppG2;  
   System::Console::WriteLine(*pi);  
   System::Console::WriteLine(*ppG2);  
  
   *pi = 55;  
   System::Console::WriteLine(*pi);  
   System::Console::WriteLine(*ppG2);  
  
   *ppG2 = 56;  
   System::Console::WriteLine(*pi);  
   System::Console::WriteLine(*ppG2);  
}  
```
