---
title: "list::generic_value (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::list::generic_value"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "generic_value 成员 [STL/CLR]"
ms.assetid: daa0fc3f-cda2-4531-8cc2-a523737d4103
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# list::generic_value (STL/CLR)
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
// cliext_list_generic_value.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct a generic container   
    cliext::list<wchar_t>::generic_container^ gc1 = %c1;   
    for each (wchar_t elem in gc1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// modify generic and display original   
    cliext::list<wchar_t>::generic_iterator gcit = gc1->begin();   
    cliext::list<wchar_t>::generic_value gcval = *gcit;   
    *++gcit = gcval;   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **a b c**  
 **a b c**  
 **".**   
## 要求  
 **页眉：** \<\/cliext 列表\>  
  
 **命名空间：** cliext  
  
## 请参阅  
 [list](../dotnet/list-stl-clr.md)   
 [list::generic\_container](../dotnet/list-generic-container-stl-clr.md)   
 [list::generic\_iterator](../dotnet/list-generic-iterator-stl-clr.md)   
 [list::generic\_reverse\_iterator](../dotnet/list-generic-reverse-iterator-stl-clr.md)