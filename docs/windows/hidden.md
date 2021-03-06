---
title: "隐藏 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.hidden
dev_langs: C++
helpviewer_keywords: hidden attribute
ms.assetid: 199c96dd-fc07-46c7-af93-92020aebebe7
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c038eb4869cb3191dd26b5c4ea8e1c6cc182e366
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="hidden"></a>隐藏
指示该项存在，但不是应在面向用户的浏览器中显示。  
  
## <a name="syntax"></a>语法  
  
```  
  
[hidden]  
  
```  
  
## <a name="remarks"></a>备注  
 **隐藏**c + + 属性具有相同的功能[隐藏](http://msdn.microsoft.com/library/windows/desktop/aa366861)MIDL 特性。  
  
## <a name="example"></a>示例  
 请参阅示例[可绑定](../windows/bindable.md)以举例说明如何使用**隐藏**。  
  
## <a name="requirements"></a>惠?  
  
### <a name="attribute-context"></a>特性上下文  
  
|||  
|-|-|  
|**适用对象**|`interface`**类**， `struct`，方法、 属性|  
|**可重复**|否|  
|**必需的特性**|**coclass** （应用于 **class** 或 `struct`时）|  
|**无效的特性**|无|  
  
 有关详细信息，请参见 [特性上下文](../windows/attribute-contexts.md)。  
  
## <a name="see-also"></a>请参阅  
 [IDL 特性](../windows/idl-attributes.md)   
 [接口特性](../windows/interface-attributes.md)   
 [类特性](../windows/class-attributes.md)   
 [方法特性](../windows/method-attributes.md)   
