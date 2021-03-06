---
title: "CEnumeratorAccessor 类 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::CEnumeratorAccessor
- CEnumeratorAccessor
- ATL.CEnumeratorAccessor
dev_langs: C++
helpviewer_keywords: CEnumeratorAccessor class
ms.assetid: 21e8e7ea-3511-4afe-b33f-d520f4ff82bb
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 4a82b09a65cb4ebe6f0f796ba9aeb46ac5a2106a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="cenumeratoraccessor-class"></a>CEnumeratorAccessor 类
使用[CEnumerator](../../data/oledb/cenumerator-class.md)从枚举器行集访问数据。  
  
## <a name="syntax"></a>语法  
  
```  
class CEnumeratorAccessor  
```  
  
## <a name="members"></a>成员  
  
### <a name="data-members"></a>数据成员  
  
|||  
|-|-|  
|[m_bIsParent](../../data/oledb/cenumeratoraccessor-m-bisparent.md)|一个指示枚举器是否的父枚举，如果行是一个枚举的变量。|  
|[m_nType](../../data/oledb/cenumeratoraccessor-m-ntype.md)|变量，该值指示是否行所说明的数据源或枚举数。|  
|[m_szDescription](../../data/oledb/cenumeratoraccessor-m-szdescription.md)|数据源或枚举器的说明。|  
|[m_szName](../../data/oledb/cenumeratoraccessor-m-szname.md)|数据源或枚举器的名称。|  
|[m_szParseName](../../data/oledb/cenumeratoraccessor-m-szparsename.md)|要传递给字符串[IParseDisplayName](http://msdn.microsoft.com/library/windows/desktop/ms680604)若要获取的数据源或枚举器的名字对象。|  
  
## <a name="remarks"></a>备注  
 下一个行集合组成的数据源和当前的枚举器中可见的枚举器。  
  
## <a name="requirements"></a>惠?  
 **标头:** atldbcli.h  
  
## <a name="see-also"></a>请参阅  
 [OLE DB 使用者模板](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB 使用者模板参考](../../data/oledb/ole-db-consumer-templates-reference.md)