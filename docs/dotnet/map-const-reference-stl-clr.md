---
title: "map:: const_reference (STL/CLR) |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::map::const_reference
dev_langs: C++
helpviewer_keywords: const_reference member [STL/CLR]
ms.assetid: 0b343e23-7f8d-46d3-876f-f1ec86776110
caps.latest.revision: "14"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: cea39eae9e7dc18d354ab3d8f80a1b1412e81769
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2017
---
# <a name="mapconstreference-stlclr"></a>map::const_reference (STL/CLR)
元素的常量引用的类型。  
  
## <a name="syntax"></a>语法  
  
```  
typedef value_type% const_reference;  
```  
  
## <a name="remarks"></a>备注  
 该类型描述元素的常量引用。  
  
## <a name="example"></a>示例  
  
```  
// cliext_map_const_reference.cpp   
// compile with: /clr   
#include <cliext/map>   
  
typedef cliext::map<wchar_t, int> Mymap;   
int main()   
    {   
    Mymap c1;   
    c1.insert(Mymap::make_value(L'a', 1));   
    c1.insert(Mymap::make_value(L'b', 2));   
    c1.insert(Mymap::make_value(L'c', 3));   
  
// display contents " [a 1] [b 2] [c 3]"   
    Mymap::const_iterator cit = c1.begin();   
    for (; cit != c1.end(); ++cit)   
        {   // get a const reference to an element   
        Mymap::const_reference cref = *cit;   
        System::Console::Write(" [{0} {1}]", cref->first, cref->second);   
        }   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
[a 1] [b 2] [c 3]  
```  
  
## <a name="requirements"></a>要求  
 **标头：** \<cliext/映射 >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>另请参阅  
 [映射 (STL/CLR)](../dotnet/map-stl-clr.md)   
 [map:: reference (STL/CLR)](../dotnet/map-reference-stl-clr.md)   
 [map::value_type (STL/CLR)](../dotnet/map-value-type-stl-clr.md)