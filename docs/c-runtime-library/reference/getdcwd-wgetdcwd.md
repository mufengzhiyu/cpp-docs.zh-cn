---
title: "_getdcwd、_wgetdcwd | Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _getdcwd
- _wgetdcwd
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
f1_keywords:
- wgetdcwd
- getdcwd
- _getdcwd
- tgetdcwd
- _wgetdcwd
- _tgetdcwd
dev_langs: C++
helpviewer_keywords:
- wgetdcwd function
- working directory
- getdcwd function
- _getdcwd function
- _wgetdcwd function
- current working directory
- directories [C++], current working
ms.assetid: 184152f5-c7b0-495b-918d-f9a6adc178bd
caps.latest.revision: "24"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e314db740322fc3d5e7df5aeb6bd7de747e77695
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/03/2018
---
# <a name="getdcwd-wgetdcwd"></a>_getdcwd、_wgetdcwd
在指定的驱动器上获取当前工作目录的完整路径。  
  
## <a name="syntax"></a>语法  
  
```  
char *_getdcwd(   
   int drive,  
   char *buffer,  
   int maxlen   
);  
wchar_t *_wgetdcwd(   
   int drive,  
   wchar_t *buffer,  
   int maxlen   
);  
```  
  
#### <a name="parameters"></a>参数  
 `drive`  
 一个指定驱动器的非负整数（0 = 默认驱动器，1 = A，2 = B，依此类推）。  
  
 如果指定的驱动器不可用，或者无法确定驱动器的类型（例如，可移动的、固定的、CD-ROM、RAM 磁盘或网络驱动器），则会调用 [Parameter Validation](../../c-runtime-library/parameter-validation.md)中介绍的无效参数处理程序。  
  
 `buffer`  
 路径的存储位置，或为 **NULL**。  
  
 如果指定 **NULL** ，则此函数会使用 `maxlen` 分配至少 **malloc**大小的缓冲区，并且 `_getdcwd` 的返回值是指向分配的缓冲区的指针。 可通过调用 `free` 并为其传递指针来释放缓冲区。  
  
 `maxlen`  
 一个指定路径的最大长度（以字符为单位）的非零正整数： `char` 的 `_getdcwd` 和 `wchar_t` 的 `_wgetdcwd`。  
  
 如果 `maxlen` 不大于零，则会调用[参数验证](../../c-runtime-library/parameter-validation.md)中所述的无效参数处理程序。  
  
## <a name="return-value"></a>返回值  
 指向字符串的指针，该字符串表示指定驱动器上当前工作目录的完整路径，或指示错误的 `NULL`。  
  
 如果将 `buffer` 指定为 `NULL` 且内存不足而无法分配 `maxlen` 字符，则会出现错误且 `errno` 将设置为 `ENOMEM`。 如果包含终止 null 字符的路径的长度超过 `maxlen`，则会出现错误且 `errno` 将设置为 `ERANGE`。 有关这些错误代码的详细信息，请参阅 [errno、_doserrno、_sys_errlist 和 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)。  
  
## <a name="remarks"></a>备注  
 `_getdcwd` 函数将获取指定驱动器上当前工作目录的完整路径，并将其存储在 `buffer`中。 如果当前工作目录设置为根目录，则字符串以反斜杠 (\\) 结尾。 如果当前工作目录设置为根目录之外的目录，则字符串以该目录的名称结尾，而不是以反斜杠结尾。  
  
 `_wgetdcwd` 是 `_getdcwd`的宽字符版本，并且其 `buffer` 参数和返回值都是宽字符字符串。 除此以外，`_wgetdcwd` 和 `_getdcwd` 的行为完全相同。  
  
 此函数是线程安全的，即使它依赖于本身不是线程安全的 **GetFullPathName**。 但是，如果你的多线程应用程序调用此函数和 **GetFullPathName**，则可以违反线程安全性。 有关详细信息，请转到 [MSDN 库](http://go.microsoft.com/fwlink/p/?linkid=150542)，然后搜索 **GetFullPathName**。  
  
 具有 `_nolock` 后缀的此函数版本与此函数的行为相同，但它不是线程安全的，并且会受到其他线程的影响。 有关详细信息，请参阅 [_getdcwd_nolock, _wgetdcwd_nolock](../../c-runtime-library/reference/getdcwd-nolock-wgetdcwd-nolock.md)。  
  
 在定义 `_DEBUG` 和 `_CRTDBG_MAP_ALLOC` 时，对 `_getdcwd` 和 `_wgetdcwd` 的调用将替换为对 `_getdcwd_dbg` 和 `_wgetdcwd_dbg` 的调用，以便你能够调试内存分配。 有关详细信息，请参阅[_getdcwd_dbg, _wgetdcwd_dbg](../../c-runtime-library/reference/getdcwd-dbg-wgetdcwd-dbg.md)。  
  
### <a name="generic-text-routine-mappings"></a>一般文本例程映射  
  
|Tchar.h 例程|未定义 _UNICODE 和 _MBCS|已定义 _MBCS|已定义 _UNICODE|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tgetdcwd`|`_getdcwd`|`_getdcwd`|`_wgetdcwd`|  
  
## <a name="requirements"></a>惠?  
  
|例程所返回的值|必需的标头|  
|-------------|---------------------|  
|`_getdcwd`|\<direct.h>|  
|`_wgetdcwd`|\<direct.h> 或 \<wchar.h>|  
  
 有关更多兼容性信息，请参阅 [兼容性](../../c-runtime-library/compatibility.md)。  
  
## <a name="example"></a>示例  
 请参见 [_getdrive](../../c-runtime-library/reference/getdrive.md)中的示例。  
  
## <a name="see-also"></a>请参阅  
 [目录控制](../../c-runtime-library/directory-control.md)   
 [_chdir、_wchdir](../../c-runtime-library/reference/chdir-wchdir.md)   
 [_getcwd、_wgetcwd](../../c-runtime-library/reference/getcwd-wgetcwd.md)   
 [_getdrive](../../c-runtime-library/reference/getdrive.md)   
 [_mkdir、_wmkdir](../../c-runtime-library/reference/mkdir-wmkdir.md)   
 [_rmdir、_wrmdir](../../c-runtime-library/reference/rmdir-wrmdir.md)