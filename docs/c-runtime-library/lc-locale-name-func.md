---
title: ___lc_locale_name_func | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: ___lc_locale_name_func
apilocation:
- msvcrt.dll
- msvcr110.dll
- msvcr100.dll
- msvcr90.dll
- msvcr120.dll
- msvcr80.dll
- msvcr110_clr0400.dll
apitype: DLLExport
f1_keywords: ___lc_locale_name_func
dev_langs: C++
helpviewer_keywords: ___lc_locale_name_func
ms.assetid: ef858308-872e-43de-95e0-9b1b4084343e
caps.latest.revision: "4"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: a60ca29a61d423186c8b53f23aa9e4d2941f8c57
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2017
---
# <a name="lclocalenamefunc"></a>___lc_locale_name_func
内部 CRT 函数。 检索线程的当前区域设置名称。  
  
## <a name="syntax"></a>语法  
  
```cpp  
wchar_t** ___lc_locale_name_func(void);  
```  
  
## <a name="return-value"></a>返回值  
 指向包含线程的当前区域设置名称的字符串的指针。  
  
## <a name="remarks"></a>备注  
 `___lc_locale_name_func` 是一个内部 CRT 函数，其他 CRT 函数可将其用于从 CRT 数据的线程本地存储中获取当前区域设置名称。 也可通过使用 [_get_current_locale](../c-runtime-library/reference/get-current-locale.md) 函数或 [setlocale、_wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md) 函数提供此信息。  
  
 内部 CRT 函数特定于实现且会根据每个发行版本发生更改。 不建议在代码中使用它们。  
  
## <a name="requirements"></a>要求  
  
|例程|必需的标头|  
|-------------|---------------------|  
|`___lc_locale_name_func`|crt\src\setlocal.h|  
  
## <a name="see-also"></a>另请参阅  
 [_get_current_locale](../c-runtime-library/reference/get-current-locale.md)   
 [setlocale、_wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [_create_locale、_wcreate_locale](../c-runtime-library/reference/create-locale-wcreate-locale.md)   
 [_free_locale](../c-runtime-library/reference/free-locale.md)