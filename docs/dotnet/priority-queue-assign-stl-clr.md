---
title: "priority_queue::assign (STL/CLR) |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::priority_queue::assign
dev_langs: C++
helpviewer_keywords: assign member [STL/CLR]
ms.assetid: 00cd3623-ecd0-4dde-ba5c-777c1c0bc0b5
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 38d36f63f6116764fe6bc00a9ab172bc46b98f3e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2017
---
# <a name="priorityqueueassign-stlclr"></a>priority_queue::assign (STL/CLR)
替换所有元素。  
  
## <a name="syntax"></a>语法  
  
```  
void assign(priority_queue<Value, Container>% right);  
```  
  
#### <a name="parameters"></a>参数  
 右  
 要插入的容器适配器。  
  
## <a name="remarks"></a>备注  
 成员函数将指派`right.get_container()`到基础的容器。 你可以使用它来更改队列的全部内容。  
  
## <a name="example"></a>示例  
  
```  
// cliext_priority_queue_assign.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::priority_queue<wchar_t> Mypriority_queue;   
int main()   
    {   
    Mypriority_queue c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign a repetition of values   
    Mypriority_queue c2;   
    c2.assign(c1);   
    for each (wchar_t elem in c2.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
c a b  
c a b  
```  
  
## <a name="requirements"></a>要求  
 **标头：** \<cliext/队列 >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>另请参阅  
 [priority_queue (STL/CLR)](../dotnet/priority-queue-stl-clr.md)   
 [priority_queue::operator= (STL/CLR)](../dotnet/priority-queue-operator-assign-stl-clr.md)