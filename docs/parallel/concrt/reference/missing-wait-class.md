---
title: "missing_wait 类 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- missing_wait
- CONCRT/concurrency::missing_wait
- CONCRT/concurrency::missing_wait::missing_wait
dev_langs:
- C++
helpviewer_keywords:
- missing_wait class
ms.assetid: ff981875-bd43-47e3-806f-b03c9f418b18
caps.latest.revision: 19
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
ms.openlocfilehash: 70b1c77660992b33de2204fd4f4221ed6e957e21
ms.contentlocale: zh-cn
ms.lasthandoff: 03/17/2017

---
# <a name="missingwait-class"></a>missing_wait 类
此类描述执行对象的析构函数时仍有计划到 `task_group` 或 `structured_task_group` 对象的任务时引发的异常。 如果因为堆栈展开为异常的结果而到达析构函数的调用条件，则永远不会引发此异常。  
  
## <a name="syntax"></a>语法  
  
```
class missing_wait : public std::exception;
```  
  
## <a name="members"></a>成员  
  
### <a name="public-constructors"></a>公共构造函数  
  
|名称|说明|  
|----------|-----------------|  
|[missing_wait](#ctor)|已重载。 构造 `missing_wait` 对象。|  
  
## <a name="remarks"></a>备注  
 不存在异常流，您负责进行调用`wait`或`run_and_wait`方法`task_group`或`structured_task_group`之前允许销毁该对象的对象。 运行时会引发此异常显示为相对值忘记调用`wait`或`run_and_wait`方法。  
  
## <a name="inheritance-hierarchy"></a>继承层次结构  
 `exception`  
  
 `missing_wait`  
  
## <a name="requirements"></a>要求  
 **标头︰** concrt.h  
  
 **命名空间：** 并发  
  
##  <a name="ctor"></a>missing_wait 

 构造 `missing_wait` 对象。  
  
```
explicit _CRTIMP missing_wait(_In_z_ const char* _Message) throw();

missing_wait() throw();
```  
  
### <a name="parameters"></a>参数  
 `_Message`  
 错误的描述性消息。  
  
## <a name="see-also"></a>另请参阅  
 [并发 Namespace](concurrency-namespace.md)   
 [task_group 类](task-group-class.md)   
 [等待](task-group-class.md)   
 [run_and_wait](task-group-class.md)   
 [structured_task_group 类](structured-task-group-class.md)

