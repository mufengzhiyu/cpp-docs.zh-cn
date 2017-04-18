---
title: "用户按钮处理程序 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ON_BN_HILITE"
  - "ON_BN_DOUBLECLICKED"
  - "ON_BN_CLICKED"
  - "ON_BN_PAINT"
  - "ON_BN_DISABLE"
  - "ON_BN_UNHILITE"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ON_BN_CLICKED"
  - "ON_BN_DISABLE"
  - "ON_BN_DOUBLECLICKED"
  - "ON_BN_HILITE"
  - "ON_BN_PAINT"
  - "ON_BN_UNHILITE"
  - "用户按钮"
ms.assetid: 410ea968-478f-4806-b7b8-5d7c8dc2bf42
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# 用户按钮处理程序
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

下列映射实体对应于函数原型。  
  
|映射项|函数原型|  
|---------|----------|  
|ON\_BN\_CLICKED\( \<id\>, \<memberFxn\> \)|afx\_msg void memberFxn\( \);|  
|ON\_BN\_DISABLE\( \<id\>, \<memberFxn\> \)|afx\_msg void memberFxn\( \);|  
|ON\_BN\_DOUBLECLICKED\( \<id\>, \<memberFxn\> \)|afx\_msg void memberFxn\( \);|  
|ON\_BN\_HILITE\( \<id\>, \<memberFxn\> \)|afx\_msg void memberFxn\( \);|  
|ON\_BN\_PAINT\( \<id\>, \<memberFxn\> \)|afx\_msg void memberFxn\( \);|  
|ON\_BN\_UNHILITE\( \<id\>, \<memberFxn\> \)|afx\_msg void memberFxn\( \);|  
  
## 请参阅  
 [消息映射](../../mfc/reference/message-maps-mfc.md)