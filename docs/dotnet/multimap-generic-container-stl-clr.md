---
title: "multimap::generic_container (STL/CLR) |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::multimap::generic_container
dev_langs: C++
helpviewer_keywords: generic_container member [STL/CLR]
ms.assetid: fc7ef7a4-80b4-472f-8911-6b9950b81d6c
caps.latest.revision: "14"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 561fd0faad299ec4fd80073e678eaee65392eab2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2017
---
# <a name="multimapgenericcontainer-stlclr"></a>multimap::generic_container (STL/CLR)
容器的泛型接口的类型。  
  
## <a name="syntax"></a>语法  
  
```  
typedef Microsoft::VisualC::StlClr::  
    ITree<GKey, GValue>  
    generic_container;  
```  
  
## <a name="remarks"></a>备注  
 该类型描述此模板容器类的泛型接口。  
  
## <a name="example"></a>示例  
  
```  
// cliext_multimap_generic_container.cpp   
// compile with: /clr   
#include <cliext/map>   
  
typedef cliext::multimap<wchar_t, int> Mymultimap;   
int main()   
    {   
    Mymultimap c1;   
    c1.insert(Mymultimap::make_value(L'a', 1));   
    c1.insert(Mymultimap::make_value(L'b', 2));   
    c1.insert(Mymultimap::make_value(L'c', 3));   
  
// display contents " [a 1] [b 2] [c 3]"   
    for each (Mymultimap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// construct a generic container   
    Mymultimap::generic_container^ gc1 = %c1;   
    for each (Mymultimap::value_type elem in gc1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// modify generic and display original   
    gc1->insert(Mymultimap::make_value(L'd', 4));   
    for each (Mymultimap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// modify original and display generic   
    c1.insert(Mymultimap::make_value(L'e', 5));   
    for each (Mymultimap::value_type elem in gc1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
[a 1] [b 2] [c 3]  
[a 1] [b 2] [c 3]  
[a 1] [b 2] [c 3] [d 4]  
[a 1] [b 2] [c 3] [d 4] [e 5]  
```  
  
## <a name="requirements"></a>要求  
 **标头：** \<cliext/映射 >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>另请参阅  
 [多重映射 (STL/CLR)](../dotnet/multimap-stl-clr.md)   
 [multimap::generic_iterator (STL/CLR)](../dotnet/multimap-generic-iterator-stl-clr.md)