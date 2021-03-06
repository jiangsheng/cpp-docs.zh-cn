---
title: "time_put_byname 类 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- xloctime/std::time_put_byname
dev_langs:
- C++
helpviewer_keywords:
- time_put_byname class
ms.assetid: e08c2348-64d2-4ace-98b1-1496e14c7b1a
caps.latest.revision: 25
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: ba50414643d430798912e6a7a25d3fe9c49c1b9a
ms.contentlocale: zh-cn
ms.lasthandoff: 10/03/2017

---
# <a name="timeputbyname-class"></a>time_put_byname 类
一种派生模板类，用于描述一个可充当类型 `time_put`\< CharType, OutputIterator > 的区域设置 facet 的对象。  
  
## <a name="syntax"></a>语法  
  
```
template <class CharType, class OutIt = ostreambuf_iterator<CharType, char_traits<CharType>>>
class time_put_byname : public time_put<CharType, OutputIterator>
{
public:
    explicit time_put_byname(
    const char* _Locname,
    size_t _Refs = 0);

    explicit time_put_byname(
    const string& _Locname,
    size_t _Refs = 0);

protected:
    virtual ~time_put_byname();

};
```  
  
#### <a name="parameters"></a>参数  
 `_Locname`  
 区域设置名称。  
  
 `_Refs`  
 初始引用计数。  
  
## <a name="remarks"></a>备注  
 其行为由[已命名的](../standard-library/locale-class.md#name)区域设置 `_Locname` 决定。 每个构造函数使用 [time_put](../standard-library/time-put-class.md#time_put)\<CharType、 OutputIterator 1> ( `_Refs`) 初始化其基对象。  
  
## <a name="requirements"></a>要求  
 **标头：**\<locale>  
  
 **命名空间：** std  
  
## <a name="see-also"></a>另请参阅  
 [C++ 标准库中的线程安全](../standard-library/thread-safety-in-the-cpp-standard-library.md)




