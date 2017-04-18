---
title: "_byteswap_uint64、_byteswap_ulong、_byteswap_ushort | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_byteswap_uint64"
  - "_byteswap_ulong"
  - "_byteswap_ushort"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
  - "api-ms-win-crt-utility-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "byteswap_ulong"
  - "_byteswap_ulong"
  - "byteswap_uint64"
  - "_byteswap_ushort"
  - "_byteswap_uint64"
  - "byteswap_ushort"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_byteswap_uint64 函数"
  - "_byteswap_ulong 函数"
  - "_byteswap_ushort 函数"
  - "字节交换"
  - "字节, 交换"
  - "byteswap_uint64 函数"
  - "byteswap_ulong 函数"
  - "byteswap_ushort 函数"
  - "交换字节"
ms.assetid: 83bda211-f02f-4cf0-8a78-d6de1f175970
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# _byteswap_uint64、_byteswap_ulong、_byteswap_ushort
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

颠倒一个整数的字节顺序。  
  
## 语法  
  
```  
unsigned short _byteswap_ushort (  
   unsigned short val  
);  
unsigned long _byteswap_ulong (  
   unsigned long val  
);  
unsigned __int64 _byteswap_uint64 (  
   unsigned __int64 val  
);  
```  
  
#### 参数  
 `val`  
 整数颠倒字节顺序。  
  
## 要求  
  
|例程|必需的标头|  
|--------|-----------|  
|`_byteswap_ushort`|\<stdlib.h\>|  
|`_byteswap_ulong`|\<stdlib.h\>|  
|`_byteswap_uint64`|\<stdlib.h\>|  
  
 有关更多兼容性信息，请参见“简介”中的[兼容性](../../c-runtime-library/compatibility.md)。  
  
## 示例  
  
```  
// crt_byteswap.c  
#include <stdlib.h>  
  
int main()  
{  
   unsigned __int64 u64 = 0x0102030405060708;  
   unsigned long ul = 0x01020304;  
  
   printf("byteswap of %I64x = %I64x\n", u64, _byteswap_uint64(u64));  
   printf("byteswap of %Ix = %Ix", ul, _byteswap_ulong(ul));  
}  
```  
  
  **102030405060708 \= 807060504030201 交换字节**  
**1020304 \= 4030201 交换字节**   
## 请参阅  
 [按类别分的运行时例程](../../c-runtime-library/run-time-routines-by-category.md)