---
title: "OLE 后台： MFC 实现 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IMarshall
- IMoniker
dev_langs: C++
helpviewer_keywords:
- MFC libraries, implementing
- OLE MFC library implementation
- OLE IMarshal interface
- IMoniker interface, MFC
- IMarshall class [MFC]
- OLE, compound files
- OLE IMoniker interface
- OLE IUnknown
ms.assetid: 2b67016a-d78e-4d60-925f-c28ec8fb6180
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 530cc14135fd38e2177e00dc87974e96ffe24b6c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="ole-background-mfc-implementation"></a>OLE 后台：MFC 实现
由于原始 OLE API 的大小和复杂性，直接调用它来编写 OLE 应用程序会非常耗时。 OLE 的 Microsoft 基础类库实现的目的是减少编写功能齐全、具有 OLE 功能的应用程序所必须进行的工作量。  
  
 本文将介绍 MFC 中尚未实现的部分 OLE API。 此外还解释了如何实现哪些功能映射到 Windows SDK 的 OLE 部分。  
  
##  <a name="_core_portions_of_ole_not_implemented_by_the_class_library"></a>未由类库实现的 OLE 的某些部分  
 MFC 未直接提供 OLE 的一些接口和功能。 如果您要使用这些功能，可以直接调用 OLE API。  
  
 IMoniker 接口  
 `IMoniker` 接口由类库（例如，`COleServerItem` 类）实现，但之前尚未向程序员公开。 有关此接口的详细信息，请参阅 OLE 名字对象实现的 Windows sdk 的 OLE 部分中。 但是，另请参阅类[CMonikerFile](../mfc/reference/cmonikerfile-class.md)和[CAsyncMonikerFile](../mfc/reference/casyncmonikerfile-class.md)。  
  
 IUnknown 和 IMarshal 接口  
 **IUnknown**接口由类库实现，但未向程序员公开。 **IMarshal**接口未由类库实现，但在内部使用。 使用类库生成的自动化服务器已内置了封送功能。  
  
 Docfiles（复合文件）  
 复合文件由类库提供部分支持。 任何直接操作复合文件的函数（创建复合文件的函数除外）都不受支持。 MFC 使用类**COleFileStream**以支持使用标准文件函数的流。 有关详细信息，请参阅文章[容器： 复合文件](../mfc/containers-compound-files.md)。  
  
 进程内服务器和对象处理程序  
 进程内服务器和对象处理程序允许在动态链接库 (DLL) 中实现可视编辑数据或完整的组件对象模型 (COM) 对象。 为此，可以通过直接调用 OLE API 实现 DLL。 但是，如果您正在编写自动化服务器而且该服务器没有用户界面，则可使用 AppWizard 使该服务器成为进程内服务器并将其完全置于 DLL 中。 有关这些主题的详细信息，请参阅[自动化服务器](../mfc/automation-servers.md)。  
  
> [!TIP]
>  实现自动化服务器的最简单方法是将它置于 DLL 中。 MFC 支持这种做法。  
  
 有关 Microsoft Foundation OLE 类如何实现 OLE 接口的详细信息，请参阅 MFC 技术说明[38](../mfc/tn038-mfc-ole-iunknown-implementation.md)， [39](../mfc/tn039-mfc-ole-automation-implementation.md)，和[40](../mfc/tn040-mfc-ole-in-place-resizing-and-zooming.md)。  
  
## <a name="see-also"></a>请参阅  
 [OLE 后台](../mfc/ole-background.md)   
 [OLE 后台：实现策略](../mfc/ole-background-implementation-strategies.md)

