---
title: "&lt;unordered_set&gt; 函数 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- unordered_set/std::swap (set)
- unordered_set/std::swap (unordered_multiset)
ms.assetid: 66b35671-4023-4411-ad50-83786580d8ee
caps.latest.revision: "10"
manager: ghogen
ms.openlocfilehash: b44e0a5d36a99f322c1b1455d753c324a6834d34
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2017
---
# <a name="ltunorderedsetgt-functions"></a>&lt;unordered_set&gt; 函数
|||  
|-|-|  
|[swap (set)](#swap)|[swap (unordered_multiset)](#swap_unordered_multiset)|  
  
##  <a name="swap"></a>  swap (unordered_set)  
 交换两个容器的内容。  
  
```  
 
template <class Key, class Hash, class Pred, class Alloc>  
void swap(
   unordered_set <Key, Hash, Pred, Alloc>& left,  
   unordered_set <Key, Hash, Pred, Alloc>& right);
```  
  
### <a name="parameters"></a>参数  
 `Key`  
 密钥类型。  
  
 `Hash`  
 哈希函数对象类型。  
  
 `Pred`  
 相等比较函数对象类型。  
  
 `Alloc`  
 allocator 类。  
  
 `left`  
 第一个要交换的容器。  
  
 `right`  
 第二个要交换的容器。  
  
### <a name="remarks"></a>备注  
 该模板函数执行 `left.`[unordered_set::swap](../standard-library/unordered-set-class.md#swap)`(right)`。  
  
### <a name="example"></a>示例  
  
```cpp  
#include <unordered_set>  
#include <iostream>  
  
typedef std::unordered_set<char> Myset;  
int main()  
{  
Myset c1;  
  
c1.insert('a');  
c1.insert('b');  
c1.insert('c');  
  
// display contents " [c] [b] [a]"  
for (Myset::const_iterator it = c1.begin();  
it != c1.end(); ++it)  
std::cout << " [" << *it << "]";  
std::cout << std::endl;  
  
Myset c2;  
  
c2.insert('d');  
c2.insert('e');  
c2.insert('f');  
  
c1.swap(c2);  
  
// display contents " [f] [e] [d]"  
for (Myset::const_iterator it = c1.begin();  
it != c1.end(); ++it)  
std::cout << " [" << *it << "]";  
std::cout << std::endl;  
  
swap(c1, c2);  
  
// display contents " [c] [b] [a]"  
for (Myset::const_iterator it = c1.begin();  
it != c1.end(); ++it)  
std::cout << " [" << *it << "]";  
std::cout << std::endl;  
  
return (0);  
}  
  
```  
  
```Output  
  
[c] [b] [a]  
[f] [e] [d]  
[c] [b] [a]  
  
```  
  
##  <a name="swap_unordered_multiset"></a>  swap (unordered_multiset) 
 交换两个容器的内容。  
  
```  
 
template <class Key, class Hash, class Pred, class Alloc>  
void swap(
   unordered_multiset <Key, Hash, Pred, Alloc>& left,  
   unordered_multiset <Key, Hash, Pred, Alloc>& right);
```  
  
### <a name="parameters"></a>参数  
 `Key`  
 密钥类型。  
  
 `Hash`  
 哈希函数对象类型。  
  
 `Pred`  
 相等比较函数对象类型。  
  
 `Alloc`  
 allocator 类。  
  
 `left`  
 第一个要交换的容器。  
  
 `right`  
 第二个要交换的容器。  
  
### <a name="remarks"></a>备注  
 该模板函数执行 `left.`[unordered_multiset::swap](../standard-library/unordered-multiset-class.md#swap)`(right)`。  
  
### <a name="example"></a>示例  
  
```cpp  
// std__unordered_set__u_ms_swap.cpp  
// compile with: /EHsc  
#include <unordered_set>  
#include <iostream>  
  
typedef std::unordered_multiset<char> Myset;
int main()
{
    Myset c1;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');

    // display contents " [c] [b] [a]"  
    for (Myset::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << " [" << *it << "]";
    std::cout << std::endl;

    Myset c2;

    c2.insert('d');
    c2.insert('e');
    c2.insert('f');

    c1.swap(c2);

    // display contents " [f] [e] [d]"  
    for (Myset::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << " [" << *it << "]";
    std::cout << std::endl;

    swap(c1, c2);

    // display contents " [c] [b] [a]"  
    for (Myset::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << " [" << *it << "]";
    std::cout << std::endl;

    return (0);
}
  
```  
  
```Output  
  
[c] [b] [a]  
[f] [e] [d]  
[c] [b] [a]  
  
```  
  
## <a name="see-also"></a>请参阅  
 [<unordered_set>](../standard-library/unordered-set.md)

