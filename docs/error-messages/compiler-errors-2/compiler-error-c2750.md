---
title: "编译器错误 C2750 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2750
dev_langs: C++
helpviewer_keywords: C2750
ms.assetid: 30450034-feb5-448c-9655-b8c5f3639695
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 96f66115c2e51a7ed49cc20c6b5da94a61cab555
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2750"></a>编译器错误 C2750
type： 不能使用引用类型; 上的 new请改用 gcnew  
  
 若要创建的是 CLR 类型，它将导致要放置在垃圾回收堆上的实例，实例必须使用[gcnew](../../windows/ref-new-gcnew-cpp-component-extensions.md)。  
  
 下面的示例生成 C2750:  
  
```  
// C2750.cpp  
// compile with: /clr  
ref struct Y1 {};  
  
int main() {  
   Y1 ^ x = new Y1;   // C2750  
  
   // try the following line instead  
   Y1 ^ x2 = gcnew Y1;  
}  
```