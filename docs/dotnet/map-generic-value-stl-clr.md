---
title: "map::generic_value (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::map::generic_value"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "generic_value 成员 [STL/CLR]"
ms.assetid: bd42ec86-fb9e-4c0d-8cae-7187a8742a94
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# map::generic_value (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

一元素的类型用于泛型接口的容器使用的。  
  
## 语法  
  
```  
typedef GValue generic_value;  
```  
  
## 备注  
 描述类型存储描述的元素值用于带有泛型接口的容器类使用此模板的 `GValue` 类型的对象。  
  
## 示例  
  
```  
// cliext_map_generic_value.cpp   
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
    for each (Mymap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// construct a generic container   
    Mymap::generic_container^ gc1 = %c1;   
    for each (Mymap::value_type elem in gc1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// get an element and display it   
    Mymap::generic_iterator gcit = gc1->begin();   
    Mymap::generic_value gcval = *gcit;   
    System::Console::WriteLine(" [{0} {1}]", gcval->first, gcval->second);   
    return (0);   
    }  
  
```  
  
  **\[a 1\] \[b 2\] \[c 3\]**  
 **\[a 1\] \[b 2\] \[c 3\]**  
 **\[一个 1\]**   
## 要求  
 **页眉：** \<\/cliext 映射\>  
  
 **命名空间：** cliext  
  
## 请参阅  
 [map](../dotnet/map-stl-clr.md)   
 [map::generic\_container](../dotnet/map-generic-container-stl-clr.md)   
 [map::generic\_iterator](../dotnet/map-generic-iterator-stl-clr.md)   
 [map::generic\_reverse\_iterator](../dotnet/map-generic-reverse-iterator-stl-clr.md)