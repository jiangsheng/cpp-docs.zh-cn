---
title: "stack::container_type (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::stack::container_type"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "container_type 成员 [STL/CLR]"
ms.assetid: ca0e862d-e57d-4638-b0ba-b4c206de38ed
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# stack::container_type (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

基础容器的类型。  
  
## 语法  
  
```  
typedef Container value_type;  
```  
  
## 备注  
 类型是的同义词。`Container`模板参数  
  
## 示例  
  
```  
// cliext_stack_container_type.cpp   
// compile with: /clr   
#include <cliext/stack>   
  
typedef cliext::stack<wchar_t> Mystack;   
int main()   
    {   
    Mystack c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display contents " a b c" using container_type   
    Mystack::container_type wc1 = c1.get_container();   
    for each (wchar_t elem in wc1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **a b c**   
## 要求  
 **页眉：** \<\/cliext 堆栈\>  
  
 **命名空间：** cliext  
  
## 请参阅  
 [stack](../dotnet/stack-stl-clr.md)   
 [stack::get\_container](../dotnet/stack-get-container-stl-clr.md)