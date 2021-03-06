---
title: "-/Qpar-report （自动并行化程序报告等级） |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 562673b9-02da-4bf8-bb64-70bc25ef4651
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 70ae055d69341cc773b8b40ed1111b65ba5683cf
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/03/2018
---
# <a name="qpar-report-auto-parallelizer-reporting-level"></a>/Qpar-report（自动并行化程序报告等级）
启用编译器的报表功能[自动并行化](../../parallel/auto-parallelization-and-auto-vectorization.md)并在编译期间指定的输出信息性消息的级别。  
  
## <a name="syntax"></a>语法  
  
```  
/Qpar-report:{1}{2}  
```  
  
## <a name="remarks"></a>备注  
 **/Qpar-报表： 1**  
 为并行化的循环输出提供相关信息的消息。  
  
 **/Qpar-报表： 2**  
 为并行化的循环和未并行化的循环输出提供相关信息的消息以及原因代码。  
  
 消息报告为 stdout。 如果未报告任何提供相关信息的消息，则该代码不包含任何循环，或者报告级别未设置为报告未并行化的循环。 有关原因代码和消息的详细信息，请参阅[矢量化程序和并行化程序消息](../../error-messages/tool-errors/vectorizer-and-parallelizer-messages.md)。  
  
### <a name="to-set-the-qpar-report-compiler-option-in-visual-studio"></a>在 Visual Studio 中设置 /Qpar-report 编译器选项  
  
1.  在“解决方案资源管理器” 中，打开项目的快捷菜单，然后选择“属性” 。  
  
2.  在**属性页**对话框中，在**C/c + +**，选择**命令行**。  
  
3.  在**其他选项**框中，输入`/Qpar-report:1`或`/Qpar-report:2`。  
  
### <a name="to-set-the-qpar-report-compiler-option-programmatically"></a>以编程方式设置 /Qpar-report 编译器选项  
  
-   使用 <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A> 中的代码示例。  
  
## <a name="see-also"></a>请参阅  
 [/Q 选项 （低级别操作）](../../build/reference/q-options-low-level-operations.md)   
 [编译器选项](../../build/reference/compiler-options.md)   
 [设置编译器选项](../../build/reference/setting-compiler-options.md)   
 [本机代码中的并行编程](http://go.microsoft.com/fwlink/p/?linkid=263662)