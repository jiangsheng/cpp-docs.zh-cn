---
title: "编译器错误 C2243 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2243
dev_langs:
- C++
helpviewer_keywords:
- C2243
ms.assetid: b90065bb-d251-4ba9-8b4c-280ee13fa9c0
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: d9725239c7e7b8899c23584aa56d26ed77bd757a
ms.contentlocale: zh-cn
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2243"></a>编译器错误 C2243
存在从“类型 1”到“类型 2”的“转换类型”转换，但不可访问  
  
 访问保护（`protected` 或 `private`）已禁止从指向派生类的指针转换为指向基类的指针。  
  
 下面的示例生成 C2243：  
  
```  
// C2243.cpp  
// compile with: /c  
class B {};  
class D : private B {};  
class E : public B {};  
  
D d;  
B *p = &d;   // C2243  
  
E e;  
B *p2 = &e;  
```  
  
 派生类的客户端不能访问具有 `protected` 或 `private` 访问权限的基类。 这些级别的访问控制用于指示基类是对客户端不可见的实现细节。 如果你希望派生类的客户端有权访问派生类指针到基类指针的隐式转换，请使用公共派生。
