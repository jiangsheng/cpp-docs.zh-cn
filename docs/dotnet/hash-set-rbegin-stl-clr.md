---
title: "hash_set::rbegin (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::hash_set::rbegin"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "rbegin 成员 [STL/CLR]"
ms.assetid: 1f2ff4ed-8557-40cf-8e61-816563acc43e
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# hash_set::rbegin (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

指定反转的受控序列的开头。  
  
## 语法  
  
```  
reverse_iterator rbegin();  
```  
  
## 备注  
 一个反向迭代器，指定受控序列的最后一个元素，或刚好在空序列的开头之外的位置。  因此，它指定反向序列的 `beginning`。  用于获取一个迭代器，该迭代器指定相反顺序的受控序列的 `current` 开头，但如果受控序列的长度发生更改，则该迭代器的状态也会发生更改。  
  
## 示例  
  
```  
// cliext_hash_set_rbegin.cpp   
// compile with: /clr   
#include <cliext/hash_set>   
  
typedef cliext::hash_set<wchar_t> Myhash_set;   
int main()   
    {   
    Myhash_set c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// inspect first two items in reversed sequence   
    Myhash_set::reverse_iterator rit = c1.rbegin();   
    System::Console::WriteLine("*rbegin() = {0}", *rit);   
    System::Console::WriteLine("*++rbegin() = {0}", *++rit);   
    return (0);   
    }  
  
```  
  
  **a b c**  
**\*rbegin\(\) \= c**  
**\*\+\+rbegin\(\) \= b**   
## 要求  
 **标头:** \<cliext\/hash\_set\>  
  
 **命名空间:** cliext  
  
## 请参阅  
 [hash\_set](../dotnet/hash-set-stl-clr.md)   
 [hash\_set::begin](../dotnet/hash-set-begin-stl-clr.md)   
 [hash\_set::end](../dotnet/hash-set-end-stl-clr.md)   
 [hash\_set::rend](../dotnet/hash-set-rend-stl-clr.md)