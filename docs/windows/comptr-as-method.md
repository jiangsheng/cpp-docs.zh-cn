---
title: "Comptr:: As 方法 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: client/Microsoft::WRL::ComPtr::As
dev_langs: C++
helpviewer_keywords: As method
ms.assetid: 2ad6c262-9bdb-4c59-a330-1af8bcd445cc
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: e12869710694083bb0608f158c91e14df36b9ed9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2017
---
# <a name="comptras-method"></a>ComPtr::As 方法
返回表示由指定模板参数标识的接口的 ComPtr 对象。  
  
## <a name="syntax"></a>语法  
  
```  
  
template<  
   typename U  
>  
HRESULT As(  
   _Out_ ComPtr<U>* p  
) const;  
  
template<  
   typename U  
>  
HRESULT As(  
   _Out_ Details::ComPtrRef<ComPtr<U>> p  
) const;  
  
```  
  
#### <a name="parameters"></a>参数  
 `U`  
 要由参数表示的接口`p`。  
  
 `p`  
 表示由参数指定的接口的 ComPtr 对象`U`。 参数`p`不得引用当前 ComPtr 对象。  
  
## <a name="remarks"></a>备注  
 第一个模板是应在代码中使用的表单。 第二个模板是支持 [自动](../cpp/auto-cpp.md) 类型推导关键字等 C++ 语言功能的内部专用帮助器。  
  
## <a name="return-value"></a>返回值  
 如果成功，则为 S_OK；否则为指示错误的 HRESULT。  
  
## <a name="requirements"></a>要求  
 **标头：** client.h  
  
 **命名空间：** Microsoft::WRL  
  
## <a name="see-also"></a>另请参阅  
 [ComPtr 类](../windows/comptr-class.md)