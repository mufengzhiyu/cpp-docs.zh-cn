---
title: "ML 错误 A1007 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: A1007
dev_langs: C++
helpviewer_keywords: A1007
ms.assetid: bcf9c826-beb3-4e93-91fe-1ffd34995fbf
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 619f1eae458b52eb7851118d6702dccec769a1ca
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="ml-fatal-error-a1007"></a>ML 错误 A1007
**嵌套级别太深**  
  
 汇编程序达到其嵌套限制。 限制为除指明外否则 20 级别。  
  
 下列其中一项已嵌套太深：  
  
-   如高级指令[。如果](../../assembler/masm/dot-if.md)， [。重复](../../assembler/masm/dot-repeat.md)，或[。虽然](../../assembler/masm/dot-while.md)。  
  
-   结构定义。  
  
-   一个条件程序集指令。  
  
-   过程定义。  
  
-   A [PUSHCONTEXT](../../assembler/masm/pushcontext.md)指令 （限制为 10）。  
  
-   段定义。  
  
-   包含文件。  
  
-   宏。  
  
## <a name="see-also"></a>请参阅  
 [ML 错误消息](../../assembler/masm/ml-error-messages.md)