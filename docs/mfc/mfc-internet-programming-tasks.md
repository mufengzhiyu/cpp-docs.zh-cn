---
title: "MFC Internet 编程任务 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- Internet applications [MFC], getting started
- Internet applications [MFC], first steps
ms.assetid: 6377e9b8-07c4-4380-b63b-05f5a9061313
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: cd726860e181eb352d7368f31a31d2cbd7489000
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="mfc-internet-programming-tasks"></a>MFC Internet 编程任务
本节包含将 Internet 支持添加到应用程序的详细步骤。 主题包括如何使用 MFC 类使现有应用程序支持 Internet，以及如何为现有 COM 组件添加活动文档支持。 你想要创建文档包含最新股票行情、 匹兹堡的橄榄球比赛的比分和南极洲 Microsoft 中的最新温度提供了许多的技术来帮助您做到这一点通过 Internet。  
  
 Active 技术包括 ActiveX 控件（以前称为 OLE 控件）和活动文档；用于在 Internet 上轻松检索和保存文件的 WinInet；以及用于有效地下载数据的异步名字对象。 Visual C++ 提供了帮助您快速上手入门级应用程序的向导。 有关这些技术的介绍，请参阅[MFC Internet 编程基础知识](../mfc/mfc-internet-programming-basics.md)和[MFC COM](../mfc/mfc-com.md)。  
  
 具有你始终希望 FTP 文件但尚未获知 WinSock 和网络编程协议 WinInet 类封装了这些协议，向你提供一组简单的函数可用于在 Internet 以下载文件上编写客户端应用程序使用 HTTP、 FTP 和 gopher。 您可以使用 WinInet 在硬盘上搜索目录或从世界各地搜索目录。 您可以透明地收集几种不同类型的数据，并在集成的界面中将其呈现给用户。  
  
 您有大量的数据要下载异步名字对象所提供的用于渐进式呈现大型对象的 COM （组件对象模型） 解决方案。 WinInet 也可以异步使用。  
  
 下表介绍了一些可使用这些技术执行的操作。  
  
|您拥有|您希望|您应该|  
|--------------|-----------------|----------------|  
|一台 Web 服务器。|跟踪有关 URL 请求的登录和详细信息。|编写一个筛选器，请求登录事件和 URL 映射的通知。|  
|一个 Web 浏览器。|提供动态内容。|创建 ActiveX 控件和活动文档。|  
|基于文档的应用程序。|添加对以 FTP 方式传输文件的支持。|使用 WinInet 或异步名字对象。|  
  
 有关帮助您入门的详细信息，请参阅下列主题：  
  
-   [应用程序设计选项](../mfc/application-design-choices.md)  
  
-   [编写 MFC 应用程序](../mfc/writing-mfc-applications.md)  
  
-   [Internet 上的 ActiveX 控件](../mfc/activex-controls-on-the-internet.md)  
  
-   [升级现有的 ActiveX 控件](../mfc/upgrading-an-existing-activex-control.md)  
  
-   [Internet 上的活动文档](../mfc/active-documents-on-the-internet.md)  
  
-   [Internet 上的异步名字对象](../mfc/asynchronous-monikers-on-the-internet.md)  
  
-   [测试 Internet 应用程序](../mfc/testing-internet-applications.md)  
  
-   [Internet 安全性](../mfc/internet-security-cpp.md)  
  
## <a name="see-also"></a>请参阅  
 [MFC Internet 编程基础知识](../mfc/mfc-internet-programming-basics.md)   
 [按任务划分的 Internet 信息](../mfc/internet-information-by-task.md)

