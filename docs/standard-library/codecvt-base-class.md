---
title: "codecvt_base 类 | Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: xlocale/std::codecvt_base
dev_langs: C++
helpviewer_keywords: codecvt_base class
ms.assetid: 7e95c083-91b4-4b3f-8918-0d4ea244a040
caps.latest.revision: "20"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 5ead26920f0b1aa7f49c43b60640a03241138163
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2017
---
# <a name="codecvtbase-class"></a>codecvt_base 类
一种 codecvt 类的基类，用于定义一种称为 **result** 的枚举类型，此类型用作 facet 成员函数的返回类型以便指示转换结果。  
  
## <a name="syntax"></a>语法  
  
```
class codecvt_base : public locale::facet {
public:
    enum result {ok, partial, error, noconv};
    codecvt_base( size_t _Refs = 0);
    bool always_noconv() const;
    int max_length() const;
    int encoding() const;
    ~codecvt_base()

protected:
    virtual bool do_always_noconv() const;
    virtual int do_max_length() const;
    virtual int do_encoding() const;
};
```  
  
## <a name="remarks"></a>备注  
 此类会描述常用于所有模板类 [codecvt](../standard-library/codecvt-class.md) 专用化的枚举。 枚举结果描述了来自 [do_in](../standard-library/codecvt-class.md#do_in) 或 [do_out](../standard-library/codecvt-class.md#do_out) 可能的返回值：  
  
- 如果内部和外部字符编码之间的转换成功，则为 **ok**。  
  
- 如果目标大小不足以使转换成功完成，则为 **partial**。  
  
- 如果源序列格式不正确，则为 **error**。  
  
- 如果函数不执行任何转换，则为 **noconv**。  
  
## <a name="requirements"></a>要求  
 **标头：**\<locale>  
  
 **命名空间：** std  
  
## <a name="see-also"></a>另请参阅  
 [C++ 标准库中的线程安全](../standard-library/thread-safety-in-the-cpp-standard-library.md)



