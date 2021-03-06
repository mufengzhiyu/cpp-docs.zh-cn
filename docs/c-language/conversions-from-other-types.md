---
title: "从其他类型的转换 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- values, converting
- type casts, conversion
ms.assetid: 30fbd974-8f5a-4b70-ac44-d3937b96b702
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8dbf2d3d269f5df3a028a5c416f8adca015be6dd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="conversions-from-other-types"></a>从其他类型的转换
由于 `enum` 值根据定义属于 `int` 值，因此 `enum` 值的转换目标和源与 `int` 类型的值的相同。 对于 Microsoft C 编译器，整数与 long 相同。  
  
 **Microsoft 专用**  
  
 结构或联合类型之间不允许转换。  
  
 任何值都可转换为类型 `void`，但此类转换的结果只能在将丢弃表达式值的上下文中使用，如在表达式语句中。  
  
 根据定义，`void` 类型没有值。 因此，它不能转换为任何其他类型，并且其他类型不能通过赋值转换为 `void`。 但是，可显式将值强制转换为类型 `void`，如[类型强制转换](../c-language/type-cast-conversions.md)中所述。  
  
 **结束 Microsoft 专用**  
  
## <a name="see-also"></a>请参阅  
 [赋值转换](../c-language/assignment-conversions.md)