---
title: "推断出的依赖项 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- inferred dependents in NMAKE
- dependents, inferred
ms.assetid: 9303045c-69b3-4f35-bffc-19d5cd6ea3c3
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 410e52dd9ee9605f6e29b81491bda0f4883e1cf9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="inferred-dependents"></a>推导出的依赖项
推理依赖项从推理规则中派生，并进行评估之前显式依赖项。 如果相对于其目标过期推理依赖项，NMAKE 调用依赖项的命令块。 如果推断依赖于不存在或已过期相对于其自身的依赖项，则 NMAKE 首先更新推理依赖项。 有关推理依赖项的详细信息，请参阅[推理规则](../build/inference-rules.md)。  
  
## <a name="see-also"></a>请参阅  
 [依赖项](../build/dependents.md)