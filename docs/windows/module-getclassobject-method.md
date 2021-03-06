---
title: "Module::GetClassObject 方法 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::Module::GetClassObject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetClassObject 方法"
ms.assetid: 95b0de1b-f728-4f96-9f44-f6ea71ce56e4
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Module::GetClassObject 方法
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

检索类工厂的缓存。  
  
## <a name="syntax"></a>语法  
  
```  
 HRESULT GetClassObject(  
   REFCLSID clsid,  
   REFIID riid,  
   _Deref_out_ void **ppv,  
   wchar_t* serverName = nullptr  
);  
```  
  
#### <a name="parameters"></a>参数  
 `clsid`  
 类 ID。  
  
 `riid`  
 您请求的接口 ID。  
  
 `ppv`  
 指向返回对象的指针。  
  
 `serverName`  
 在 `ActivatableClassWithFactory`、`ActivatableClassWithFactoryEx` 或 `ActivatableClass` 宏中指定的服务器名称；或用于获取默认服务器名称的 `nullptr`。  
  
## <a name="return-value"></a>返回值  
  
## <a name="remarks"></a>备注  
 仅对 COM 而不是 [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] 使用此方法。 此方法仅公开 IClassFactory 方法。  
  
## <a name="requirements"></a>要求  
 **标头︰** module.h  
  
 **命名空间：** Microsoft::WRL
 
 ## <a name="see-also"></a>另请参阅
 [Module 类](../windows/module-class.md)