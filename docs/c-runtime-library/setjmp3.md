---
title: _setjmp3 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _setjmp3
apilocation:
- msvcrt.dll
- msvcr90.dll
- msvcr110.dll
- msvcr80.dll
- msvcr110_clr0400.dll
- msvcr100.dll
- msvcr120.dll
apitype: DLLExport
f1_keywords:
- setjmp3
- _setjmp3
dev_langs: C++
helpviewer_keywords:
- _setjmp3 function
- setjmp3 function
ms.assetid: 6129c2f3-8bac-4fdb-a827-44e1eebba500
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: ba68e059224d2d15046730a9ee0058e3114d52ed
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2017
---
# <a name="setjmp3"></a>_setjmp3
内部 CRT 函数。 `setjmp` 函数的新实现。  
  
## <a name="syntax"></a>语法  
  
```  
int _setjmp3(  
   OUT jmp_buf env,  
   int count,  
   (optional parameters)  
);  
```  
  
#### <a name="parameters"></a>参数  
 [out] `env`  
 用于存储状态信息的缓冲区地址。  
  
 [in] `count`  
 存储在 `DWORD` 中的信息的附加 `optional parameters` 数。  
  
 [in] `optional parameters`  
 由 `setjmp` 内部函数向下推送的其他数据。 第一个 `DWORD` 是一个用于展开多余数据并返回到永久性注册状态的函数指针。 第二个 `DWORD` 是要还原的尝试级别。 之后的所有数据都将保存在 `jmp_buf` 的通用数据数组中。  
  
## <a name="return-value"></a>返回值  
 始终返回 0。  
  
## <a name="remarks"></a>备注  
 请不要在 C++ 程序中使用此函数。 它是一个不支持 C++ 的内部函数。 有关如何使用 `setjmp` 的详细信息，请参阅[使用 setjmp/longjmp](../cpp/using-setjmp-longjmp.md)。  
  
## <a name="requirements"></a>要求  
  
## <a name="see-also"></a>另请参阅  
 [按字母顺序的函数参考](../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [setjmp](../c-runtime-library/reference/setjmp.md)