---
title: "hash_multimap::equal_range (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::hash_multimap::equal_range"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "equal_range 成员 [STL/CLR]"
ms.assetid: 3ea11e31-d4af-4d2e-a80b-eafe12c97d0c
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# hash_multimap::equal_range (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

查找与指定键匹配的范围。  
  
## 语法  
  
```  
cliext::pair<iterator, iterator> equal_range(key_type key);  
```  
  
#### 参数  
 键  
 要搜索的键值。  
  
## 备注  
 成员函数返回一对迭代器 `cliext::pair<iterator, iterator>(` [hash\_multimap::lower\_bound](../dotnet/hash-multimap-lower-bound-stl-clr.md)[hash\_multimap::upper\_bound](../dotnet/hash-multimap-upper-bound-stl-clr.md)`(``key``),` `(``key``))`。  可以使用它来确定当前受控序列中与指定键匹配的元素范围。  
  
## 示例  
  
```  
// cliext_hash_multimap_equal_range.cpp   
// compile with: /clr   
#include <cliext/hash_map>   
  
typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;   
typedef Myhash_multimap::pair_iter_iter Pairii;   
int main()   
    {   
    Myhash_multimap c1;   
    c1.insert(Myhash_multimap::make_value(L'a', 1));   
    c1.insert(Myhash_multimap::make_value(L'b', 2));   
    c1.insert(Myhash_multimap::make_value(L'c', 3));   
  
// display contents " [a 1] [b 2] [c 3]"   
    for each (Myhash_multimap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// display results of failed search   
    Pairii pair1 = c1.equal_range(L'x');   
    System::Console::WriteLine("equal_range(L'x') empty = {0}",   
        pair1.first == pair1.second);   
  
// display results of successful search   
    pair1 = c1.equal_range(L'b');   
    for (; pair1.first != pair1.second; ++pair1.first)   
        System::Console::Write(" [{0} {1}]",   
            pair1.first->first, pair1.first->second);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **\[a 1\] \[b 2\] \[c 3\]**  
**equal\_range\(L'x'\) empty \= True**  
 **\[b 2\]**   
## 要求  
 **标头:** \<cliext\/hash\_map\>  
  
 **命名空间:** cliext  
  
## 请参阅  
 [hash\_multimap](../dotnet/hash-multimap-stl-clr.md)   
 [hash\_multimap::count](../dotnet/hash-multimap-count-stl-clr.md)   
 [hash\_multimap::find](../dotnet/hash-multimap-find-stl-clr.md)   
 [hash\_multimap::lower\_bound](../dotnet/hash-multimap-lower-bound-stl-clr.md)   
 [hash\_multimap::upper\_bound](../dotnet/hash-multimap-upper-bound-stl-clr.md)