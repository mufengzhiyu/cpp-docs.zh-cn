---
title: "Cdynamicaccessor:: Getlength |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDynamicAccessor.GetLength
- ATL.CDynamicAccessor.GetLength
- CDynamicAccessor::GetLength
- ATL::CDynamicAccessor::GetLength
dev_langs: C++
helpviewer_keywords: GetLength method
ms.assetid: 3ae8983b-b267-4cf9-bfc0-3e191f79e646
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 24a22348b873967a860c65edb5c4f6d46ab101ba
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="cdynamicaccessorgetlength"></a>CDynamicAccessor::GetLength
检索指定列的长度。  
  
## <a name="syntax"></a>语法  
  
```  
  
      bool GetLength(   
   DBORDINAL nColumn,   
   DBLENGTH* pLength    
) const throw( );  
bool GetLength(   
   const CHAR* pColumnName,   
   DBLENGTH* pLength    
) const throw( );  
bool GetLength(   
   const WCHAR* pColumnName,   
   DBLENGTH* pLength    
) const throw( );  
```  
  
#### <a name="parameters"></a>参数  
 `nColumn`  
 [in] 列号。 列编号从 1 开始。 值为 0 引用的书签列中，如果有的话。  
  
 `pColumnName`  
 [in] 指向包含列名的字符串的指针。  
  
 `pLength`  
 [out]指向包含以字节为单位的列的长度的整数的指针。  
  
## <a name="return-value"></a>返回值  
 返回**true**如果找到指定的列。 否则，此函数返回**false**。  
  
## <a name="remarks"></a>备注  
 第一个替代采用的列号，并第二个和第三个替代方法分别 ANSI 或 Unicode 格式，采用列名称。  
  
## <a name="requirements"></a>惠?  
 **标头:** atldbcli.h  
  
## <a name="see-also"></a>请参阅  
 [CDynamicAccessor 类](../../data/oledb/cdynamicaccessor-class.md)   
 [CDynamicAccessor::SetLength](../../data/oledb/cdynamicaccessor-setlength.md)