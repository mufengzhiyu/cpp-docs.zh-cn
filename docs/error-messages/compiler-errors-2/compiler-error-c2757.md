---
title: "编译器错误 C2757 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2757
dev_langs: C++
helpviewer_keywords: C2757
ms.assetid: 421f102f-8a32-4d47-a109-811ddf2c909d
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6100e413c599a9aa6300e6cd7c675c6e2b156178
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2757"></a>编译器错误 C2757
symbol： 已存在具有此名称的符号，因此此名称不能用作命名空间名称  
  
 中引用的程序集中已使用的命名空间标识符作为当前的编译中使用的符号。  
  
 下面的示例生成 C2757:  
  
```  
// C2757a.cpp  
// compile with: /clr /LD  
public ref class Nes {};  
```  
  
 然后，  
  
```  
// C2757b.cpp  
// compile with: /clr /c  
#using <C2757a.dll>  
  
namespace Nes {    // C2757  
// try the following line instead  
// namespace Nes2 {  
   public ref class X {};  
}  
```  
