---
title: "定义规则 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- NMAKE program, inference rules
- defining inference rules
ms.assetid: 071cd092-3f2e-4065-b0fb-36a9d393cfa8
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c0d6ca616e3685db36d6d24b339a860eab4c6150
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="defining-a-rule"></a>定义规则
*Fromext*表示是依赖文件的扩展和*toext*表示目标文件的扩展名。  
  
```  
.fromext.toext:  
   commands  
```  
  
## <a name="remarks"></a>备注  
 扩展不区分大小写。 可以调用宏以表示*fromext*和*toext*; 宏展开在预处理过程。 句点 （.） 前面*fromext*必须出现在行的开头。 冒号 （:） 前面是零个或多个空格或制表符。 它可以后面只能跟空格或制表符、 分号 （;） 以指定的命令，以数字符号 （#） 来指定注释或换行字符。 不允许有其他任何空格。 同描述块一样指定的命令。  
  
## <a name="what-do-you-want-to-know-more-about"></a>你想进一步了解什么？  
 [规则中的搜索路径](../build/search-paths-in-rules.md)  
  
## <a name="see-also"></a>请参阅  
 [推理规则](../build/inference-rules.md)