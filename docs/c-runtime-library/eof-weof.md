---
title: "EOF、WEOF |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: EOF
dev_langs: C++
helpviewer_keywords:
- EOF function
- WEOF function
- end of file
ms.assetid: a7150563-cdae-4cdf-9798-ad509990e505
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 0d2aa2496683f10b0f603839d27104bd0e28fa50
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2017
---
# <a name="eof-weof"></a>EOF、WEOF
## <a name="syntax"></a>语法  
  
```  
  
#include <stdio.h>  
```  
  
## <a name="remarks"></a>备注  
 当文件尾（或在某些情况下为错误）遇到错误时，I/O 例程将返回 EOF。  
  
 WEOF 将生成用于在宽流的结尾发出信号或报告错误条件的 **wint_t** 类型的值。  
  
## <a name="see-also"></a>另请参阅  
 [putc、putwc](../c-runtime-library/reference/putc-putwc.md)   
 [ungetc、ungetwc](../c-runtime-library/reference/ungetc-ungetwc.md)   
 [scanf、_scanf_l、wscanf、_wscanf_l](../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)   
 [fflush](../c-runtime-library/reference/fflush.md)   
 [fclose、_fcloseall](../c-runtime-library/reference/fclose-fcloseall.md)   
 [_ungetch、_ungetwch、_ungetch_nolock、_ungetwch_nolock](../c-runtime-library/reference/ungetch-ungetwch-ungetch-nolock-ungetwch-nolock.md)   
 [_putch、_putwch](../c-runtime-library/reference/putch-putwch.md)   
 [isascii、__isascii、iswascii](../c-runtime-library/reference/isascii-isascii-iswascii.md)   
 [全局常量](../c-runtime-library/global-constants.md)