---
title: "编译器错误 C2891 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2891
dev_langs:
- C++
helpviewer_keywords:
- C2891
ms.assetid: e12cfb2d-df45-4b0d-b155-c51d17e812fa
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 6c35294472fe4142e7e6689adfc5f5f71c27b664
ms.contentlocale: zh-cn
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2891"></a>编译器错误 C2891
parameter： 不能采用一个模板参数的地址  
  
 不能采用一个模板参数的地址，除非它是左值。 类型参数不是左值，因为它们没有任何地址。 非类型值都不是左值的模板参数列表中还没有一个地址。 这是代码的导致编译器错误 C2891 示例，因为作为模板参数传递的值是代码的编译器生成的复制的模板自变量。  
  
```  
template <int i> int* f() { return &i; }  
```  
  
 都是左值，如引用类型的模板参数可以具有其采用地址。  
  
```  
template <int& r> int* f() { return &r; }  
```  
  
 若要更正此错误，不会模板参数的地址除非它是左值。
