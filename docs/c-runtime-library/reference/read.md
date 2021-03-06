---
title: "_read | Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _read
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
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords: _read
dev_langs: C++
helpviewer_keywords:
- data [CRT]
- _read function
- read function
- data [C++], reading
- reading data [C++]
- files [C++], reading
ms.assetid: 2ce9c433-57ad-47fe-9ac1-4a7d4c883d30
caps.latest.revision: "15"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 2473dcac2d737d8419a90f4f8e7a47939065f3be
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2017
---
# <a name="read"></a>_read

从文件读取数据。  
  
## <a name="syntax"></a>语法  
  
```  
int _read(  
   int fd,  
   void *buffer,  
   unsigned int count   
);  
```  
  
### <a name="parameters"></a>参数  

*fd*  
引用打开的文件的文件说明符。  
  
*buffer*  
数据的存储位置。  
  
*count*  
最大字节数。  
  
## <a name="return-value"></a>返回值  

`_read`返回读取，这可能会更少的字节数比*计数*如果少于*计数*字节留在文件中，或如果在文本模式下打开该文件，在此情况下每个回车符返回行源对`\r\n`使用单一的换行的字符替换`\n`。 在返回值中仅计算单个换行符。 此替换不影响文件指针。  
  
如果函数尝试在文件末尾进行读取，则返回 0。 如果*fd*是无效，文件不是将打开以便读取，或文件被锁定，则调用无效参数处理程序，如中所述[参数验证](../../c-runtime-library/parameter-validation.md)。 如果允许执行继续，则该函数将返回 -1 并将 `errno` 设置为 `EBADF`。  
  
如果 *buffer* 为 **NULL**，则将调用无效的参数处理程序。 如果允许执行继续，则函数将返回 -1 并将 `errno` 设置为 `EINVAL`。  
  
有关此代码以及其他返回代码的详细信息，请参阅 [_doserrno、errno、_sys_errlist 和 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)。  
  
## <a name="remarks"></a>备注  

`_read`函数将读取的最多*计数*字节写入*缓冲区*与关联的文件从*fd*。 读取操作从与给定文件相关联的文件指针的当前位置开始执行。 读取操作完成后，文件指针将指向下一个未读取的字符。  
  
如果文件是在文本模式下打开的，则在 `_read` 遇到 CTRL+Z 字符（被视为文件尾指示符）时，读取将终止。 使用 [_lseek](../../c-runtime-library/reference/lseek-lseeki64.md) 可清除文件尾指示符。  
  
## <a name="requirements"></a>要求  
  
|例程|必需的标头|  
|-------------|---------------------|  
|`_read`|\<io.h>|  
  
有关兼容性的详细信息，请参阅[兼容性](../../c-runtime-library/compatibility.md)。  
  
## <a name="libraries"></a>库  

[C 运行时库](../../c-runtime-library/crt-library-features.md)的所有版本。  
  
## <a name="example"></a>示例  
  
```C  
// crt_read.c  
/* This program opens a file named crt_read.txt  
 * and tries to read 60,000 bytes from  
 * that file using _read. It then displays the  
 * actual number of bytes read.  
 */  
  
#include <fcntl.h>      /* Needed only for _O_RDWR definition */  
#include <io.h>  
#include <stdlib.h>  
#include <stdio.h>  
#include <share.h>  
  
char buffer[60000];  
  
int main( void )  
{  
   int fh;  
   unsigned int nbytes = 60000, bytesread;  
  
   /* Open file for input: */  
   if( _sopen_s( &fh, "crt_read.txt", _O_RDONLY, _SH_DENYNO, 0 ) )  
   {  
      perror( "open failed on input file" );  
      exit( 1 );  
   }  
  
   /* Read in input: */  
   if( ( bytesread = _read( fh, buffer, nbytes ) ) <= 0 )  
      perror( "Problem reading file" );  
   else  
      printf( "Read %u bytes from file\n", bytesread );  
  
   _close( fh );  
}  
```  
  
### <a name="input-crtreadtxt"></a>输入：crt_read.txt  
  
```  
Line one.  
Line two.  
```  
  
### <a name="output"></a>输出  
  
```  
Read 19 bytes from file  
```  
  
## <a name="see-also"></a>另请参阅  

[低级别 I/O](../../c-runtime-library/low-level-i-o.md)   
[_creat、_wcreat](../../c-runtime-library/reference/creat-wcreat.md)   
[fread](../../c-runtime-library/reference/fread.md)   
[_open、_wopen](../../c-runtime-library/reference/open-wopen.md)   
[_write](../../c-runtime-library/reference/write.md)
