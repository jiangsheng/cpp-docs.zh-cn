---
title: "编译器错误 C3196 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3196
dev_langs: C++
helpviewer_keywords: C3196
ms.assetid: d9c38a13-191d-472d-aa2b-f61a6459d16c
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: c7425abce554427aafa1443d4a5cc6828deefef8
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3196"></a>编译器错误 C3196
keyword： 使用多个一次  
  
 不止一次使用的关键字。  
  
 下面的示例生成 C3196:  
  
```  
// C3196.cpp  
// compile with: /clr  
ref struct R abstract abstract {};   // C3196  
ref struct S abstract {};   // OK  
```