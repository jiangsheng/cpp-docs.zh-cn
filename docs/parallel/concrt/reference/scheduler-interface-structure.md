---
title: "scheduler_interface 结构 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- scheduler_interface
- PPLINTERFACE/concurrency::scheduler_interface
- PPLINTERFACE/concurrency::scheduler_interface::scheduler_interface::schedule
dev_langs:
- C++
ms.assetid: 4de61c78-a2c6-4698-bd47-964baf7fa287
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: a56c36ae0cb4cf7111137351dbd71cc53d73b42a
ms.contentlocale: zh-cn
ms.lasthandoff: 03/17/2017

---
# <a name="schedulerinterface-structure"></a>scheduler_interface 结构
计划程序接口  
  
## <a name="syntax"></a>语法  
  
```
struct __declspec(novtable) scheduler_interface;
```  
  
## <a name="members"></a>成员  
  
### <a name="public-methods"></a>公共方法  
  
|名称|描述|  
|----------|-----------------|  
|[scheduler_interface:: schedule](#schedule)||  
  
## <a name="inheritance-hierarchy"></a>继承层次结构  
 `scheduler_interface`  
  
## <a name="requirements"></a>要求  
 **标头︰** pplinterface.h  
  
 **命名空间：** 并发  
  
##  <a name="schedule"></a>scheduler_interface:: schedule 方法  
  
```
virtual void schedule(
    TaskProc_t,
 void*) = 0;
```  
  
## <a name="see-also"></a>另请参阅  
 [并发命名空间](concurrency-namespace.md)

