---
title: "Asyncbase:: Putonprogress 方法 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: async/Microsoft::WRL::AsyncBase::PutOnProgress
dev_langs: C++
helpviewer_keywords: PutOnProgress method
ms.assetid: 1f5f180e-eb5a-4afe-ac16-69dbf36f0383
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 25479de837c157871d7757b6948d6cd581d56ace
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="asyncbaseputonprogress-method"></a>AsyncBase::PutOnProgress 方法
进度事件处理程序的地址设置为指定的值。  
  
## <a name="syntax"></a>语法  
  
```  
STDMETHOD(  
   PutOnProgress  
)(TProgress* progressHandler);  
```  
  
#### <a name="parameters"></a>参数  
 `progressHandler`  
 进度事件处理程序设置为地址。  
  
## <a name="return-value"></a>返回值  
 如果成功，则则为 S_OK否则为 E_ILLEGAL_METHOD_CALL。  
  
## <a name="requirements"></a>惠?  
 **标头：** async.h  
  
 **命名空间：** Microsoft::WRL  
  
## <a name="see-also"></a>请参阅  
 [AsyncBase 类](../windows/asyncbase-class.md)