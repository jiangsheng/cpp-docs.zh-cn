---
title: "collection_adapter::base (STL/CLR) |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::collection_adapter::base
dev_langs: C++
helpviewer_keywords: base member [STL/CLR]
ms.assetid: 44928046-3fda-4974-817f-bc61a6f11b9f
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 87d8c557250f0ff97c0ef1d53e8cd4bb65b0476e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2017
---
# <a name="collectionadapterbase-stlclr"></a>collection_adapter::base (STL/CLR)
指定的已包装的 BCL 接口。  
  
## <a name="syntax"></a>语法  
  
```  
Coll^ base();  
```  
  
## <a name="remarks"></a>备注  
 成员函数返回存储的 BCL 接口句柄。  
  
## <a name="example"></a>示例  
  
```  
// cliext_collection_adapter_base.cpp   
// compile with: /clr   
#include <cliext/adapter>   
#include <cliext/deque>   
  
typedef cliext::collection_adapter<   
    System::Collections::ICollection> Mycoll;   
int main()   
    {   
    cliext::deque<wchar_t> d6x(6, L'x');   
    Mycoll c1(%d6x);   
  
// display initial contents " x x x x x x"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("base() same = {0}", c1.base() == %c1);   
    return (0);   
    }  
  
```  
  
```Output  
 x x x x x x  
base() same = True  
```  
  
## <a name="requirements"></a>要求  
 **标头：** \<cliext/适配器 >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>另请参阅  
 [collection_adapter (STL/CLR)](../dotnet/collection-adapter-stl-clr.md)