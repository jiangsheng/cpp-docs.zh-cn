---
title: "__setusermatherr |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: __setusermatherr
apilocation:
- msvcr80.dll
- msvcr90.dll
- msvcrt.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr100.dll
- api-ms-win-crt-math-l1-1-0.dll
apitype: DLLExport
f1_keywords: __setusermatherr
dev_langs: C++
helpviewer_keywords: __setusermatherr
ms.assetid: f306818d-381a-4d68-8739-71b92bacb5ea
caps.latest.revision: "2"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: fa4f5b7b60bf4ea6fea0d0d63d2ee911101174b5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2017
---
# <a name="setusermatherr"></a>__setusermatherr
指定用户提供的例程（而不是 [_matherr](../c-runtime-library/reference/matherr.md) 例程）处理数学错误。  
  
## <a name="syntax"></a>语法  
  
```cpp  
void __setusermatherr(  
   _HANDLE_MATH_ERROR pf   
   )  
```  
  
#### <a name="parameters"></a>参数  
 `pf`  
 指向用户提供的 `_matherr` 的实现的指针。  
  
 将 `pf` 参数的类型声明为 `typedef int (__cdecl * _HANDLE_MATH_ERROR)(struct _exception *)`。  
  
## <a name="remarks"></a>备注  
  
## <a name="requirements"></a>要求  
  
|例程|必需的标头|  
|-------------|---------------------|  
|__setusermatherr|matherr.c|