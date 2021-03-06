---
title: "set::end (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::set::end"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "end 成员 [STL/CLR]"
ms.assetid: 3fe66e73-5eb9-4972-8a07-01f2eb4d1ccb
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# set::end (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

指定受控序列的末尾。  
  
## 语法  
  
```  
iterator end();  
```  
  
## 备注  
 该成员函数返回一个双向迭代器，指向刚刚超越控制序列的末尾。  用于获取一个迭代器，该迭代器指定受控序列的末尾，但如果受控序列的长度发生更改，则该迭代器的状态也不会发生更改。  
  
## 示例  
  
```  
// cliext_set_end.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::set<wchar_t> Myset;   
int main()   
    {   
    Myset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// inspect last two items   
    Myset::iterator it = c1.end();   
    --it;   
    System::Console::WriteLine("*-- --end() = {0}", *--it);   
    System::Console::WriteLine("*--end() = {0}", *++it);   
    return (0);   
    }  
  
```  
  
  **a b c**  
**\*\-\- \-\-end\(\) \= b**  
**\*\-\-end\(\) \= c**   
## 要求  
 **标头:** \<cliext\/set\>  
  
 **命名空间:** cliext  
  
## 请参阅  
 [集合](../dotnet/set-stl-clr.md)   
 [set::begin](../dotnet/set-begin-stl-clr.md)