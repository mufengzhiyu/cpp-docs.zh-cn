---
title: "__nop |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: __nop
dev_langs: C++
helpviewer_keywords:
- nop instruction
- __nop intrinsic
ms.assetid: 7a2a938b-87e0-476d-a348-03ea7635b6b9
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: eef05150aab36abc6f6be76785284d017cf204ac
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/03/2018
---
# <a name="nop"></a>__nop
**Microsoft 专用**  
  
 生成不执行任何操作的特定于平台的机器代码。  
  
## <a name="syntax"></a>语法  
  
```  
void __nop();  
```  
  
## <a name="requirements"></a>惠?  
  
|内部函数|体系结构|  
|---------------|------------------|  
|`__nop`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **标头文件** \<intrin.h >  
  
**结束 Microsoft 专用**  
  
## <a name="remarks"></a>备注  
 `__nop`函数等同于`NOP`计算机指令。 有关详细信息，搜索文档中，"Intel 体系结构软件开发人员手册，卷 2： 指令集引用，"在[Intel Corporation](http://go.microsoft.com/fwlink/p/?linkid=127)站点。  
  
## <a name="see-also"></a>请参阅  
 [编译器内部函数](../intrinsics/compiler-intrinsics.md)   
 [__noop](../intrinsics/noop.md)