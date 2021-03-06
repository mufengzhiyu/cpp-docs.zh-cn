---
title: "文本和二进制流 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- binary streams
- text streams
ms.assetid: 57035e4a-955d-4e04-a560-fcf67ce68b4e
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1665ff1551ffe94b475c463d8f93eba2184eaa27
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="text-and-binary-streams"></a>文本和二进制流
文本流包含一个或多个文本行，这些文本行可写入到面向文本的显示器中以供读取。 当从文本流中进行读取时，程序在每行末尾读取一个 `NL`（换行符）。 在写入文本流时，程序写入一个 `NL` 以表示行的结尾。 为了在目标环境中匹配不同的约定来表示文件中的文本，库函数可以更改在程序和文本流之间传输的字符的数量和表示。  
  
 因此，在文本流中定位是受限的。 可通过调用 [fgetpos](../c-runtime-library/reference/fgetpos.md) 或 [ftell](../c-runtime-library/reference/ftell-ftelli64.md) 获取当前文件位置指示符。 可以将文本流定位到通过这种方式获取的位置，或者通过调用 [fsetpos](../c-runtime-library/reference/fsetpos.md) 或 [fseek](../c-runtime-library/reference/fseek-fseeki64.md)，定位到文本流的开头或结尾。 可能无法很好地支持任何其他位置更改。  
  
 为获得最大的可移植，程序不应写入：  
  
-   空文件。  
  
-   行尾的空白字符。  
  
-   部分行（通过在文件尾省略 `NL`）。  
  
-   除可打印字符、NL 和 `HT`（水平制表符）之外的字符。  
  
 如果您遵循这些规则，则您从文本流读取的字符序列（作为字节或多字节字符）将与您创建文件时写入到文本流的字符序列匹配。 否则，如果您创建的文件在关闭时是空的，则库函数可以删除该文件。 或者库函数也可更改或删除您写入到该文件的字符。  
  
 二进制流包含一个或多个字节的任意信息。 您可将存储在任意对象中的值写入到一个（面向字节的）二进制流，并读取您在编写二进制流时存储在该对象中的完全相同的内容。 库函数不会更改您在程序和二进制流之间传输的字节。 然而，库函数可以将任意数量的 null 字节追加到您使用二进制流编写的文件。 程序必须在任何二进制流的末尾处理这些附加的 null 字节。  
  
 因此，二进制流内的定位可以明确地进行定义，但相对于流的末尾的定位除外。 与文本流相似，可获取和更改当前的文件定位指示符。 此外，由 [ftell](../c-runtime-library/reference/ftell-ftelli64.md) 和 [fseek](../c-runtime-library/reference/fseek-fseeki64.md) 使用的偏移量从流的开头（字节 0）计算字节数，因此有关这些偏移量的整数算法将产生可预知的结果。  
  
 字节流将文件视作一个字节序列。 在程序内部，除了上面所述的可能的更改之外，流类似于相同的字节序列。  
  
## <a name="see-also"></a>请参阅  
 [文件和流](../c-runtime-library/files-and-streams.md)