---
title: "casinh、casinhf、casinhl | Microsoft 文档"
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
- casinh
- casinhl
- casinhf
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
- casinh
- casinhf
- casinhl
- complex/casinh
- complex/casinhf
- complex/casinhl
dev_langs:
- C++
helpviewer_keywords:
- casinh function
- casinhf function
- casinhl function
ms.assetid: bd18340b-21dd-4c86-a14e-e8e15dd97e3b
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
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
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: 1620eb200723fe4b2cd6553e7ba50405b026d53c
ms.contentlocale: zh-cn
ms.lasthandoff: 04/01/2017

---
# <a name="casinh-casinhf-casinhl"></a>casinh、casinhf、casinhl
检索在间隔外的分支刮痕部为复数的反双曲正弦 [-i，+ 我] 轴虚部的复数。  
  
## <a name="syntax"></a>语法  
  
```  
_Dcomplex casinh(   
   _Dcomplex z   
);  
_Fcomplex casinh(   
   _Fcomplex z   
);  // C++ only  
_Lcomplex casinh(   
   _Lcomplex z   
);  // C++ only  
_Fcomplex casinhf(   
   _Fcomplex z   
);  
_Lcomplex casinhl(   
   _Lcomplex z   
);  
```  
  
#### <a name="parameters"></a>参数  
 `z`  
 表示角度的复数（以弧度为单位）。  
  
## <a name="return-value"></a>返回值  
 `z` 的反双曲正弦值（以弧度为单位）。 结果是未绑定该实际轴和间隔的 [-iπ/2 + iπ/2] 轴虚部的复数。  
  
## <a name="remarks"></a>备注  
 由于 C++ 允许重载，因此你可以调用采用并返回 `casinh` 和 `_Fcomplex` 值的 `_Lcomplex` 重载。 在 C 程序中，`casinh` 始终采用并返回 `_Dcomplex` 值。  
  
## <a name="requirements"></a>要求  
  
|例程|C 标头|C++ 标头|  
|-------------|--------------|------------------|  
|`casinh`,               `casinhf`, `casinhl`|\<complex.h>|\<ccomplex>|  
  
 有关兼容性的详细信息，请参阅“简介”中的[兼容性](../../c-runtime-library/compatibility.md)。  
  
## <a name="see-also"></a>另请参阅  
 [按字母顺序的函数参考](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [catanh、catanhf、catanhl](../../c-runtime-library/reference/catanh-catanhf-catanhl.md)   
 [ctanh、ctanhf、ctanhl](../../c-runtime-library/reference/ctanh-ctanhf-ctanhl.md)   
 [catan、catanf、catanl](../../c-runtime-library/reference/catan-catanf-catanl.md)   
 [csinh、csinhf、csinhl](../../c-runtime-library/reference/csinh-csinhf-csinhl.md)   
 [ccosh、ccoshf、ccoshl](../../c-runtime-library/reference/ccosh-ccoshf-ccoshl.md)   
 [cacosh、cacoshf、cacoshl](../../c-runtime-library/reference/cacosh-cacoshf-cacoshl.md)   
 [cacos、cacosf、cacosl](../../c-runtime-library/reference/cacos-cacosf-cacosl.md)   
 [ctan、ctanf、ctanl](../../c-runtime-library/reference/ctan-ctanf-ctanl.md)   
 [csin、csinf、csinl](../../c-runtime-library/reference/csin-csinf-csinl.md)   
 [casin、casinf、casinl](../../c-runtime-library/reference/casin-casinf-casinl.md)   
 [ccos、ccosf、ccosl](../../c-runtime-library/reference/ccos-ccosf-ccosl.md)   
 [csqrt、csqrtf、csqrtl](../../c-runtime-library/reference/csqrt-csqrtf-csqrtl.md)
