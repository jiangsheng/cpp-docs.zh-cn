---
title: "编译器错误 C2847 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2847
dev_langs:
- C++
helpviewer_keywords:
- C2847
ms.assetid: 9ad9a0e0-8b16-49d9-a5be-f8eda2372aa9
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 8406ea786def9c3241a0ae1de8743d53e91f96cd
ms.contentlocale: zh-cn
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2847"></a>编译器错误 C2847
无法将 sizeof 应用到托管或 WinRT 类型“类”  
  
 [Sizeof](../../cpp/sizeof-operator.md)运算符可在编译时获取对象的值。 由于托管或 WinRT 类的大小、接口或值类型是动态的，因此在编译时无法得知。  
  
 例如，以下示例生成 C2847：  
  
```  
// C2847.cpp  
// compile with: /clr  
ref class A {};  
  
int main() {  
   A ^ xA = gcnew A;  
   sizeof(*xA);   // C2847 cannot use sizeof on managed object  
}  
```  

