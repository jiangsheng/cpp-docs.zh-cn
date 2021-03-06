---
title: "Module:: releasenotifier 类 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: module/Microsoft::WRL::Module::ReleaseNotifier
dev_langs: C++
helpviewer_keywords: ReleaseNotifier class
ms.assetid: 17249cd1-4d88-42e3-8146-da9e942d12bd
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: b48374182d9b39d43cbf0ec99cb51075867e914d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2017
---
# <a name="modulereleasenotifier-class"></a>Module::ReleaseNotifier 类
在释放模块中的最后一个对象时调用事件处理程序。  
  
## <a name="syntax"></a>语法  
  
```  
class ReleaseNotifier;  
```  
  
## <a name="members"></a>成员  
  
### <a name="public-constructors"></a>公共构造函数  
  
|名称|描述|  
|----------|-----------------|  
|[Module::ReleaseNotifier::~ReleaseNotifier 析构函数](../windows/module-releasenotifier-tilde-releasenotifier-destructor.md)|取消初始化 Module::ReleaseNotifier 类的当前实例。|  
|[Module::ReleaseNotifier::ReleaseNotifier 构造函数](../windows/module-releasenotifier-releasenotifier-constructor.md)|初始化 Module::ReleaseNotifier 类的新实例。|  
  
### <a name="public-methods"></a>公共方法  
  
|名称|描述|  
|----------|-----------------|  
|[Module::ReleaseNotifier::Invoke 方法](../windows/module-releasenotifier-invoke-method.md)|实现后，在释放模块中的最后一个对象时调用事件处理程序。|  
|[Module::ReleaseNotifier::Release](../windows/module-releasenotifier-release.md)|如果对象是使用 `true` 的参数构造的，则删除当前 Module::ReleaseNotifier 对象。|  
  
## <a name="inheritance-hierarchy"></a>继承层次结构  
 `ReleaseNotifier`  
  
## <a name="requirements"></a>要求  
 **标头：** module.h  
  
 **命名空间：** Microsoft::WRL
 
 ## <a name="see-also"></a>另请参阅
 [Module 类](../windows/module-class.md)