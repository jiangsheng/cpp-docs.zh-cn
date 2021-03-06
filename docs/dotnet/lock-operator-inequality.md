---
title: "lock::operator ！ = |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- lock.operator!=
- msclr.lock.operator!=
- msclr::lock::operator!=
- lock::operator!=
dev_langs: C++
helpviewer_keywords: lock::operator!=
ms.assetid: ed1d674e-9ee9-4257-8a7e-2e3567d50222
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 090d461a8f11d47d25119f5949f9f570093244fb
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2017
---
# <a name="lockoperator"></a>lock::operator!=
不是等运算符。  
  
## <a name="syntax"></a>语法  
  
```  
template<class T> bool operator!=(  
   T t  
);  
```  
  
#### <a name="parameters"></a>参数  
 `t`  
 要比较不相等的对象。  
  
## <a name="return-value"></a>返回值  
 返回`true`如果`t`锁的对象不同`false`否则为。  
  
## <a name="example"></a>示例  
  
```  
// msl_lock_op_ineq.cpp  
// compile with: /clr  
#include <msclr/lock.h>  
  
using namespace System;  
using namespace System::Threading;  
using namespace msclr;  
  
int main () {  
   Object^ o1 = gcnew Object;  
   Object^ o2 = gcnew Object;  
   lock l1(o1);  
   if (l1 != o2) {  
      Console::WriteLine("Inequal!");  
   }  
}  
```  
  
```Output  
Inequal!  
```  
  
## <a name="requirements"></a>要求  
 **标头文件** \<msclr\lock.h >  
  
 **Namespace** msclr  
  
## <a name="see-also"></a>另请参阅  
 [锁定成员](../dotnet/lock-members.md)   
 [lock::operator==](../dotnet/lock-operator-equality.md)