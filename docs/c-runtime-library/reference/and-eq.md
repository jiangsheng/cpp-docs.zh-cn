---
title: "and_eq | Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
apitype: DLLExport
f1_keywords:
- and_eq
- std.and_eq
- std::and_eq
dev_langs: C++
helpviewer_keywords: and_eq macro
ms.assetid: 11091772-e359-4c2b-95c6-00841ac04354
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 9314242e8251c1cecb246fa7ee9f47e270b7a97c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2017
---
# <a name="andeq"></a>and_eq
&= 运算符的替代项。  
  
## <a name="syntax"></a>语法  
  
```  
  
#define and_eq &=  
  
```  
  
## <a name="remarks"></a>备注  
 该宏产生运算符 &=。  
  
## <a name="example"></a>示例  
  
```  
// iso646_and_eq.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <iso646.h>  
  
int main( )  
{  
   using namespace std;  
   int a = 3, b = 2, result;  
  
   result= a &= b;  
   cout << result << endl;  
  
   result= a and_eq b;  
   cout << result << endl;  
}  
```  
  
```Output  
2  
2  
```  
  
## <a name="requirements"></a>要求  
 **标头：** \<iso646.h>