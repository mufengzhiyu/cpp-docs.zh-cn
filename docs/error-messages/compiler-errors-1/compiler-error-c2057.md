---
title: "编译器错误 C2057 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2057
dev_langs: C++
helpviewer_keywords: C2057
ms.assetid: 038a99d6-1f5a-42fa-8449-03b4ff11ee0b
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 12cf150a5c9ea866c195f3b7366a9ff9608bc10f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2057"></a>编译器错误 C2057
应输入常量表达式  
  
 该上下文要求输入常数表达式，即其值在编译时已知的表达式。  
  
 编译器在编译时必须知道类型的大小，以便为该类型的实例分配空间。  
  
## <a name="example"></a>示例  
 下面的示例生成 C2057，并演示如何修复此错误：  
  
```  
// C2057.cpp  
int i;  
int b[i];   // C2057 - value of i is unknown at compile time  
int main() {  
   const int i = 8;  
   int b[i]; // OK - value of i is fixed and known to compiler  
}  
```  
  
## <a name="example"></a>示例  
 C 对常数表达式有限制性更强的规则。  下面的示例生成 C2057，并演示如何修复此错误：  
  
```  
// C2057b.c  
#define ArraySize1 10  
int main() {   
   const int ArraySize2 = 10;   
   int h[ArraySize2];   // C2057 - C does not allow variables here  
   int h[ArraySize1];   // OK - uses preprocessor constant  
}  
```