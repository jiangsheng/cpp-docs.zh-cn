---
title: "ctype_byname 类 | Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: xlocale/std::ctype_byname
dev_langs: C++
helpviewer_keywords: ctype_byname class
ms.assetid: a5cec021-a1f8-425f-8757-08e6f064b604
caps.latest.revision: "22"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: f1fb3ef836361a4d98ac8c7ab764da5e3fd43c7a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2017
---
# <a name="ctypebyname-class"></a>ctype_byname 类
派生模板类描述一个对象，该对象可以充当给定区域设置的 ctype facet ，允许对字符进行分类，并在大小写之间以及本机字符集和区域设置指定的字符集之间进行转换。  
  
## <a name="syntax"></a>语法  
  
```
template <class _Elem>
class ctype_byname : public ctype<_Elem>
{
public:
    explicit ctype_byname(
    const char* _Locname,
    size_t _Refs = 0);

    explicit ctype_byname(
    const string& _Locname,
    size_t _Refs = 0);

protected:
    virtual __CLR_OR_THIS_CALL ~ctype_byname();

};
```  
  
## <a name="remarks"></a>备注  
 其行为由命名的区域设置 `_Locname` 决定。 每个构造函数对具有 [ctype](../standard-library/ctype-class.md)\<CharType 1> ( `_Refs`) 的基对象或基类 `ctype<char>` 的同等对象进行初始化。  
  
## <a name="requirements"></a>要求  
 **标头：**\<locale>  
  
 **命名空间：** std  
  
## <a name="see-also"></a>另请参阅  
 [C++ 标准库中的线程安全](../standard-library/thread-safety-in-the-cpp-standard-library.md)



