---
title: "编译器错误 C2253 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2253
dev_langs: C++
helpviewer_keywords: C2253
ms.assetid: bd6445ae-b2c1-4669-9657-a8f4acf80b16
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 11c9a7a1a11daa58b6046fdc0a8f6bbdabb9c039
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2253"></a>编译器错误 C2253
function： 纯说明符或抽象重写说明符仅允许对虚拟函数  
  
 非虚拟函数被指定为纯`virtual`。  
  
 下面的示例生成 C2253:  
  
```  
// C2253.cpp  
// compile with: /c  
class A {  
public:  
   void func1() = 0;   // C2253 not virtual  
   virtual void func2() = 0;   // OK  
};  
```  
  
 下面的示例生成 C2253:  
  
```  
// C2253_2.cpp  
// compile with: /clr /c  
ref struct A {  
   property int Prop_3 {  
      int get() abstract;   // C2253  
      // try the following line instead  
      // virtual int get() abstract;  
  
      void set(int i) abstract;   // C2253  
      // try the following line instead  
      // virtual void set(int i) abstract;  
   }  
};  
```