---
title: "prev_permutation (STL/CLR) |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::prev_permutation
dev_langs: C++
helpviewer_keywords: prev_permutation function [STL/CLR]
ms.assetid: 5294dbe5-1b5f-4369-a764-067dff86d1e8
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: e2023cfda5d434fd7302c66dd1a583186cb11adb
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2017
---
# <a name="prevpermutation-stlclr"></a>prev_permutation (STL/CLR)
重新排序范围中的元素，以便使用按字典顺序的下一个更大排列（如果有）替换原有排序，其中“下一个”的意义可通过二元谓词指定。  
  
## <a name="syntax"></a>语法  
  
```  
template<class _BidIt> inline  
    bool prev_permutation(_BidIt _First, _BidIt _Last);  
template<class _BidIt, class _Pr> inline  
    bool prev_permutation(_BidIt _First, _BidIt _Last, _Pr _Pred);  
```  
  
## <a name="remarks"></a>备注  
 此函数的行为与 c + + 标准库函数相同`prev_permutation`。 有关详细信息，请参阅[prev_permutation](../standard-library/algorithm-functions.md#prev_permutation)。  
  
## <a name="requirements"></a>要求  
 **标头：** \<cliext/算法 >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>另请参阅  
 [algorithm (STL/CLR)](../dotnet/algorithm-stl-clr.md)