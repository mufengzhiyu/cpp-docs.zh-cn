---
title: "mbtowc、_mbtowc_l | Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- mbtowc
- _mbtowc_l
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
- api-ms-win-crt-multibyte-l1-1-0.dll
apitype: DLLExport
f1_keywords: mbtowc
dev_langs: C++
helpviewer_keywords:
- mbtowc function
- _mbtowc_l function
- mbtowc_l function
ms.assetid: dfd1c8a7-e73a-4307-9353-53b70b45d4d1
caps.latest.revision: "16"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 52f2c1d3defb822f00095a24bfcc87bd07fc8cc4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="mbtowc-mbtowcl"></a>mbtowc、_mbtowc_l
将多字节字符转换为相应的宽字符。  
  
## <a name="syntax"></a>语法  
  
```  
int mbtowc(  
   wchar_t *wchar,  
   const char *mbchar,  
   size_t count   
);  
int _mbtowc_l(  
   wchar_t *wchar,  
   const char *mbchar,  
   size_t count,  
   _locale_t locale  
);  
```  
  
#### <a name="parameters"></a>参数  
 *wchar*  
 宽字符的地址（类型 `wchar_t`）。  
  
 `mbchar`  
 字节（多字节字符）序列的地址。  
  
 *count*  
 要检查的字节数。  
  
 *locale*  
 要使用的区域设置。  
  
## <a name="return-value"></a>返回值  
 如果 **mbchar** 不是 **NULL** 并且如果 `mbchar` 指向的对象构成了有效的多字节字符，则 `mbtowc` 返回多字节字符的长度（以字节为单位）。 如果 `mbchar` 是 **NULL** 或其指向的对象是宽字符空字符 (L'\0')，则此函数返回 0。 如果该对象的`mbchar`指向未形成有效的多字节字符，在第一个*计数*字符，则返回-1。  
  
## <a name="remarks"></a>备注  
 如果 `mbchar` 不是 **NULL**，则 `mbtowc` 函数将 `mbchar` 指向的 *count* 个或更少的字节转换为相应的宽字符。 如果 *wchar* 不是 **NULL**，则 `mbtowc` 将生成的宽字符存储在 *wchar* 中。 `mbtowc` 检查的字节数不超过 `MB_CUR_MAX`。 `mbtowc` 将当前区域设置用于与区域设置相关的行为；`_mbtowc_l` 也是一样，只不过它使用传入的区域设置。 有关详细信息，请参阅 [Locale](../../c-runtime-library/locale.md)。  
  
## <a name="requirements"></a>惠?  
  
|例程所返回的值|必需的标头|  
|-------------|---------------------|  
|`mbtowc`|\<stdlib.h>|  
|**_mbtowc_l**|\<stdlib.h>|  
  
 有关其他兼容性信息，请参见“简介”中的 [兼容性](../../c-runtime-library/compatibility.md) 。  
  
## <a name="libraries"></a>库  
 [C 运行时库](../../c-runtime-library/crt-library-features.md)的所有版本。  
  
## <a name="example"></a>示例  
  
```  
// crt_mbtowc.c  
/* Illustrates the behavior of the mbtowc function  
 */  
  
#include <stdlib.h>  
#include <stdio.h>  
  
int main( void )  
{  
    int      i;  
    char    *pmbc    = (char *)malloc( sizeof( char ) );  
    wchar_t  wc      = L'a';  
    wchar_t *pwcnull = NULL;  
    wchar_t *pwc     = (wchar_t *)malloc( sizeof( wchar_t ) );  
    printf( "Convert a wide character to multibyte character:\n" );  
    wctomb_s( &i, pmbc, sizeof(char), wc );  
    printf( "  Characters converted: %u\n", i );  
    printf( "  Multibyte character: %x\n\n", *pmbc );  
  
    printf( "Convert multibyte character back to a wide "  
            "character:\n" );  
    i = mbtowc( pwc, pmbc, MB_CUR_MAX );  
    printf( "  Bytes converted: %u\n", i );  
    printf( "  Wide character: %x\n\n", *pwc );  
    printf( "Attempt to convert when target is NULL\n" );  
    printf( "  returns the length of the multibyte character:\n" );  
    i = mbtowc( pwcnull, pmbc, MB_CUR_MAX );  
    printf( "  Length of multibyte character: %u\n\n", i );  
  
    printf( "Attempt to convert a NULL pointer to a" );  
    printf( " wide character:\n" );  
    pmbc = NULL;  
    i = mbtowc( pwc, pmbc, MB_CUR_MAX );  
    printf( "  Bytes converted: %u\n", i );  
}  
```  
  
## <a name="output"></a>输出  
  
```  
Convert a wide character to multibyte character:  
  Characters converted: 1  
  Multibyte character: 61  
  
Convert multibyte character back to a wide character:  
  Bytes converted: 1  
  Wide character: 61  
  
Attempt to convert when target is NULL  
  returns the length of the multibyte character:  
  Length of multibyte character: 1  
  
Attempt to convert a NULL pointer to a wide character:  
  Bytes converted: 0  
```  
  
## <a name="see-also"></a>请参阅  
 [数据转换](../../c-runtime-library/data-conversion.md)   
 [MultiByteToWideChar](http://msdn.microsoft.com/library/windows/desktop/dd319072)   
 [区域设置](../../c-runtime-library/locale.md)   
 [多字节字符序列的解释](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [_mbclen、mblen、_mblen_l](../../c-runtime-library/reference/mbclen-mblen-mblen-l.md)   
 [wcstombs、_wcstombs_l](../../c-runtime-library/reference/wcstombs-wcstombs-l.md)   
 [wctomb、_wctomb_l](../../c-runtime-library/reference/wctomb-wctomb-l.md)