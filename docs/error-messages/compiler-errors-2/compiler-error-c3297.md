---
title: "编译器错误 C3297 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3297
dev_langs: C++
helpviewer_keywords: C3297
ms.assetid: 2a718b4c-6cdb-4418-92c0-fc3a259431c4
caps.latest.revision: "3"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: c2190bb4f2fe5c6195221deebe5b24097b614691
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3297"></a>编译器错误 C3297
“constraint_2”：不能使用“constraint_1”作为约束，因为“constraint_1”具有值约束  
  
 值类已密封。 如果约束是值类，则永远无法从它派生其他约束。  
  
 有关详细信息，请参阅[泛型类型参数的约束 (C + + /cli CLI)](../../windows/constraints-on-generic-type-parameters-cpp-cli.md)。  
  
## <a name="example"></a>示例  
 下面的示例生成 C3297。  
  
```  
// C3297.cpp  
// compile with: /clr /c  
generic<class T, class U>  
where T : value class  
where U : T   // C3297  
public ref struct R {};  
```