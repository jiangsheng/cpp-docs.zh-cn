---
title: "编译器错误 C3235 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3235
dev_langs:
- C++
helpviewer_keywords:
- C3235
ms.assetid: 0554d6c7-e1dc-4c99-8934-cbcf491c8203
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 43be37f86df82117896efd51be1a69e8d7ee853a
ms.contentlocale: zh-cn
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3235"></a>编译器错误 C3235
“专用化”: 不允许显式专用化或部分专用化泛型类  
  
 泛型类不能用于显式专用化或部分专用化。  
  
## <a name="example"></a>示例  
 以下示例生成 C3235。  
  
```  
// C3235.cpp  
// compile with: /clr  
generic<class T>  
public ref class C {};  
  
generic<>  
public ref class C<int> {};   // C3235 Remove this specialization to resolve this error.  
```
