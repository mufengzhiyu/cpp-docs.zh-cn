---
title: "编译器错误 C3003 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3003
dev_langs: C++
helpviewer_keywords: C3003
ms.assetid: 22e74f99-bb7f-4518-ab0d-934d5d49bcc7
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 26d6a2199dbf2ff6fb3d0a1381914fde0aa722bb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3003"></a>编译器错误 C3003
“directive”：在指令子句之后不允许使用 OpenMP 指令名称  
  
 OpenMP 指令名称不能位于 OpenMP 指令子句之后。  
  
 下面的示例生成 C3003：  
  
```  
// C3003.c  
// compile with: /openmp  
int main()  
{  
   int x, y, z;  
   #pragma omp parallel shared(x, y, z) for   // C3003  
}  
```