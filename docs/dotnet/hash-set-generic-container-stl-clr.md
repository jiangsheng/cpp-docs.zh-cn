---
title: "hash_set::generic_container (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::hash_set::generic_container"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "generic_container 成员 [STL/CLR]"
ms.assetid: 7883af0b-e9ad-47fb-8ecc-14c563948e83
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# hash_set::generic_container (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

泛型接口的容器适配器类型。  
  
## 语法  
  
```  
typedef Microsoft::VisualC::StlClr::  
    IHash<GKey, GValue>  
    generic_container;  
```  
  
## 备注  
 此类型描述了模板容器类的泛型接口。  
  
## 示例  
  
```  
// cliext_hash_set_generic_container.cpp   
// compile with: /clr   
#include <cliext/hash_set>   
  
typedef cliext::hash_set<wchar_t> Myhash_set;   
int main()   
    {   
    Myhash_set c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct a generic container   
    Myhash_set::generic_container^ gc1 = %c1;   
    for each (wchar_t elem in gc1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// modify generic and display original   
    gc1->insert(L'd');   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// modify original and display generic   
    c1.insert(L'e');   
    for each (wchar_t elem in gc1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **a b c**  
 **a b c**  
 **a b c d**  
 **a b c d e**   
## 要求  
 **标头:** \<cliext\/hash\_set\>  
  
 **命名空间:** cliext  
  
## 请参阅  
 [hash\_set](../dotnet/hash-set-stl-clr.md)   
 [hash\_set::generic\_iterator](../dotnet/hash-set-generic-iterator-stl-clr.md)