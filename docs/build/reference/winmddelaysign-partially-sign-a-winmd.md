---
title: "-WINMDDELAYSIGN （部分 winmd 的登录） |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VC.Project.VCLinkerTool.WINMDDelaySign
dev_langs: C++
ms.assetid: 445cd602-62cb-400a-8e3a-4beb6572724d
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 79b22e0634a28d208081d29d0fa3ec0cb01456bd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="winmddelaysign-partially-sign-a-winmd"></a>/WINMDDELAYSIGN（对 winmd 进行部分签名）
通过将公钥部分放在 Windows 运行时元数据 (.winmd) 文件中来启用该文件的部分签名。  
  
```  
/WINMDDELAYSIGN[:NO]  
```  
  
## <a name="remarks"></a>备注  
 类似于[/DELAYSIGN](../../build/reference/delaysign-partially-sign-an-assembly.md)应用于.winmd 文件的链接器选项。 使用**/WINMDDELAYSIGN**如果你想要将仅将公钥放在.winmd 文件。 默认情况下，链接器的作用如同**/WINMDDELAYSIGN:NO**指定; 也就是说，它不会不签名 winmd 文件。  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此链接器选项  
  
1.  打开项目的“属性页”  对话框。 有关详细信息，请参阅[使用项目属性](../../ide/working-with-project-properties.md)。  
  
2.  选择**链接器**文件夹。  
  
3.  选择**Windows 元数据**属性页。  
  
4.  在**Windows 元数据延迟签名**下拉列表框中，选择所需的选项。  
  
## <a name="see-also"></a>请参阅  
 [设置链接器选项](../../build/reference/setting-linker-options.md)   
 [链接器选项](../../build/reference/linker-options.md)