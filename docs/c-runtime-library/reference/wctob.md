---
title: "wctob | Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: wctob
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
- api-ms-win-crt-convert-l1-1-0.dll
apitype: DLLExport
f1_keywords: wctob
dev_langs: C++
helpviewer_keywords:
- wide characters, converting
- wctob function
- characters, converting
ms.assetid: 46aec98b-c2f2-4e9d-9d89-7db99ba8a9a6
caps.latest.revision: "14"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ae0b23c099bb681b43daf4b61af84a52bba24982
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="wctob"></a>wctob
确定宽字符对应多字节字符，并返回该多字节字符的表示形式。  
  
## <a name="syntax"></a>语法  
  
```  
int wctob(  
   wint_t wchar  
);  
```  
  
#### <a name="parameters"></a>参数  
 `wchar`  
 要转换的值。  
  
## <a name="return-value"></a>返回值  
 如果 `wctob` 成功转换宽字符，仅在多字节字符正好为一个字节长时返回该字符的表示形式。 如果`wctob`遇到它不能将其转换为多字节字符或多字节字符的宽字符不完全是 1 个字节长，它将返回-1。  
  
## <a name="remarks"></a>备注  
 如果多字节字符正好为一个字节长，`wctob` 函数会将 `wchar` 中的宽字符转换为 `int` 返回值传递的相应多字节字符。  
  
 如果 `wctob` 失败且未找到相应的多字节字符，该函数会将 `errno` 设置为 `EILSEQ` 并返回 -1。  
  
## <a name="requirements"></a>惠?  
  
|例程所返回的值|必需的标头|  
|-------------|---------------------|  
|`wctob`|\<wchar.h>|  
  
 有关其他兼容性信息，请参见“简介”中的 [兼容性](../../c-runtime-library/compatibility.md) 。  
  
## <a name="example"></a>示例  
 本程序演示 `wcstombs` 函数的行为。  
  
```  
// crt_wctob.c  
#include <stdio.h>  
#include <wchar.h>  
  
int main( void )  
{  
    int     bChar = 0;  
    wint_t  wChar = 0;  
  
    // Set the corresponding wide character to exactly one byte.  
    wChar = (wint_t)'A';  
  
    bChar = wctob( wChar );  
    if (bChar == WEOF)  
    {  
        printf( "No corresponding multibyte character was found.\n");  
    }  
    else  
    {  
        printf( "Determined the corresponding multibyte character to"  
                " be \"%c\".\n", bChar);  
    }  
}  
  
```  
  
```Output  
Determined the corresponding multibyte character to be "A".  
```  
  
## <a name="see-also"></a>请参阅  
 [数据转换](../../c-runtime-library/data-conversion.md)   
 [区域设置](../../c-runtime-library/locale.md)   
 [_mbclen、mblen、_mblen_l](../../c-runtime-library/reference/mbclen-mblen-mblen-l.md)   
 [mbstowcs、_mbstowcs_l](../../c-runtime-library/reference/mbstowcs-mbstowcs-l.md)   
 [mbtowc、_mbtowc_l](../../c-runtime-library/reference/mbtowc-mbtowc-l.md)   
 [wctomb、_wctomb_l](../../c-runtime-library/reference/wctomb-wctomb-l.md)   
 [WideCharToMultiByte](http://msdn.microsoft.com/library/windows/desktop/dd374130)