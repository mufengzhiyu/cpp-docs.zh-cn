---
title: "编译器错误 C3140 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3140"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3140"
ms.assetid: 122f8943-fac3-4db8-a3a8-2c5d19233de6
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 编译器错误 C3140
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

同一编译单元中不能有多个“module”特性  
  
 每个项目只能定义一次 [module](../../windows/module-cpp.md) 特性。  
  
 下面的示例生成 C3140：  
  
```  
// C3140.cpp  
// compile with: /c  
[emitidl];  
[module(name = "MyLibrary")];  
[module(name = "MyLibrary2")];   // C3140  
```