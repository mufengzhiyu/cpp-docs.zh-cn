---
title: "错误 C1077 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C1077
dev_langs: C++
helpviewer_keywords: C1077
ms.assetid: 514d66f4-b512-479a-b793-ebf45c91e15b
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: babd8afd8b238c9b18d07500e0ccd3f4df0d836a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="fatal-error-c1077"></a>错误 C1077
编译器限制：命令行选项数不得超过其限定值  
  
 命令行选项数超过了内部限制。  
  
 可能多用 [/D](../../build/reference/d-preprocessor-definitions.md)定义的符号太多。 （改为将定义放置在头文件中。）