---
title: "编译器错误 C2196 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2196
dev_langs: C++
helpviewer_keywords: C2196
ms.assetid: fd2f6a58-48ce-4e58-96f8-e37720feb8e7
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: b40e086c530d63fab6762f8b79d87e987c35226d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2196"></a>编译器错误 C2196
case 值“value”已使用。  
  
 Switch 语句不止一次使用相同的 case 值。  
  
 下面的示例生成 C2196：  
  
```  
// C2196.cpp  
int main() {  
   int i = 0;  
   switch( i ) {  
   case 0:  
      break;  
   case 0:   // C2196  
   // try the following line instead  
   // case 1:  
      break;  
   }  
}  
```