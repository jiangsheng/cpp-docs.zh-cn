---
title: "编译器错误 C2310 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2310
dev_langs: C++
helpviewer_keywords: C2310
ms.assetid: 1969c682-b97e-43fb-b9a9-f783e7ff1710
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 526ba25418a3d61764eb2ce1fa36c1e5faea00e3
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2310"></a>编译器错误 C2310
catch 处理程序必须指定一个类型  
  
 Catch 处理程序指定任何类型或多个类型。  
  
 下面的示例生成 C2310:  
  
```  
// C2310.cpp  
// compile with: /EHsc  
#include <eh.h>  
int main() {  
   try {  
      throw "Out of memory!";  
   }  
   catch( int ,int) {}   // C2310 two types  
   // try the following line instead  
   // catch( int)  {}  
}  
```