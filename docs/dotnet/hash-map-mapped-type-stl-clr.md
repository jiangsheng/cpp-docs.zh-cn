---
title: "hash_map::mapped_type (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::hash_map::mapped_type"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "mapped_type 成员 [STL/CLR]"
ms.assetid: 00c8738f-7dd9-418d-9566-a2e05fd7e7f6
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# hash_map::mapped_type (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

与每个键关联的映射值的类型。  
  
## 语法  
  
```  
typedef Mapped mapped_type;  
```  
  
## 备注  
 表示模板参数的 `Mapped`同义词。  
  
## 示例  
  
```  
// cliext_hash_map_mapped_type.cpp   
// compile with: /clr   
#include <cliext/hash_map>   
  
typedef cliext::hash_map<wchar_t, int> Myhash_map;   
int main()   
    {   
    Myhash_map c1;   
    c1.insert(Myhash_map::make_value(L'a', 1));   
    c1.insert(Myhash_map::make_value(L'b', 2));   
    c1.insert(Myhash_map::make_value(L'c', 3));   
  
// display contents " [a 1] [b 2] [c 3]" using mapped_type   
    for (Myhash_map::iterator it = c1.begin(); it != c1.end(); ++it)   
        {   // store element in mapped_type object   
        Myhash_map::mapped_type val = it->second;   
  
        System::Console::Write(" {0}", val);   
        }   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **1 2 3**   
## 要求  
 **标头:** \<cliext\/hash\_map\>  
  
 **Namespace:** cliext  
  
## 请参阅  
 [hash\_map](../dotnet/hash-map-stl-clr.md)   
 [hash\_map::key\_compare](../dotnet/hash-map-key-compare-stl-clr.md)   
 [hash\_map::value\_type](../dotnet/hash-map-value-type-stl-clr.md)