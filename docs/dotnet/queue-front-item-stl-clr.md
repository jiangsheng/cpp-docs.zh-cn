---
title: "queue::front_item (STL/CLR) |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::queue::front_item
dev_langs: C++
helpviewer_keywords: front_item member [STL/CLR]
ms.assetid: 389ab030-4351-48e6-9b03-417f1d3fcb86
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: bef48cb7ba1914b5c5bef82543e464faaba8f8d1
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2017
---
# <a name="queuefrontitem-stlclr"></a>queue::front_item (STL/CLR)
访问第一个元素。  
  
## <a name="syntax"></a>语法  
  
```  
property value_type front_item;  
```  
  
## <a name="remarks"></a>备注  
 属性访问必须为非空的受控序列的第一个元素。 你可以使用它来读取或写入的第一个元素，当你知道它存在。  
  
## <a name="example"></a>示例  
  
```  
// cliext_queue_front_item.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::queue<wchar_t> Myqueue;   
int main()   
    {   
    Myqueue c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// inspect last item   
    System::Console::WriteLine("front_item = {0}", c1.front_item);   
  
// alter last item and reinspect   
    c1.front_item = L'x';   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
front_item = a  
 x b c  
```  
  
## <a name="requirements"></a>要求  
 **标头：** \<cliext/队列 >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>另请参阅  
 [队列 (STL/CLR)](../dotnet/queue-stl-clr.md)   
 [queue:: back (STL/CLR)](../dotnet/queue-back-stl-clr.md)   
 [queue::back_item (STL/CLR)](../dotnet/queue-back-item-stl-clr.md)   
 [queue:: front (STL/CLR)](../dotnet/queue-front-stl-clr.md)   
 [queue::front (STL/CLR)](../dotnet/queue-front-stl-clr.md)