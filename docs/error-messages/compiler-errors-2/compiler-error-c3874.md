---
title: "编译器错误 C3874 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3874
dev_langs: C++
helpviewer_keywords: C3874
ms.assetid: fd55fc05-69a7-4237-b3b7-dca1d5400b4f
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: cd30858e2118a7305583736c31b84ed56ab7095a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3874"></a>编译器错误 C3874
function 的返回类型应为 int 而不是 type  
  
 函数没有所需的编译器的返回类型。  
  
 下面的示例生成 C3874:  
  
```  
// C3874b.cpp  
double main()  
{   // C3874  
}  
```