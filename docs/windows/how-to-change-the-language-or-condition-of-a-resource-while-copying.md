---
title: "如何： 在复制时更改语言或资源的条件 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.resvw.resource.changing
dev_langs: C++
helpviewer_keywords:
- Language property
- condition property of resource
ms.assetid: 8f622ab0-bac2-468f-ae70-78911afc4759
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 3655366e8851494482e628b9c260c796df3f64bd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-change-the-language-or-condition-of-a-resource-while-copying"></a>如何：在复制时更改资源的语言或条件
在资源中进行复制时，你可以更改其语言属性和/或条件属性。  
  
-   资源的语言仅标识资源的语言。 使用此[FindResource](http://msdn.microsoft.com/library/windows/desktop/ms648042)以帮助识别要查找的资源。 （但是，每种不与文本相关的语言的资源可能存在差异，例如，可能仅适用于日语键盘的加速器或仅适用于中文本地化生成的位图，等等。）  
  
-   资源的条件是定义的符号，后者标识了使用资源的此特定副本的条件。  
  
 语言和资源的条件显示在工作区窗口中资源名称之后的括号内。 在此示例中名为 IDD_AboutBox 的资源使用芬兰语作为其语言，而其条件是 XX33。  
  
```  
IDD_AboutBox (Finnish - XX33)  
```  
  
### <a name="to-copy-an-existing-resource-and-change-its-language-or-condition"></a>复制的现有资源并更改其语言或条件  
  
1.  在.rc 文件中或在[资源视图](../windows/resource-view-window.md)窗口中，右键单击你想要复制的资源。  
  
2.  选择**插入副本**从快捷菜单。  
  
3.  在**插入资源副本**对话框中：  
  
    -   有关**语言**列表框中，选择的语言。  
  
    -   在**条件**框中，键入条件。  
  

  
 惠?  
  
 Win32  
  
## <a name="see-also"></a>请参阅  
 [如何： 复制资源](../windows/how-to-copy-resources.md)   
 [资源文件](../windows/resource-files-visual-studio.md)   
 [资源编辑器](../windows/resource-editors.md)