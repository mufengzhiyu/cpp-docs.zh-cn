---
title: "COMPAREITEMSTRUCT 结构 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: COMPAREITEMSTRUCT
dev_langs: C++
helpviewer_keywords: COMPAREITEMSTRUCT structure [MFC]
ms.assetid: 4b7131a5-5c7d-4e98-aac7-e85650262b52
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7903e51a83533c8f2458c4400c64717021a1ccb8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="compareitemstruct-structure"></a>COMPAREITEMSTRUCT 结构
`COMPAREITEMSTRUCT`结构提供的标识符和排序、 所有者描述列表框或组合框中的两个项的应用程序提供数据。  
  
## <a name="syntax"></a>语法  
  
```  
typedef struct tagCOMPAREITEMSTRUCT {  
    UINT CtlType;  
    UINT CtlID;  
    HWND hwndItem;  
    UINT itemID1;  
    DWORD itemData1;  
    UINT itemID2;  
    DWORD itemData2;  
} COMPAREITEMSTRUCT;  
```  
  
#### <a name="parameters"></a>参数  
 `CtlType`  
 **ODT_LISTBOX** （它指定一个所有者描述列表框） 或**ODT_COMBOBOX** （它指定一个所有者描述组合框）。  
  
 `CtlID`  
 列表框或组合框的控件 ID。  
  
 `hwndItem`  
 控件的窗口句柄。  
  
 *itemID1*  
 列表框或组合框要比较的第一项的索引。  
  
 *itemData1*  
 要比较的第一项应用程序提供数据。 将项添加到组合或列表框中的调用中传递此值。  
  
 *itemID2*  
 中的列表框或组合框要比较的第二个项的索引。  
  
 *itemData2*  
 要比较的第二项应用程序提供数据。 将项添加到组合或列表框中的调用中传递此值。  
  
## <a name="remarks"></a>备注  
 每当应用程序将新项添加到一个所有者描述的列表框或组合框创建与**CBS_SORT**或**LBS_SORT**样式，Windows 将向所有者发送`WM_COMPAREITEM`消息。 `lParam`消息参数包含的长指针`COMPAREITEMSTRUCT`结构。 接收消息后，所有者比较的两个项，并返回一个值，该值哪一项进行排序之前另。  
  
## <a name="requirements"></a>惠?  
 **标头：** winuser.h  
  
## <a name="see-also"></a>请参阅  
 [结构、 样式、 回调和消息映射](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnCompareItem](../../mfc/reference/cwnd-class.md#oncompareitem)

