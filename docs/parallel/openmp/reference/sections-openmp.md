---
title: "部分 (OpenMP) |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- section
- SECTIONS
dev_langs: C++
helpviewer_keywords: sections OpenMP directive
ms.assetid: 4cd1d776-e198-470e-930a-01fb0ab0a0bd
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 458d62bf17ce7f8778e40a4e90592aa59ba09e4c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="sections-openmp"></a>sections (OpenMP)
标识要作为被除数所有线程间的代码部分。  
  
## <a name="syntax"></a>语法  
  
```  
#pragma omp [parallel] sections [clauses]  
{  
   #pragma omp section  
   {  
      code_block   
   }   
}  
```  
  
## <a name="remarks"></a>备注  
 其中，  
  
 `clause`（可选）  
 零个或多个子句。 请参阅支持的子句列表的备注部分**部分**。  
  
## <a name="remarks"></a>备注  
 **部分**指令都可以包含零个或多**部分**指令。  
  
 **部分**指令支持以下 OpenMP 子句：  
  
-   [firstprivate](../../../parallel/openmp/reference/firstprivate.md)  
  
-   [lastprivate](../../../parallel/openmp/reference/lastprivate.md)  
  
-   [nowait](../../../parallel/openmp/reference/nowait.md)  
  
-   [专用](../../../parallel/openmp/reference/private-openmp.md)  
  
-   [reduction](../../../parallel/openmp/reference/reduction.md)  
  
 如果**并行**同时指定，则`clause`可以会被接受的任何子句**并行**或**部分**指令，除`nowait`。  
  
 有关详细信息，请参阅[2.4.2 sections 构造](../../../parallel/openmp/2-4-2-sections-construct.md)。  
  
## <a name="example"></a>示例  
  
```  
// omp_sections.cpp  
// compile with: /openmp   
#include <stdio.h>  
#include <omp.h>  
  
int main() {  
    #pragma omp parallel sections num_threads(4)  
    {  
        printf_s("Hello from thread %d\n", omp_get_thread_num());  
        #pragma omp section  
        printf_s("Hello from thread %d\n", omp_get_thread_num());  
    }  
}  
```  
  
```Output  
Hello from thread 0  
Hello from thread 0  
```  
  
## <a name="see-also"></a>请参阅  
 [指令](../../../parallel/openmp/reference/openmp-directives.md)