---
title: "编译器错误 C2213 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2213
dev_langs: C++
helpviewer_keywords: C2213
ms.assetid: ff012278-7f3b-4d49-aaed-2349756f6225
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: adfe94d1285ba0f237077820909ac955a5a65953
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2213"></a>编译器错误 C2213
modifier： 非法的自变量以 __based  
  
 自变量修改`__based`无效。  
  
 下面的示例生成 C2213:  
  
```  
// C2213.cpp  
// compile with: /c  
int i;  
int *j;  
char __based(i) *p;   // C2213  
char __based(j) *p2;   // OK  
```