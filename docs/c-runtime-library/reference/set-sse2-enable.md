---
title: "_set_SSE2_enable | Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _set_SSE2_enable
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
- _set_SSE2_enable
- set_SSE2_enable
dev_langs: C++
helpviewer_keywords:
- _set_SSE2_enable function
- Streaming SIMD Extensions 2 instructions
- set_SSE2_enable function
ms.assetid: 55db895d-fc1e-475a-9110-b781a9bb51c5
caps.latest.revision: "19"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: d6db305c6674b974786cd6c17e6bf8b63b304aa2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2017
---
# <a name="setsse2enable"></a>_set_SSE2_enable
启用或禁用在 CRT 数学例程中使用[流式处理 SIMD 扩展 2](http://msdn.microsoft.com/en-us/f98440eb-73a9-4f96-b203-ac41bb6701ea) (SSE2) 指令。 （此函数在 x64 体系结构上不可用，因为默认情况下将启用 SSE2。）  
  
## <a name="syntax"></a>语法  
  
```  
int _set_SSE2_enable(  
   int flag  
);  
```  
  
#### <a name="parameters"></a>参数  
 `flag`  
 1 表示启用 SSE2 实现；0 表示禁用 SSE2 实现。 默认情况下，在支持 SSE2 实现的处理器上启用 SSE2 实现。  
  
## <a name="return-value"></a>返回值  
 如果启用 SSE2 实现，则值为非零；如果禁用 SSE2 实现，则值为零。  
  
## <a name="remarks"></a>备注  
 下列函数具有 SSE2 实现，可通过使用 `_set_SSE2_enable` 进行启用：  
  
-   [atan](../../c-runtime-library/reference/atan-atanf-atanl-atan2-atan2f-atan2l.md)  
  
-   [ceil](../../c-runtime-library/reference/ceil-ceilf-ceill.md)  
  
-   [exp](../../c-runtime-library/reference/exp-expf.md)  
  
-   [floor](../../c-runtime-library/reference/floor-floorf-floorl.md)  
  
-   [log](../../c-runtime-library/reference/log-logf-log10-log10f.md)  
  
-   [log10](../../c-runtime-library/reference/log-logf-log10-log10f.md)  
  
-   [modf](../../c-runtime-library/reference/modf-modff-modfl.md)  
  
-   [pow](../../c-runtime-library/reference/pow-powf-powl.md)  
  
 这些函数的 SSE2 实现可能会产生与默认实现稍微不同的答案，因为 SSE2 中间值为 64 位浮点数，而默认实现中间值为 80 位浮点数。  
  
> [!NOTE]
>  如果使用 [/Oi（生成内部函数）](../../build/reference/oi-generate-intrinsic-functions.md)编译器选项编译项目，则可能出现 `_set_SSE2_enable` 似乎没有效果的情况。 `/Oi` 编译器选项为编译器提供使用内部函数的权限来替换 CRT 调用；此行为重写 `_set_SSE2_enable` 的效果。 如果要保证 `/Oi` 不会重写 `_set_SSE2_enable`，请使用 `/Oi-` 来编译项目。 当使用暗示 `/Oi` 的其他编译器开关时，这也可能是一种好方法。  
  
 只有在屏蔽所有异常时才可使用 SSE2 实现。 使用 [_control87、_controlfp](../../c-runtime-library/reference/control87-controlfp-control87-2.md) 来屏蔽异常。  
  
## <a name="requirements"></a>要求  
  
|例程|必需的标头|  
|-------------|---------------------|  
|`_set_SSE2_enable`|\<math.h>|  
  
 有关兼容性的详细信息，请参阅“简介”中的[兼容性](../../c-runtime-library/compatibility.md)。  
  
## <a name="example"></a>示例  
  
```  
// crt_set_SSE2_enable.c  
// processor: x86  
#include <math.h>  
#include <stdio.h>  
  
int main()  
{  
   int i = _set_SSE2_enable(1);  
  
   if (i)  
      printf("SSE2 enabled.\n");  
   else  
      printf("SSE2 not enabled; processor does not support SSE2.\n");  
}  
```  
  
 **输出**  
  
 `SSE2 enabled.`  
  
## <a name="see-also"></a>另请参阅  
 [CRT 库功能](../../c-runtime-library/crt-library-features.md)