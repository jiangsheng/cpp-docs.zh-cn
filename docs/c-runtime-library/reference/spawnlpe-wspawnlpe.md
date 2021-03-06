---
title: "_spawnlpe、_wspawnlpe | Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _spawnlpe
- _wspawnlpe
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
- api-ms-win-crt-process-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- spawnlpe
- _wspawnlpe
- _spawnlpe
- wspawnlpe
dev_langs: C++
helpviewer_keywords:
- _wspawnlpe function
- wspawnlpe function
- processes, creating
- spawnlpe function
- _spawnlpe function
- processes, executing new
- process creation
ms.assetid: e171ebfa-70e7-4c44-8331-2a291fc17bd6
caps.latest.revision: "18"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 693f356f990a0b2e9d66aa1a3b8b53583500cfad
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2017
---
# <a name="spawnlpe-wspawnlpe"></a>_spawnlpe、_wspawnlpe
创建并执行更新过程。  
  
> [!IMPORTANT]
>  此 API 不能用于在 Windows 运行时中执行的应用程序。 有关详细信息，请参阅 [/ZW 不支持的 CRT 函数](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)。  
  
## <a name="syntax"></a>语法  
  
```  
intptr_t _spawnlpe(  
   int mode,  
   const char *cmdname,  
   const char *arg0,  
   const char *arg1,  
   ... const char *argn,  
   NULL,  
   const char *const *envp   
);  
intptr_t _wspawnlpe(  
   int mode,  
   const wchar_t *cmdname,  
   const wchar_t *arg0,  
   const wchar_t *arg1,  
   ... const wchar_t *argn,  
   NULL,  
   const wchar_t *const *envp   
);  
```  
  
#### <a name="parameters"></a>参数  
 `mode`  
 调用进程的执行模式。  
  
 `cmdname`  
 要执行的文件的路径。  
  
 `arg0, arg1, ... argn`  
 指向参数的指针的列表。 `arg0` 参数通常是指向 `cmdname` 的指针。 参数 `arg1` 到 `argn` 是指向构成新参数列表的字符字符串的指针。 在 `argn` 之后，必须是一个 `NULL` 指针，用以标记参数列表的末尾。  
  
 `envp`  
 指向环境设置的指针的数组。  
  
## <a name="return-value"></a>返回值  
 同步 `_spawnlpe` 或 `_wspawnlpe`（为 `_P_WAIT` 指定的 `mode`）中的返回值是新进程的退出状态。 异步 `_spawnlpe` 或 `_wspawnlpe`（为 `_P_NOWAIT` 指定的 `_P_NOWAITO` 或 `mode`）的返回值是进程句柄。 如果进程正常终止，则退出状态为 0。 如果生成进程专门使用非零参数调用 `exit` 例程，则可以将退出状态设置为一个非零值。 如果更新过程未显式设置正退出状态，则正退出状态指示因中止或中断而造成的异常退出。 返回值-1 指示的错误 （不启动新过程）。 在这种情况下， `errno` 设置为下列值之一。  
  
 `E2BIG`  
 参数列表超过 1024 个字节。  
  
 `EINVAL`  
 `mode` 参数无效。  
  
 `ENOENT`  
 未找到文件或路径。  
  
 `ENOEXEC`  
 指定的文件不是可执行文件，或者具有无效的可执行文件格式。  
  
 `ENOMEM`  
 没有足够的内存可用于执行新进程。  
  
 有关这些代码及其他返回代码的详细信息，请参阅 [errno、_doserrno、_sys_errlist 和 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)。  
  
## <a name="remarks"></a>备注  
 其中每个函数都创建并执行一个新进程，将每个命令行自变量作为单独的参数进行传递，并将一个数组指针传递给环境设置。 这些函数使用 `PATH` 环境变量查找要执行的文件。  
  
 这些函数验证其参数。 如果 `cmdname` 或 `arg0` 是空字符串或 null 指针，则调用的参数处理程序无效，如 [Parameter Validation](../../c-runtime-library/parameter-validation.md)。 如果允许执行继续，则这些功能将 `errno` 设置为 `EINVAL`，并返回 -1。 不生成任何新进程。  
  
## <a name="requirements"></a>要求  
  
|例程|必需的标头|  
|-------------|---------------------|  
|`_spawnlpe`|\<process.h>|  
|`_wspawnlpe`|\<stdio.h> 或 \<wchar.h>|  
  
 有关兼容性的详细信息，请参阅[兼容性](../../c-runtime-library/compatibility.md)。  
  
## <a name="example"></a>示例  
 在参见 [_spawn、_wspawn 函数](../../c-runtime-library/spawn-wspawn-functions.md)中的示例。  
  
## <a name="see-also"></a>另请参阅  
 [进程和环境控制](../../c-runtime-library/process-and-environment-control.md)   
 [_spawn、_wspawn 函数](../../c-runtime-library/spawn-wspawn-functions.md)   
 [abort](../../c-runtime-library/reference/abort.md)   
 [atexit](../../c-runtime-library/reference/atexit.md)   
 [_exec、_wexec 函数](../../c-runtime-library/exec-wexec-functions.md)   
 [exit、_Exit、_exit](../../c-runtime-library/reference/exit-exit-exit.md)   
 [_flushall](../../c-runtime-library/reference/flushall.md)   
 [_getmbcp](../../c-runtime-library/reference/getmbcp.md)   
 [_onexit、_onexit_m](../../c-runtime-library/reference/onexit-onexit-m.md)   
 [_setmbcp](../../c-runtime-library/reference/setmbcp.md)   
 [system、_wsystem](../../c-runtime-library/reference/system-wsystem.md)