---
title: "Cdynamicstringaccessor:: Setstring |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDynamicStringAccessor::SetString
- CDynamicStringAccessor.SetString
dev_langs: C++
helpviewer_keywords: SetString method
ms.assetid: 94846d8b-4c1b-47fe-acdc-1752981cee25
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 7c05186d8ea7f62ad07cae9a4b4689083543e485
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="cdynamicstringaccessorsetstring"></a>CDynamicStringAccessor::SetString
将指定列数据设置为字符串。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT SetString(  
   DBORDINAL nColumn,  
   BaseType* data  
) throw( );  
HRESULT SetString(  
   const CHAR* pColumnName,  
   BaseType* data  
) throw( );  
HRESULT SetString(  
   const WCHAR* pColumnName,  
   BaseType* data  
) throw( );  
```  
  
#### <a name="parameters"></a>参数  
 `nColumn`  
 [in] 列号。 列编号从 1 开始。 特殊的 0 值引用的书签列中，如果有的话。  
  
 `pColumnName`  
 [in]指向包含列名的字符串的指针。  
  
 `data`  
 [in]指向要写入到指定的列的字符串数据的指针。  
  
## <a name="return-value"></a>返回值  
 指向要设置的指定的列的字符串值的指针。 值的类型是`BaseType`，这将是`CHAR`或`WCHAR`具体取决于是否`_UNICODE`或未定义。  
  
## <a name="remarks"></a>备注  
 第二个重写窗体采用 ANSI 字符串形式的列名称和第三个重写窗体采用为 Unicode 字符串的列名称。  
  
 如果`_SECURE_ATL`定义具有非零值，运行时断言失败将生成如果输入`data`字符串的长度超过引用的数据列的最大允许长度。 否则，如果它的长度大于最大允许长度，则将截断的输入的字符串。  
  
## <a name="requirements"></a>惠?  
 **标头:** atldbcli.h  
  
## <a name="see-also"></a>请参阅  
 [CDynamicStringAccessor 类](../../data/oledb/cdynamicstringaccessor-class.md)