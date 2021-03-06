---
title: "_get_doserrno | Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _get_doserrno
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _get_doserrno
- get_doserrno
dev_langs: C++
helpviewer_keywords:
- get_doserrno function
- _get_doserrno function
ms.assetid: 7fec7be3-6e39-4181-846b-8ef24489361c
caps.latest.revision: "19"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 67f546afa3059508787c7d3a5295d2b85651f125
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2017
---
# <a name="getdoserrno"></a>_get_doserrno
请先获取由操作系统返回的错误值，然后再将该值转换为 `errno` 值。  
  
## <a name="syntax"></a>语法  
  
```  
errno_t _get_doserrno(   
   int * pValue   
);   
```  
  
#### <a name="parameters"></a>参数  
 [out] `pValue`  
 指向要使用 `_doserrno` 全局宏的当前值填充的整数的指针。  
  
## <a name="return-value"></a>返回值  
 如果 `_get_doserrno` 成功，则它将返回零；如果失败，则它将返回错误代码。 如果 `pValue` 为 `NULL`，则将调用无效的参数处理程序，如[参数验证](../../c-runtime-library/parameter-validation.md)中所述。 如果允许执行继续，则该函数将 `errno` 设置为 `EINVAL` 并返回 `EINVAL`。  
  
## <a name="remarks"></a>备注  
 在进程执行开始之前，在 CRT 初始化过程中将 `_doserrno` 全局宏设置为零。 将它设置为由返回操作系统错误的任一系统级函数调用返回的操作系统错误值，而且在执行过程中永远不会将其重置为零。 当你编写代码以检查由某个函数返回的错误值时，请始终在函数调用之前使用 [_set_doserrno](../../c-runtime-library/reference/set-doserrno.md) 清除 `_doserrno`。 因为另一个函数调用可能会覆盖 `_doserrno`，因此请在函数调用之后立即使用 `_get_doserrno` 检查该值。  
  
 建议使用 [_get_errno](../../c-runtime-library/reference/get-errno.md) 而非 `_get_doserrno` 获取可移植的错误代码。  
  
 在 \<errno.h> 中定义 `_doserrno` 的可能值。  
  
## <a name="requirements"></a>要求  
  
|例程|必需的标头|可选标头|  
|-------------|---------------------|---------------------|  
|`_get_doserrno`|\<stdlib.h>、\<cstdlib> (C++)|\<errno.h>、\<cerrno> (C++)|  
  
 `_get_doserrno` 是 Microsoft 扩展。 有关兼容性的详细信息，请参阅[兼容性](../../c-runtime-library/compatibility.md)。  
  
## <a name="see-also"></a>另请参阅  
 [_set_doserrno](../../c-runtime-library/reference/set-doserrno.md)   
 [errno、_doserrno、_sys_errlist 和 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)