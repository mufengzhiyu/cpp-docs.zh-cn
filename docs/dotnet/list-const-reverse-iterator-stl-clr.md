---
title: "list:: const_reverse_iterator (STL/CLR) |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::list::const_reverse_iterator
dev_langs: C++
helpviewer_keywords: const_reverse_iterator member [STL/CLR]
ms.assetid: d9a9a1ec-df5f-411f-9918-beb5838ffa63
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: e0903be0ec7e71e2ef37d34dfee193c6ecbdba3d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="listconstreverseiterator-stlclr"></a>list::const_reverse_iterator (STL/CLR)
受控序列的常量反向迭代器的类型...  
  
## <a name="syntax"></a>语法  
  
```  
typedef T4 const_reverse_iterator;  
```  
  
## <a name="remarks"></a>备注  
 此类型描述未指定类型的对象`T4`，可用作受控序列的常量反向迭代器。  
  
## <a name="example"></a>示例  
  
```  
// cliext_list_const_reverse_iterator.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c" reversed   
    cliext::list<wchar_t>::const_reverse_iterator crit = c1.rbegin();   
    cliext::list<wchar_t>::const_reverse_iterator crend = c1.rend();   
    for (; crit != crend; ++crit)   
        System::Console::Write(" {0}", *crit);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
c b a  
```  
  
## <a name="requirements"></a>惠?  
 **标头：** \<cliext/列表 >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>请参阅  
 [列表 (STL/CLR)](../dotnet/list-stl-clr.md)   
 [list::reverse_iterator (STL/CLR)](../dotnet/list-reverse-iterator-stl-clr.md)