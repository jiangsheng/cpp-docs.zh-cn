---
title: "__pctype_func |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: __pctype_func
apilocation:
- msvcrt.dll
- msvcr110_clr0400.dll
- msvcr110.dll
- msvcr120.dll
- msvcr90.dll
- msvcr100.dll
- msvcr80.dll
apitype: DLLExport
f1_keywords: __pctype_func
dev_langs: C++
helpviewer_keywords: __pctype_func
ms.assetid: d52b8add-d07d-4516-a22f-e836cde0c57f
caps.latest.revision: "2"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: ae2c5f53c10083deb281a88a5f398712722700b3
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2017
---
# <a name="pctypefunc"></a>__pctype_func
检索指向字符分类信息数组的指针。  
  
## <a name="syntax"></a>语法  
  
```cpp  
const unsigned short *__pctype_func(  
   )  
```  
  
## <a name="return-value"></a>返回值  
 指向字符分类信息数组的指针。  
  
## <a name="remarks"></a>备注  
 字符分类表中的信息仅供内部使用，并且由对类型 `char` 的字符进行分类的各种函数使用。 有关详细信息，请参阅 [_pctype、_pwctype、_wctype、_mbctype、_mbcasemap](../c-runtime-library/pctype-pwctype-wctype-mbctype-mbcasemap.md) 中的 `Remarks` 部分。  
  
## <a name="requirements"></a>要求  
  
|例程|必需的标头|  
|-------------|---------------------|  
|__pctype_func|ctype.h|  
  
## <a name="see-also"></a>另请参阅  
 [_pctype、_pwctype、_wctype、_mbctype、_mbcasemap](../c-runtime-library/pctype-pwctype-wctype-mbctype-mbcasemap.md)