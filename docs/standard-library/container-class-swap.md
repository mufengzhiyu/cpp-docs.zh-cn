---
title: "Container Class::swap | Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: swap method
ms.assetid: 898c219c-bc8e-4d14-a149-6240426c693f
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 09229429c64e895a722d52d203f0259cf69e6d24
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="container-classswap"></a>Container Class::swap
> [!NOTE]
>  本主题位于 Visual C++ 文档内，作为在 C++ 标准库内使用的容器的非功能性示例。 有关详细信息，请参阅 [C++ 标准库容器](../standard-library/stl-containers.md)。  
  
交换 **\*this** 和其参数之间的受控序列。  
  
## <a name="syntax"></a>语法  
  
```  
void swap(Container& right);
```  
  
## <a name="remarks"></a>备注  
如果 **\*this.get\_ 分配器 ==** _right_ **.get_allocator**，它将在常量时间内执行交换。 否则，它所执行的元素分配和构造函数调用数量会与两个受控序列中的元素数量成正比。  
  
## <a name="see-also"></a>请参阅  
[Sample Container 类](../standard-library/sample-container-class.md)
