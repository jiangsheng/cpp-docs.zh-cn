---
title: "_msize | Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _msize
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
- api-ms-win-crt-heap-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- msize
- _msize
dev_langs:
- C++
helpviewer_keywords:
- memory blocks
- msize function
- _msize function
ms.assetid: 02b1f89e-d0d7-4f12-938a-9eeba48a0f88
caps.latest.revision: 12
author: corob-msft
ms.author: corob
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
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: f669b35ab67ff08835e3335f702027d61581b868
ms.contentlocale: zh-cn
ms.lasthandoff: 03/30/2017

---
# <a name="msize"></a>_msize
返回在堆中分配的存储块的大小。  
  
## <a name="syntax"></a>语法  
  
```  
  
      size_t _msize(  
   void *memblock   
);  
```  
  
#### <a name="parameters"></a>参数  
 `memblock`  
 指向内存块的指针。  
  
## <a name="return-value"></a>返回值  
 `_msize` 返回无符号整数形式的大小（以字节为单位）。  
  
## <a name="remarks"></a>备注  
 `_msize` 函数通过调用 `calloc`、`malloc` 或 `realloc` 返回分配的内存块的大小（以字节为单位）。  
  
 当应用程序与调试版的 C 运行时库链接时，`_msize` 将解析为 [_msize_dbg](../../c-runtime-library/reference/msize-dbg.md)。 有关在调试过程中如何托管堆的详细信息，请参阅 [CRT 调试堆](/visualstudio/debugger/crt-debug-heap-details)。  
  
 此函数验证其参数。 如果 `memblock` 为 null 指针，则 `_msize` 将调用无效参数处理程序，如[参数验证](../../c-runtime-library/parameter-validation.md)中所述。 如果处理了错误，则该函数将 `errno` 设置为 `EINVAL` 并返回 -1。  
  
## <a name="requirements"></a>要求  
  
|例程|必需的标头|  
|-------------|---------------------|  
|`_msize`|\<malloc.h>|  
  
 有关兼容性的详细信息，请参阅“简介”中的[兼容性](../../c-runtime-library/compatibility.md)。  
  
## <a name="libraries"></a>库  
 [C 运行时库](../../c-runtime-library/crt-library-features.md)的所有版本。  
  
## <a name="example"></a>示例  
 请参阅 [realloc](../../c-runtime-library/reference/realloc.md) 的示例。  
  
## <a name="see-also"></a>另请参阅  
 [内存分配](../../c-runtime-library/memory-allocation.md)   
 [calloc](../../c-runtime-library/reference/calloc.md)   
 [_expand](../../c-runtime-library/reference/expand.md)   
 [malloc](../../c-runtime-library/reference/malloc.md)   
 [realloc](../../c-runtime-library/reference/realloc.md)
