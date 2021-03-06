---
title: "__rdtsc |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: __rdtsc
dev_langs: C++
helpviewer_keywords:
- __rdtsc intrinsic
- rdtsc instruction
- Read Time Stamp Counter instruction
ms.assetid: e31d0e51-c9bb-42ca-bbe9-a81ffe662387
caps.latest.revision: "17"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: bd108c36dc60f6186d247cd3cf61d27d1dad3239
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="rdtsc"></a>__rdtsc
**Microsoft 专用**  
  
 生成`rdtsc`指令，返回的处理器时间戳。 处理器时间戳记录上次重置后的时钟周期数。  
  
## <a name="syntax"></a>语法  
  
```  
unsigned __int64 __rdtsc();  
```  
  
## <a name="return-value"></a>返回值  
 一个 64 位无符号的整型，表示滴答计数。  
  
## <a name="requirements"></a>惠?  
  
|内部函数|体系结构|  
|---------------|------------------|  
|`__rdtsc`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **标头文件** \<intrin.h >  
  
## <a name="remarks"></a>备注  
 此例程是仅用作内部函数。  
  
 在这一代的硬件 TSC 值的解释不同于在早期版本的[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]。 请参阅硬件手册，以获得详细信息。  
  
## <a name="example"></a>示例  
  
```  
// rdtsc.cpp  
// processor: x86, x64  
#include <stdio.h>  
#include <intrin.h>  
  
#pragma intrinsic(__rdtsc)  
  
int main()  
{  
    unsigned __int64 i;  
    i = __rdtsc();  
    printf_s("%I64d ticks\n", i);  
}  
```  
  
```Output  
3363423610155519 ticks  
```  
  
**结束 Microsoft 专用**  
  
## <a name="see-also"></a>请参阅  
 [编译器内部函数](../intrinsics/compiler-intrinsics.md)