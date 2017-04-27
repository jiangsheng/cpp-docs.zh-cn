---
title: "raise | Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- raise
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
- Raise
dev_langs:
- C++
helpviewer_keywords:
- signals, sending to executing programs
- raise function
- signals
- programs [C++], sending signals to executing programs
ms.assetid: a3ccd3ad-f68f-4a7b-a005-c3ebfb217e8b
caps.latest.revision: 14
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: ff8b387b81487e0c39ba5018487a1b8045bd0574
ms.lasthandoff: 02/24/2017

---
# <a name="raise"></a>raise
将信号发送到正在执行的程序。  
  
> [!NOTE]
>  不要使用此方法关闭 [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] 应用程序，除非在测试或调试方案中。 根据 [Windows 8 应用认证要求](http://go.microsoft.com/fwlink/?LinkId=262889)中第 3.6 节的说明，禁止以编程或 UI 方式关闭 [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] 应用。 有关详细信息，请参阅[应用程序生命周期（Windows 应用商店应用）](http://go.microsoft.com/fwlink/?LinkId=262853)。  
  
## <a name="syntax"></a>语法  
  
```  
  
      int raise(  
int sig   
);  
```  
  
#### <a name="parameters"></a>参数  
 *sig*  
 要引发的信号。  
  
## <a name="return-value"></a>返回值  
 如果成功，则 **raise** 返回 0。 否则，返回一个非零值。  
  
## <a name="remarks"></a>备注  
 **raise** 函数将 *sig* 发送到正在执行的程序。 如果对 **signal** 的之前调用已经为 *sig* 安装了信号处理函数，则 **raise** 将执行该函数。 如果未安装处理程序函数，则执行与信号值 *sig* 相关联的默认操作，如下所示：  
  
|Signal|含义|Default|  
|------------|-------------|-------------|  
|`SIGABRT`|异常终止|使用退出代码 3 终止调用程序|  
|`SIGFPE`|浮点错误|终止调用程序|  
|`SIGILL`|非法指令|终止调用程序|  
|`SIGINT`|CTRL+C 中断|终止调用程序|  
|`SIGSEGV`|非法存储区访问|终止调用程序|  
|`SIGTERM`|发送到程序的终止请求|忽略信号|  
  
 如果参数不是以上指定的有效信号，则调用无效的参数处理程序，如[参数验证](../../c-runtime-library/parameter-validation.md)中所述。 如果未处理，则函数将 `errno` 设置为 `EINVAL` 并返回一个非零值。  
  
## <a name="requirements"></a>要求  
  
|例程|必需的标头|  
|-------------|---------------------|  
|**raise**|\<signal.h>|  
  
 有关其他兼容性信息，请参阅[兼容性](../../c-runtime-library/compatibility.md)。  
  
## <a name="libraries"></a>库  
 [C 运行时库](../../c-runtime-library/crt-library-features.md)的所有版本。  
  
## <a name="net-framework-equivalent"></a>.NET Framework 等效项  
 不适用。 若要调用标准 C 函数，请使用 `PInvoke`。 有关详细信息，请参阅[平台调用示例](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)。  
  
## <a name="see-also"></a>另请参阅  
 [进程和环境控制](../../c-runtime-library/process-and-environment-control.md)   
 [abort](../../c-runtime-library/reference/abort.md)   
 [signal](../../c-runtime-library/reference/signal.md)