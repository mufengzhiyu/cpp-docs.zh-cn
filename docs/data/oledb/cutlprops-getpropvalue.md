---
title: "Cutlprops:: Getpropvalue |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CUtlProps::GetPropValue
- CUtlProps.GetPropValue
- GetPropValue
dev_langs: C++
helpviewer_keywords: GetPropValue method
ms.assetid: 9a3fbadb-7814-48f7-96a4-b960fc4ecf2e
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: f6af9c8d909039927a7b4ad1f4840adac4353c97
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="cutlpropsgetpropvalue"></a>CUtlProps::GetPropValue
获取来自属性集的属性。  
  
## <a name="syntax"></a>语法  
  
```  
  
      OUT_OF_LINE HRESULT GetPropValue(  
   const GUID* pguidPropSet,  
   DBPROPID dwPropId,  
   VARIANT* pvValue   
);  
```  
  
#### <a name="parameters"></a>参数  
 `pguidPropSet`  
 [in]属性集 GUID。  
  
 `dwPropId`  
 [in]则在 property 索引。  
  
 `pvValue`  
 [out]指向一个包含新的属性值的变量的指针。  
  
## <a name="return-value"></a>返回值  
 `Failure`失败和`S_OK`如果成功。  
  
## <a name="requirements"></a>惠?  
 **标头：** atldb.h  
  
## <a name="see-also"></a>请参阅  
 [CUtlProps 类](../../data/oledb/cutlprops-class.md)