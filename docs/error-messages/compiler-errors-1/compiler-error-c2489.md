---
title: "编译器错误 C2489 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2489
dev_langs:
- C++
helpviewer_keywords:
- C2489
ms.assetid: 67d8cd98-db7e-4f7f-86b4-4af7bc89ec8b
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 697f64be4ee5ef0b38af6d8a027b9032f38d3db6
ms.contentlocale: zh-cn
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2489"></a>编译器错误 C2489
identifier： 初始化函数范围中函数中不允许 naked 的自动或注册变量  
  
 有关详细信息，请参阅[裸](../../cpp/naked-cpp.md)。  
  
 下面的示例生成 C2489:  
  
```  
// C2489.cpp  
// processor: x86  
__declspec( naked ) int func() {  
   int i = 1;   // C2489  
   register int j = 1;   // C2489  
}  
```
