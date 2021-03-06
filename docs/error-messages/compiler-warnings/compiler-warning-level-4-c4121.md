---
title: "编译器警告 （等级 4） 了 C4121 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4121
dev_langs: C++
helpviewer_keywords: C4121
ms.assetid: 8c5b85c9-2543-426b-88bc-319c50158c7e
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4886f8274ed8813cf556529efe657dca786f0e36
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4121"></a>编译器警告 （等级 4） 了 C4121
“符号”：成员的对齐方式对封装敏感  
  
 编译器添加了填充以在封装边界对齐结构成员，但封装值小于该成员的大小。 例如，以下代码片段生成了 C4121：  
  
```  
// C4121.cpp  
// compile with: /W4 /c  
#pragma pack(2)  
struct s  
{  
   char a;  
   int b; // C4121  
   long long c;  
};  
```  
  
 若要修复此问题，请作出以下更改之一：  
  
-   将封装大小更改为导致警告的成员的大小或更大。 例如，在此代码片段中，将 `pack(2)` 更改为 `pack(4)` 或 `pack(8)`。  
  
-   按大小对成员声明进行重新排序（从大到小）。 在代码片段中，反转结构成员的顺序，使 `long long` 位于 `int` 前面，并使 `int` 位于 `char` 前面。  
  
 仅当编译器在数据成员前添加填充时，此警告才出现。 当封装已在没有针对数据类型对齐的内存位置放置数据，但数据成员前没有放置填充时，将出现此警告。 如果某些边界的大小是某个数据在大小的倍数，但该数据未在这些边界上对齐，则性能可能会降低。 未对齐的数据的读取和写入会导致某些体系结构中出现处理器错误，可能需要多用两三个数量级的时间来解决该错误。 未对齐的数据访问无法移植到某些 RISC 体系结构。  
  
 你可以使用[#pragma 包](../../preprocessor/pack.md)或[/Zp](../../build/reference/zp-struct-member-alignment.md)指定结构的对齐方式。 (编译器不会生成此警告**/Zp1**指定。)