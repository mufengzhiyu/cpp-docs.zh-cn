---
title: "SRWLockExclusiveTraits 结构 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SRWLockExclusiveTraits
dev_langs: C++
helpviewer_keywords: SRWLockExclusiveTraits structure
ms.assetid: 38a996ef-c2d7-4886-b413-a426ecee8f05
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 05e7b2a6814cefffee258909f4bab11fcfe34f1c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="srwlockexclusivetraits-structure"></a>SRWLockExclusiveTraits 结构
描述中排他锁模式的 SRWLock 类的共同特征。  
  
## <a name="syntax"></a>语法  
  
```  
struct SRWLockExclusiveTraits;  
```  
  
## <a name="members"></a>成员  
  
### <a name="public-typedefs"></a>公共 Typedef  
  
|名称|描述|  
|----------|-----------------|  
|`Type`|同义词指向的指针[SRWLOCK](../windows/srwlock-class.md)类。|  
  
### <a name="public-methods"></a>公共方法  
  
|名称|描述|  
|----------|-----------------|  
|[SRWLockExclusiveTraits::GetInvalidValue 方法](../windows/srwlockexclusivetraits-getinvalidvalue-method.md)|检索始终无效的 SRWLockExclusiveTraits 对象。|  
|[SRWLockExclusiveTraits::Unlock 方法](../windows/srwlockexclusivetraits-unlock-method.md)|释放指定 SRWLock 对象的独有控制。|  
  
## <a name="inheritance-hierarchy"></a>继承层次结构  
 `SRWLockExclusiveTraits`  
  
## <a name="requirements"></a>惠?  
 **标头：** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers::HandleTraits  
  
## <a name="see-also"></a>请参阅  
 [Microsoft::WRL::Wrappers::HandleTraits 命名空间](../windows/microsoft-wrl-wrappers-handletraits-namespace.md)