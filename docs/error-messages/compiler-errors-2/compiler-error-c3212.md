---
title: "编译器错误 C3212 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3212
dev_langs: C++
helpviewer_keywords: C3212
ms.assetid: 9e271bb6-a51f-4b96-b26b-9f4ca28fca0a
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: e7534a3a05366eb866c67c500ed946d838732e95
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3212"></a>编译器错误 C3212
“specialization”：模板成员的显式专用化必须是显示专用化的成员  
  
 显式专用化的格式不正确。  
  
 以下示例生成 C3212：  
  
```  
// C3212.cpp  
// compile with: /LD  
template <class T>  
struct S {  
   template <class T1>  
   struct S1;  
};  
  
template <class T>   // C3212  
template <>  
struct S<T>::S1<int> {};  
  
/*  
// try the following instead  
template <>  
template <>  
struct S<int>::S1<int> {};  
*/  
  
/*  
// or, the following  
template <>  
struct S<int> {  
   template <class T1>  
   struct S1;  
};  
  
template <>  
struct S<int>::S1<int> {  
};  
*/  
```