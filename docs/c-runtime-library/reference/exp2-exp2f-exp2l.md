---
title: "exp2、exp2f、exp2l |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- exp2
- exp2f
- exp2l
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-math-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- exp2
- math/exp2
- exp2f
- math/exp2f
- exp2l
- math/exp2l
dev_langs: C++
helpviewer_keywords:
- exp2 function
- exp2f function
- exp2l function
ms.assetid: 526e3e10-201a-4610-a886-533f44ece344
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 19aeabbda33f4eb2e6b140ab2d887813f155b67f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2017
---
# <a name="exp2-exp2f-exp2l"></a>exp2、exp2f、exp2l
计算 2 提升到指定的值。  
  
## <a name="syntax"></a>语法  
  
```  
double exp2(  
   double x  
);  
  
float exp2(  
   float x  
);  // C++ only  
  
long double exp2(  
   long double x  
); // C++ only  
  
float exp2f(  
   float x  
);  
  
long double exp2l(  
   long double x  
);  
```  
  
#### <a name="parameters"></a>参数  
 [in] `x`  
 指数值。  
  
## <a name="return-value"></a>返回值  
 如果成功，返回的二进制指数`x`，即 2<sup>x</sup>。 否则，它将返回下列值之一：  
  
|问题|返回|  
|-----------|------------|  
|`x` = ±0|1|  
|`x` = -INFINITY|+0|  
|`x` = +INFINITY|+INFINITY|  
|`x` = NaN|NaN|  
|溢出范围错误|+ HUGE_VAL、+ HUGE_VALF，或 + HUGE_VALL|  
|下溢范围错误|正确的结果，舍入后|  
  
 按 [_matherr](../../c-runtime-library/reference/matherr.md) 中所指定的报告错误。  
  
## <a name="remarks"></a>备注  
 由于 c + + 允许重载，你可以调用的重载`exp2`采用并返回**float**和**长双精度**类型。 在 C 程序中，`exp2`始终采用并返回**double**。  
  
## <a name="requirements"></a>要求  
  
|例程|C 标头|C++ 标头|  
|-------------|--------------|------------------|  
|`exp`, `expf`, `expl`|\<math.h>|\<cmath>|  
  
 有关其他兼容性信息，请参阅[兼容性](../../c-runtime-library/compatibility.md)。  
  
## <a name="see-also"></a>另请参阅  
 [按字母顺序的函数参考](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [exp、 expf，资源管理器](../../c-runtime-library/reference/exp-expf.md)   
 [log2、log2f、log2l](../../c-runtime-library/reference/log2-log2f-log2l.md)