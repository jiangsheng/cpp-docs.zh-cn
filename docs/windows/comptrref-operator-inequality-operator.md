---
title: "Comptrref:: Operator ！ = 运算符 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: client/Microsoft::WRL::Details::ComPtrRef::operator!=
dev_langs: C++
ms.assetid: ab3093cc-6fbd-4039-890a-6df1cde992b6
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: a61ed97ffd3caad6d254d3258711a7b45ad3c0dc
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2017
---
# <a name="comptrrefoperator-operator"></a>ComPtrRef::operator!= 运算符
支持 WRL 基础结构，不应在代码中直接使用。  
  
## <a name="syntax"></a>语法  
  
```cpp  
bool operator!=(  
   const Details::ComPtrRef<ComPtr<T>>& a,  
   const Details::ComPtrRef<ComPtr<U>>& b  
);  
  
bool operator!=(  
   const Details::ComPtrRef<ComPtr<T>>& a,  
   decltype(__nullptr)  
);  
  
bool operator!=(  
   decltype(__nullptr),  
   const Details::ComPtrRef<ComPtr<T>>& a  
);  
  
bool operator!=(  
   const Details::ComPtrRef<ComPtr<T>>& a,  
   void* b  
);  
  
bool operator!=(  
   void* b,  
   const Details::ComPtrRef<ComPtr<T>>& a  
);  
```  
  
#### <a name="parameters"></a>参数  
 `a`  
 ComPtrRef 对象的引用。  
  
 `b`  
 对另一个 ComPtrRef 对象或指向的匿名对象的指针的引用 (`void*`)。  
  
## <a name="return-value"></a>返回值  
 第一个运算符生成`true`如果对象`a`不等于对象`b`; 否则为`false`。  
  
 第二个和第三个运算符生成`true`如果对象`a`是否不等于`nullptr`; 否则为`false`。  
  
 第四个和第五个运算符生成`true`如果对象`a`不等于对象`b`; 否则为`false`。  
  
## <a name="remarks"></a>备注  
 指示两个 ComPtrRef 对象是否不相等。  
  
## <a name="requirements"></a>要求  
 **标头：** client.h  
  
 **命名空间：** Microsoft::WRL  
  
## <a name="see-also"></a>另请参阅  
 [Microsoft::WRL::Details Namespace](../windows/microsoft-wrl-details-namespace.md)   
 [ComPtrRef 类](../windows/comptrref-class.md)