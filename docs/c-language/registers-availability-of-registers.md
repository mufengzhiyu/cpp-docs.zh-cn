---
title: "寄存器：寄存器的可用性 | Microsoft Docs"
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
- registers
ms.assetid: f6654e53-742c-4a30-8620-1a4d436a6ae4
caps.latest.revision: 7
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
ms.openlocfilehash: 86ccb4a64287e3d0e51b5f34a6b6066ed60099a9
ms.contentlocale: zh-cn
ms.lasthandoff: 05/18/2017

---
# <a name="registers-availability-of-registers"></a>寄存器：寄存器的可用性
**ANSI 3.5.1** 通过使用寄存器存储类说明符可将对象实际放置在寄存器中的范围  
  
 编译器不接受对寄存器变量的用户请求。 相反，在进行优化时，它将自行做出选择。  
  
## <a name="see-also"></a>另请参阅  
 [实现定义的行为](../c-language/implementation-defined-behavior.md)