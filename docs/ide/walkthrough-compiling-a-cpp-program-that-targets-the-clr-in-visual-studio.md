---
title: "演练：在 Visual Studio 中编译面向 CLR 的 C++ 程序 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "命令行应用程序 [C++], 托管代码"
  - "编译程序 [C++]"
  - "托管代码 [C++]"
  - "Visual C++, 托管代码"
ms.assetid: 339f89df-a5d2-4040-831a-ddbe25b5dce4
caps.latest.revision: 40
caps.handback.revision: 40
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 演练：在 Visual Studio 中编译面向 CLR 的 C++ 程序
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

通过使用 Visual Studio 开发环境，您可以创建使用 .NET 类的 Visual C\+\+ 程序，并对它们进行编译。  
  
 在本过程中，您可以键入自己的 Visual C\+\+ 程序，也可以使用示例程序之一。  本过程中使用的示例程序创建一个名为 textfile.txt 的文本文件，并将其保存到项目目录中。  
  
## 系统必备  
 这些主题假定您具备 C\+\+ 语言的基础知识。  
  
### 在 Visual Studio 中创建新项目并添加新的源文件  
  
1.  创建新项目。  在**“文件”**菜单上，指向**“新建”**，然后单击**“项目”**。  
  
2.  在“Visual C\+\+ 项目类型”中单击**“CLR”**，然后单击**“CLR 空项目”**。  
  
3.  键入项目名称。  
  
     默认情况下，包含项目的解决方案与新项目同名，当然，您也可以键入其他名称。  如果愿意，您可以为项目输入一个不同的位置。  
  
     单击**“确定”**创建新项目。  
  
4.  如果“解决方案资源管理器”不可见，请单击**“视图”**菜单上的**“解决方案资源管理器”**。  
  
5.  向该项目添加新的源文件：  
  
    -   在解决方案资源管理器中右击**“源文件”**文件夹，指向**“添加”**并单击**“新建项...”**。  
  
    -   单击**“C\+\+ 文件\(.cpp\)”**，键入一个文件名，然后单击**“添加”**。  
  
     该 **.cpp** 文件即显示在“解决方案资源管理器”中的**“源文件”**文件夹中，并且，在键入要包含在该文件中的代码的位置，出现一个选项卡式窗口。  
  
6.  在 Visual Studio 中，在新创建的选项卡中单击并键入有效的 Visual C\+\+ 程序，或者复制并粘贴示例程序之一。  
  
     例如，您可以使用 [如何：编写文本文件](../dotnet/how-to-write-a-text-file-cpp-cli.md) 示例程序（位于“编程指南”中的**“文件处理和 I\/O”**节点）。  
  
     如果要使用示例程序，请注意在创建 .NET 对象时，您可以使用 `gcnew` `` 关键字（而非 `new`），且 `gcnew` 返回一个句柄 \(`^`\) 而不是指针 \(`*`\)：  
  
     `StreamWriter^ sw = gcnew StreamWriter(fileName);`  
  
     有关新 Visual C\+\+ 语法的更多信息，请参见 [适用于运行时平台的组件扩展](../windows/component-extensions-for-runtime-platforms.md)。  
  
7.  在**“生成”**菜单上，单击**“生成解决方案”**。  
  
     **“输出”**窗口显示有关编译过程的信息，如生成日志的位置，以及指示生成状态的消息。  
  
     如果进行了更改，并在未执行生成的情况下运行该程序，则对话框可能指示该项目已过期。  如果要让 Visual Studio 始终使用文件的当前版本，并且在每次生成应用程序时不发出提示，请在单击**“确定”**之前选中此对话框上的复选框。  
  
8.  在**“调试”**菜单上，单击**“开始执行\(不调试\)”**。  
  
9. 如果您使用的是示例程序，则在运行程序时将显示一个命令窗口，指示已创建了该文本文件。  按任意键，关闭该命令窗口。  
  
     **textfile.txt** 文本文件现在位于您的项目目录中。  您可以使用记事本打开此文件。  
  
    > [!NOTE]
    >  选择空 CLR 项目模板会自动设置 **\/clr** 编译器选项。  若要验证这一点，请在**“解决方案资源管理器”**中右击该项目，再单击**“属性”**，然后选中**“配置属性”**的**“常规”**节点中的**“公共语言运行时支持”**选项。  
  
## 接下来的内容  
 **上一部分：** [演练：在命令行上编译本机 C\+\+ 程序](../build/walkthrough-compiling-a-native-cpp-program-on-the-command-line.md) &#124; **下一部分：** [演练：在命令行上编译 C 程序](../Topic/Walkthrough:%20Compiling%20a%20C%20Program%20on%20the%20Command%20Line.md)  
  
## 请参阅  
 [Visual C\+\+ Guided Tour](http://msdn.microsoft.com/zh-cn/499cb66f-7df1-45d6-8b6b-33d94fd1f17c)   
 [C\+\+ 语言参考](../cpp/cpp-language-reference.md)   
 [生成 C\/C\+\+ 程序](../build/building-c-cpp-programs.md)