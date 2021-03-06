---
title: "&lt;chrono&gt; 函数 | Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- chrono/std::duration_cast
- chrono/std::time_point_cast
ms.assetid: d6800e15-77a1-4df3-900e-d8b2fee190c7
caps.latest.revision: 10
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: 2df866e0f6fec9833c67e4d4ea405a826996dedf
ms.contentlocale: zh-cn
ms.lasthandoff: 10/03/2017

---
# <a name="ltchronogt-functions"></a>&lt;chrono&gt; 函数
||||  
|-|-|-|  
|[duration_cast](#duration_cast)|[time_point_cast](#time_point_cast)|  
  

##  <a name="duration_cast"></a>duration_cast
 将 `duration` 对象转换为指定类型。  
  
```  
template <class To, class Rep, class Period>  
constexpr To duration_cast(const duration<Rep, Period>& Dur);
```  
  
### <a name="return-value"></a>返回值  
 一个表示时间间隔 `Dur` 的 `To` 类型的 `duration` 对象，需进行截断才能适应目标类型大小。  
  
### <a name="remarks"></a>备注  
 如果 `To` 为 `duration` 的实例化，则此函数不参与重载决策。  
  
##  <a name="time_point_cast"></a>time_point_cast
 将 [time_point](../standard-library/time-point-class.md) 对象转换为指定类型。  
  
```  
template <class To, class Clock, class Duration>  
time_point<Clock, To> time_point_cast(const time_point<Clock, Duration>& Tp);
```  
  
### <a name="return-value"></a>返回值  
 持续时间为 `To` 类型的 `time_point` 对象。  
  
### <a name="remarks"></a>备注  
 除非 `To` 为 [duration](../standard-library/duration-class.md) 的实例化，否则函数不参与重载决策。  
  
## <a name="see-also"></a>另请参阅  
 [\<chrono>](../standard-library/chrono.md)


