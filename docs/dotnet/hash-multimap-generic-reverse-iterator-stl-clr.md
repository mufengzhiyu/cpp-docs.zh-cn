---
title: "hash_multimap::generic_reverse_iterator (STL/CLR) |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::hash_multimap::generic_reverse_iterator
dev_langs: C++
helpviewer_keywords: generic_reverse_iterator member [STL/CLR]
ms.assetid: 490dc65b-939b-4fe3-9bad-2e738da35a38
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: b825caa573af29975f93a89d04143b641b51aba3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="hashmultimapgenericreverseiterator-stlclr"></a>hash_multimap::generic_reverse_iterator (STL/CLR)
反向迭代器用于与容器的泛型接口类型。  
  
## <a name="syntax"></a>语法  
  
```  
typedef Microsoft::VisualC::StlClr::Generic::  
    ReverseRandomAccessIterator<generic_value>  
    generic_reverse_iterator;  
```  
  
## <a name="remarks"></a>备注  
 该类型描述一个泛型反向迭代器，此模板容器类可与泛型接口中使用。  
  
## <a name="example"></a>示例  
  
```  
// cliext_hash_multimap_generic_reverse_iterator.cpp   
// compile with: /clr   
#include <cliext/hash_map>   
  
typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;   
int main()   
    {   
    Myhash_multimap c1;   
    c1.insert(Myhash_multimap::make_value(L'a', 1));   
    c1.insert(Myhash_multimap::make_value(L'b', 2));   
    c1.insert(Myhash_multimap::make_value(L'c', 3));   
  
// display contents " [a 1] [b 2] [c 3]"   
    for each (Myhash_multimap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// construct a generic container   
    Myhash_multimap::generic_container^ gc1 = %c1;   
    for each (Myhash_multimap::value_type elem in gc1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// get an element and display it   
    Myhash_multimap::generic_reverse_iterator gcit = gc1->rbegin();   
    Myhash_multimap::generic_value gcval = *gcit;   
    System::Console::WriteLine(" [{0} {1}]", gcval->first, gcval->second);   
    return (0);   
    }  
  
```  
  
```Output  
[a 1] [b 2] [c 3]  
[a 1] [b 2] [c 3]  
[c 3]  
```  
  
## <a name="requirements"></a>惠?  
 **标头：** \<cliext/hash_map >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>请参阅  
 [hash_multimap (STL/CLR)](../dotnet/hash-multimap-stl-clr.md)   
 [hash_multimap::generic_container (STL/CLR)](../dotnet/hash-multimap-generic-container-stl-clr.md)   
 [hash_multimap::generic_iterator (STL/CLR)](../dotnet/hash-multimap-generic-iterator-stl-clr.md)