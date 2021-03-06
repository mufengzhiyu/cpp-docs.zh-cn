---
title: "将消息映射到函数 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.codewiz.mapping.msg.function
dev_langs: C++
helpviewer_keywords:
- Windows messages [MFC], adding message handlers
- message maps [MFC], mapping messages to functions
ms.assetid: a7727a62-f638-4b20-b7f5-131f47200d6a
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ad36b249e601e15e25f32ef1ef7e6d5a28874cf1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="mapping-messages-to-functions"></a>将消息映射到函数
属性窗口，可将消息处理程序 （MFC 用户界面类的成员函数） 绑定到你的应用程序资源生成的消息。 它们使用[MFC 消息映射](../../mfc/messages-and-commands-in-the-framework.md)以创建绑定。  
  
 当你使用类视图创建从框架类之一派生的新类时，它自动放置指向完整的功能的类标头 (.h) 和实现 (.cpp) 中指定的文件。  
  
> [!NOTE]
>  若要添加一个新类，并不处理消息，请在文本编辑器中直接创建类。  
  
### <a name="to-define-or-remove-a-message-handler-using-the-properties-window"></a>若要定义或删除消息处理程序使用属性窗口  
  
1.  在类视图中，单击类。  
  
2.  在属性窗口中，单击**消息**按钮。  
  
    > [!NOTE]
    >  **消息**当在类视图或当您单击源窗口中选择类名时，按钮才可用。  
  
     如果你的项目具有的处理程序一条消息，处理程序的名称将出现在消息旁边右侧列中。  
  
3.  如果消息没有处理程序，然后单击在属性窗口来显示为处理程序的建议的名称右侧列中的单元格\<添加 >*HandlerName*。 (例如，`WM_TIMER`消息处理程序提供的建议\<添加 >`OnTimer`)。  
  
4.  单击要添加函数的存根 （stub） 代码的建议的名称。  
  
5.  若要编辑消息处理程序，请双击类视图中的消息，然后编辑源窗口中的代码。  
  
 若要删除消息处理程序，请双击右列中的处理程序，然后选择\<删除 >*HandlerName*。 函数的代码注释掉。  
  
## <a name="see-also"></a>请参阅  
 [MFC 消息处理程序](../../mfc/reference/adding-an-mfc-message-handler.md)   
 [用代码向导添加功能](../../ide/adding-functionality-with-code-wizards-cpp.md)   
 [添加类](../../ide/adding-a-class-visual-cpp.md)   
 [添加成员函数](../../ide/adding-a-member-function-visual-cpp.md)   
 [添加成员变量](../../ide/adding-a-member-variable-visual-cpp.md)   
 [重写虚函数](../../ide/overriding-a-virtual-function-visual-cpp.md)   
 [添加事件处理程序对话框控件](../../windows/adding-event-handlers-for-dialog-box-controls.md)   
 [导航类结构](../../ide/navigating-the-class-structure-visual-cpp.md)
