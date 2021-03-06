---
title: "hash_multimap:: clear (STL/CLR) |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::hash_multimap::clear
dev_langs: C++
helpviewer_keywords: clear member [STL/CLR]
ms.assetid: 8ad99f08-93b3-42b7-be07-f9a8ec556554
caps.latest.revision: "14"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 8bda656c05db383f944e66d90f9117d4dcb80a9f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2017
---
# <a name="hashmultimapclear-stlclr"></a>hash_multimap::clear (STL/CLR)
删除所有元素。  
  
## <a name="syntax"></a>语法  
  
```  
void clear();  
```  
  
## <a name="remarks"></a>备注  
 成员函数可有效地调用[hash_multimap:: erase (STL/CLR)](../dotnet/hash-multimap-erase-stl-clr.md) `(` [hash_multimap:: begin (STL/CLR)](../dotnet/hash-multimap-begin-stl-clr.md) `(),` [hash_multimap:: end (STL/CLR)](../dotnet/hash-multimap-end-stl-clr.md)`())`. 你可以使用它来确保受控的序列为空。  
  
## <a name="example"></a>示例  
  
```  
// cliext_hash_multimap_clear.cpp   
// compile with: /clr   
#include <cliext/hash_map>   
  
typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;   
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
  
// clear the container and reinspect   
    c1.clear();   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
    c1.insert(Myhash_multimap::make_value(L'a', 1));   
    c1.insert(Myhash_multimap::make_value(L'b', 2));   
  
// display contents " [a 1] [b 2]"   
    for each (Myhash_multimap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
    c1.clear();   
    System::Console::WriteLine("size() = {0}", c1.size());   
    return (0);   
    }  
  
```  
  
```Output  
 [a 1] [b 2] [c 3]  
size() = 0  
 [a 1] [b 2]  
size() = 0  
```  
  
## <a name="requirements"></a>要求  
 **标头：** \<cliext/hash_map >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>另请参阅  
 [hash_multimap (STL/CLR)](../dotnet/hash-multimap-stl-clr.md)   
 [hash_multimap::erase (STL/CLR)](../dotnet/hash-multimap-erase-stl-clr.md)