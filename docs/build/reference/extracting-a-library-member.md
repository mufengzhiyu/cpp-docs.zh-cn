---
title: "提取库成员 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: Lib
dev_langs: C++
helpviewer_keywords:
- LIB [C++], extracting library members
- EXTRACT library manager option
- libraries, extracting members
- -EXTRACT library manager option
- extracting library members
- /EXTRACT library manager option
ms.assetid: a2c5c2a1-9b7e-489a-a9a4-1dec694e1fc5
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 38f45463bb76f858d1b88c059de57a4b8b86227e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="extracting-a-library-member"></a>提取库成员
LIB 可用于创建对象 (.obj) 文件包含的一个成员的现有库的副本。 若要提取的成员的副本，请使用以下语法：  
  
```  
LIB library /EXTRACT:member /OUT:objectfile  
```  
  
 此命令创建的.obj 文件中调用*objectfile* ，其中包含一份`member`的*库*。 `member`名称是区分大小写。 你可以提取单个命令中的只有一个成员。 /OUT 选项是必需的;没有默认输出名称。 如果文件调用*objectfile*指定目录中已存在 (或当前目录中，如果没有目录指定与*objectfile*)，提取*objectfile*替换现有文件。  
  
## <a name="see-also"></a>请参阅  
 [LIB 引用](../../build/reference/lib-reference.md)