---
title: "collection_adapter::begin (STL/CLR) |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::collection_adapter::begin
dev_langs: C++
helpviewer_keywords: begin member [STL/CLR]
ms.assetid: fba55a3f-c1c6-4679-8c94-54cbb468e44c
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 42b228f9f83060f3578f1ef2bf78d9d8259bb55c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="collectionadapterbegin-stlclr"></a>collection_adapter::begin (STL/CLR)
指定受控序列的开头。  
  
## <a name="syntax"></a>语法  
  
```  
iterator begin();  
```  
  
## <a name="remarks"></a>备注  
 成员函数返回指定第一个元素的受控序列，或刚超出空序列末尾的输入迭代器。  
  
## <a name="example"></a>示例  
  
```  
// cliext_collection_adapter_begin.cpp   
// compile with: /clr   
#include <cliext/adapter>   
#include <cliext/deque>   
  
typedef cliext::collection_adapter<   
    System::Collections::ICollection> Mycoll;   
int main()   
    {   
    cliext::deque<wchar_t> d1;   
    d1.push_back(L'a');   
    d1.push_back(L'b');   
    d1.push_back(L'c');   
    Mycoll c1(%d1);   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// inspect first two items   
    Mycoll::iterator it = c1.begin();   
    System::Console::WriteLine("*begin() = {0}", *it);   
    System::Console::WriteLine("*++begin() = {0}", *++it);   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
*begin() = a  
*++begin() = b  
```  
  
## <a name="requirements"></a>惠?  
 **标头：** \<cliext/适配器 >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>请参阅  
 [collection_adapter (STL/CLR)](../dotnet/collection-adapter-stl-clr.md)   
 [collection_adapter::end (STL/CLR)](../dotnet/collection-adapter-end-stl-clr.md)