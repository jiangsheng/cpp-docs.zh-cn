---
title: "编译器警告 （等级 1） C4163 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4163
dev_langs:
- C++
helpviewer_keywords:
- C4163
ms.assetid: b08413fd-03fc-4f41-9167-a98976ac12f2
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 53538ee7959112e1a2cb04a727fda54d7afb995e
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-level-1-c4163"></a>编译器警告（等级 1）C4163
“identifier”：不可用作内部函数  
  
 指定的函数不能用作[内部](../../preprocessor/intrinsic.md)函数。 编译器将忽略无效的函数名称。  
  
 以下示例生成 C4163：  
  
```  
// C4163.cpp  
// compile with: /W1 /LD  
#include <math.h>  
#pragma intrinsic(mysin)   // C4163  
// try the following line instead  
// #pragma intrinsic(sin)  
```
