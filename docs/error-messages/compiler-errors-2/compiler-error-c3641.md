---
title: "编译器错误 C3641 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3641
dev_langs: C++
helpviewer_keywords: C3641
ms.assetid: e8d3613e-5e8d-46fe-a516-eb7d1de7cd21
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 145d1739752f96b35cbf9af51c81900ab66fe6c4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3641"></a>编译器错误 C3641
function： 无效的使用 /clr 编译的函数调用约定 calling_convention: pure 或 /clr: safe  
  
 **/clr:pure** 和 **/clr:safe** 编译器选项在 Visual Studio 2015 中已弃用。  
  
 仅[__clrcall](../../cpp/clrcall.md)调用约定允许使用[/clr: pure](../../build/reference/clr-common-language-runtime-compilation.md)。  
  
 下面的示例生成 C3641:  
  
```  
// C3641.cpp  
// compile with: /clr:pure /c  
void __cdecl f() {}   // C3641  
```