---
title: "C 语句概述 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- semicolon, in C statements
- statements, C
- semicolon
- statements, about statements
- Visual C, statements
ms.assetid: 0d49837a-5399-4881-b60c-af5f4e9720de
caps.latest.revision: 8
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: 040cc7a1718975285088fb0d1a7474cc72a5c4d8
ms.contentlocale: zh-cn
ms.lasthandoff: 05/18/2017

---
# <a name="overview-of-c-statements"></a>C 语句概述
C 语句由标记、表达式和其他语句组成。 构成另一个语句的组成部分的语句称为封闭语句的“体”。 本节中将讨论以下语法给定的每个语句类型。  
  
## <a name="syntax"></a>语法  
 statement：  
labeled-statement [](../c-language/goto-and-labeled-statements-c.md)  
  
 compound-statement[](../c-language/compound-statement-c.md)  
  
 expression-statement[](../c-language/expression-statement-c.md)  
  
 selection-statement[](../c-language/if-statement-c.md)  
  
 iteration-statement[](../c-language/do-while-statement-c.md)  
  
 [jump-statement](../c-language/break-statement-c.md)  
  
 [try-except-statement](../c-language/try-except-statement-c.md)  
  
 /* Microsoft 专用 \*/[try-finally-statement](../c-language/try-finally-statement-c.md) /\* Microsoft 专用 \*/  
  
 通常，语句体为“复合语句”。 复合语句由可包含关键字的其他语句组成。 复合语句由大括号 ({ }) 分隔。 所有其他 C 语句以分号 (;) 结尾。 分号是语句结束符。  
  
 表达式语句包含可包含[表达式和赋值](../c-language/expressions-and-assignments.md)中介绍的算术或逻辑运算符的 C 表达式。 null 语句是空语句。  
  
 所有 C 语句都可以以由名称和冒号组成的标识标签开头。 由于只有 `goto` 语句可识别语句标签，因此语句标签将与 `goto` 一起讨论。 有关详细信息，请参阅 [goto 和标记语句](../c-language/goto-and-labeled-statements-c.md)。  
  
## <a name="see-also"></a>另请参阅  
 [语句](../c-language/statements-c.md)