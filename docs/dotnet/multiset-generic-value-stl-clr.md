---
title: "multiset::generic_value (STL/CLR) |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::multiset::generic_value
dev_langs: C++
helpviewer_keywords: generic_value member [STL/CLR]
ms.assetid: 4b77b5f8-1e69-48b3-b523-c92ab538a29f
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: ed9fc78fc78882b2c45bb5c62bbab95ef765297d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="multisetgenericvalue-stlclr"></a>multiset::generic_value (STL/CLR)
使用容器的泛型接口具有的元素的类型。  
  
## <a name="syntax"></a>语法  
  
```  
typedef GValue generic_value;  
```  
  
## <a name="remarks"></a>备注  
 此类型描述类型的对象`GValue`描述使用的存储的元素值与此模板容器类的泛型接口。  
  
## <a name="example"></a>示例  
  
```  
// cliext_multiset_generic_value.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct a generic container   
    Mymultiset::generic_container^ gc1 = %c1;   
    for each (wchar_t elem in gc1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// get an element and display it   
    Mymultiset::generic_iterator gcit = gc1->begin();   
    Mymultiset::generic_value gcval = *gcit;   
    System::Console::WriteLine(" {0}", gcval);   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
a b c  
a  
```  
  
## <a name="requirements"></a>惠?  
 **标头：** \<cliext/set >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>请参阅  
 [多集 (STL/CLR)](../dotnet/multiset-stl-clr.md)   
 [multiset::generic_container (STL/CLR)](../dotnet/multiset-generic-container-stl-clr.md)   
 [multiset::generic_iterator (STL/CLR)](../dotnet/multiset-generic-iterator-stl-clr.md)   
 [multiset::generic_reverse_iterator (STL/CLR)](../dotnet/multiset-generic-reverse-iterator-stl-clr.md)