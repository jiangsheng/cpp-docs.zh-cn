---
title: "2.6.6 ordered 构造 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 5b3c1ba5-cfb8-4b05-865b-f446ae1c9f7c
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 690db7cbc03e9aa9a3b4780dd2b115812c31f984
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2017
---
# <a name="266-ordered-construct"></a>2.6.6 ordered 构造
结构化的块以下**排序**迭代将执行顺序循环中的顺序执行指令。 语法**排序**指令是，如下所示：  
  
```  
#pragma omp ordered new-linestructured-block  
```  
  
 **排序**指令必须在动态程度**为**或**为并行**构造。 **为**或**为并行**指令到**排序**构造绑定必须具有**排序**子句指定中所述[部分 2.4.1](../../parallel/openmp/2-4-1-for-construct.md)第 11 页上。 在执行**为**或**并行的**采用构造**排序**子句，**排序**严格在执行构造将在循环的顺序执行过程中执行的顺序。  
  
 限制到**排序**指令如下所示：  
  
-   使用循环的迭代**为**构造不能执行相同的有序的指令不止一次，并且必须执行多个**排序**指令。