---
title: "Ccommand:: Getnextresult |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::CCommand::GetNextResult
- CCommand::GetNextResult
- GetNextResult
- CCommand.GetNextResult
- ATL.CCommand.GetNextResult
dev_langs: C++
helpviewer_keywords: GetNextResult method
ms.assetid: 63df9b55-9490-45c4-934a-879c5c2725d8
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: a3bf105f0c85d831d1a8e4bb0048a1385e6275da
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="ccommandgetnextresult"></a>CCommand::GetNextResult
提取下一个结果集是否可用。  
  
## <a name="syntax"></a>语法  
  
```  
  
      HRESULT GetNextResult(  
   DBROWCOUNT* pulRowsAffected,  
   bool bBind = true   
) throw( );  
```  
  
#### <a name="parameters"></a>参数  
 *pulRowsAffected*  
 [输入/输出]指向内存其中返回某一命令受影响的行数的指针。  
  
 `bBind`  
 [in]指定是否在正在执行后自动绑定命令。 默认值是**true**，这将导致产生命令自动绑定。 设置`bBind`到**false**阻止自动绑定命令，以便你可以手动绑定。 （手动绑定是 OLAP 用户的特别感兴趣。）  
  
## <a name="return-value"></a>返回值  
 一个标准 `HRESULT`。  
  
## <a name="remarks"></a>备注  
 如果先前已读取的结果集，此函数将释放以前的结果集，并取消绑定列。 如果`bBind`是**true**，它将新列的绑定。  
  
 仅当你通过设置指定多个结果，应调用此函数`CCommand`模板参数*TMultiple*=`CMultipleResults`。  
  
## <a name="requirements"></a>惠?  
 **标头:** atldbcli.h  
  
## <a name="see-also"></a>请参阅  
 [CCommand 类](../../data/oledb/ccommand-class.md)