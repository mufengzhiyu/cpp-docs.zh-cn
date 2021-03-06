---
title: "如何： 添加功能区控件和事件处理程序 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- event handlers [MFC], adding
- ribbon controls [MFC], adding
ms.assetid: b31f25bc-ede7-49c3-9e3c-dffe4e174a69
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f5d5015fdf5fd2a97b6b8a9b9ee9cf5ccc755ce5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-add-ribbon-controls-and-event-handlers"></a>如何：添加功能区控件和事件处理程序
功能区控件是元素，如按钮和组合框中，添加到面板。 面板将显示一组相关控件的功能区栏的区域。  
  
 在本主题中，将打开功能区设计器、 添加一个按钮，然后将显示"Hello World"的事件的链接。  
  
### <a name="to-open-the-ribbon-designer"></a>若要打开功能区设计器  
  
1.  在 Visual Studio 中，在**视图**菜单上，单击**资源视图**。  
  
2.  在**资源视图**，双击功能区资源可将其显示在设计图面上。  
  
### <a name="to-add-a-button-and-an-event-handler"></a>若要添加一个按钮和一个事件处理程序  
  
1.  从**工具栏**，单击**按钮**并将其拖到设计图面中的一个面板。  
  
2.  右键单击该按钮，然后单击**添加事件处理程序**。  
  
3.  在**事件处理程序向导**，确认的默认设置，然后单击**添加和编辑**。 有关详细信息，请参阅[事件处理程序向导](../ide/event-handler-wizard.md)。  
  
4.  在代码编辑器中，执行处理程序函数中添加以下代码：  
  
 ```  
    MessageBox((LPCTSTR)L"Hello World");

 ```  
  
## <a name="see-also"></a>请参阅  
 [RibbonGadgets 示例： 功能区小工具应用程序](../visual-cpp-samples.md)   
 [功能区设计器 (MFC)](../mfc/ribbon-designer-mfc.md)

