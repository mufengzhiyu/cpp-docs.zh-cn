---
title: "operator&gt;= (multimap) (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::multimap::operator>="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "operator>= 成员 [STL/CLR]"
ms.assetid: a9e2451b-476f-48ad-a305-50798c2991f2
caps.latest.revision: 16
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# operator&gt;= (multimap) (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

“大于或等于”比较。  
  
## 语法  
  
```  
template<typename Key,  
    typename Mapped>  
    bool operator>=(multimap<Key, Mapped>% left,  
        multimap<Key, Mapped>% right);  
```  
  
#### 参数  
 left  
 比较左边的容器。  
  
 right  
 比较右边的容器。  
  
## 备注  
 操作符函数返回`!(``left` `<` `right``)` 。  当一个个元素地比较两种多集时，您可以用它测试 `left` 是否在 `right` 之前排序。  
  
## 示例  
  
```  
// cliext_multimap_operator_ge.cpp   
// compile with: /clr   
#include <cliext/map>   
  
typedef cliext::multimap<wchar_t, int> Mymultimap;   
int main()   
    {   
    Mymultimap c1;   
    c1.insert(Mymultimap::make_value(L'a', 1));   
    c1.insert(Mymultimap::make_value(L'b', 2));   
    c1.insert(Mymultimap::make_value(L'c', 3));   
  
// display contents " [a 1] [b 2] [c 3]"   
    for each (Mymultimap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// assign to a new container   
    Mymultimap c2;   
    c2.insert(Mymultimap::make_value(L'a', 1));   
    c2.insert(Mymultimap::make_value(L'b', 2));   
    c2.insert(Mymultimap::make_value(L'd', 4));   
  
// display contents " [a 1] [b 2] [d 4]"   
    for each (Mymultimap::value_type elem in c2)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("[a b c] >= [a b c] is {0}",   
        c1 >= c1);   
    System::Console::WriteLine("[a b c] >= [a b d] is {0}",   
        c1 >= c2);   
    return (0);   
    }  
  
```  
  
  **\[a 1\] \[b 2\] \[c 3\]**  
 **\[a 1\] \[b 2\] \[d 4\]**  
**\[a b c\] \>\= \[a b c\] 为True**  
**\[a b c\] \>\= \[a b d\] 为 False**   
## 要求  
 **标头:** \<cliext\/map\>  
  
 **命名空间:** cliext  
  
## 请参阅  
 [multimap](../dotnet/multimap-stl-clr.md)   
 [operator\=\= \(multimap\)](../dotnet/operator-equality-multimap-stl-lr.md)   
 [operator\!\= \(multimap\)](../dotnet/operator-inequality-multimap-stl-clr.md)   
 [operator\< \(multimap\)](../dotnet/operator-less-than-multimap-stl-clr.md)   
 [operator\> \(multimap\)](../dotnet/operator-greater-than-multimap-stl-clr.md)   
 [operator\<\= \(multimap\)](../dotnet/operator-less-or-equal-multimap-stl-clr.md)