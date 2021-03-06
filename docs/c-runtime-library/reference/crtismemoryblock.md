---
title: "_CrtIsMemoryBlock | Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _CrtIsMemoryBlock
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
apitype: DLLExport
f1_keywords:
- CrtlsMemoryBlock
- _CrtIsMemoryBlock
dev_langs:
- C++
helpviewer_keywords:
- _CrtIsMemoryBlock function
- CrtIsMemoryBlock function
ms.assetid: f7cbbc60-3690-4da0-a07b-68fd7f250273
caps.latest.revision: 14
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 739a3625f264492ec59d3b5e9f9fef67b3c20df7
ms.contentlocale: zh-cn
ms.lasthandoff: 10/09/2017

---
# <a name="crtismemoryblock"></a>_CrtIsMemoryBlock
确认指定的内存块位于本地堆，并且具有有效的调试堆块类型标识符（仅限调试版本）。  
  
## <a name="syntax"></a>语法  
  
```  
int _CrtIsMemoryBlock(   
   const void *userData,  
   unsigned int size,  
   long *requestNumber,  
   char **filename,  
   int *linenumber   
);  
```  
  
#### <a name="parameters"></a>参数  
 [in] `userData`  
 指向要验证的内存块开头的指针。  
  
 [in] `size`  
 指定块的大小（以字节为单位）。  
  
 [out] `requestNumber`  
 指向块分配编号的指针或 `NULL`。  
  
 [out] `filename`  
 指向已请求块的源文件名的指针或 `NULL`。  
  
 [out] `linenumber`  
 指向源文件中的行号的指针或 `NULL`。  
  
## <a name="return-value"></a>返回值  
 如果指定的内存块位于本地堆，并且具有有效的调试堆块类型标识符，则 `_CrtIsMemoryBlock` 返回 `TRUE`，否则，该函数返回 `FALSE`。  
  
## <a name="remarks"></a>备注  
 `_CrtIsMemoryBlock` 函数确认指定的内存块位于应用程序的本地堆，并且具有有效的块类型标识符。 此函数还可用于获取最初请求内存块分配的对象分配序号和源文件名/行号。 `requestNumber`、`filename` 或 `linenumber` 参数传递非 NULL 值会导致 `_CrtIsMemoryBlock` 将这些参数设置为内存块调试标头中的值（如果它在本地堆中找到该内存块）。 未定义 [_DEBUG](../../c-runtime-library/debug.md) 时，会在预处理过程中删除对 `_CrtIsMemoryBlock` 的调用。  
  
 如果 `_CrtIsMemoryBlock` 失败，则返回 `FALSE`，输出参数将初始化为默认值：将 `requestNumber` 和 `lineNumber` 设置为 0，将 `filename` 设置为 `NULL`。  
  
 因为此函数返回 `TRUE` 或 `FALSE`，因此可将它传递到一个 [_ASSERT](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md) 宏，以创建一种简单的调试错误处理机制。 如果本地堆中没有指定的地址，则以下示例将导致断言失败：  
  
```  
_ASSERTE( _CrtIsMemoryBlock( userData, size, &requestNumber,   
&filename, &linenumber ) );  
```  
  
 有关如何将 `_CrtIsMemoryBlock` 与其他调试函数和宏一起使用的详细信息，请参阅[用于报告的宏](/visualstudio/debugger/macros-for-reporting)。 有关如何在基堆的调试版本中分配、初始化和管理内存块的信息，请参阅 [CRT 调试堆详细信息](/visualstudio/debugger/crt-debug-heap-details)。  
  
## <a name="requirements"></a>要求  
  
|例程|必需的标头|  
|-------------|---------------------|  
|`_CrtIsMemoryBlock`|\<crtdbg.h>|  
  
 有关兼容性的详细信息，请参阅“简介”中的[兼容性](../../c-runtime-library/compatibility.md)。  
  
## <a name="libraries"></a>库  
 仅限 [C 运行时库](../../c-runtime-library/crt-library-features.md)的调试版本。  
  
## <a name="example"></a>示例  
 请参阅 [_CrtIsValidHeapPointer](../../c-runtime-library/reference/crtisvalidheappointer.md) 主题的示例。  
  
## <a name="see-also"></a>另请参阅  
 [调试例程](../../c-runtime-library/debug-routines.md)
