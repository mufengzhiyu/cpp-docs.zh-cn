---
title: "is_object 类 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- is_object
- std::is_object
- type_traits/std::is_object
dev_langs:
- C++
helpviewer_keywords:
- is_object class
- is_object
ms.assetid: b452ceea-5676-488f-925b-ab881126c387
caps.latest.revision: 19
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 51fbd09793071631985720550007dddbe16f598f
ms.openlocfilehash: 7c82d8c19dbc87e53c2681c0a4b924f4b265ef1d
ms.lasthandoff: 02/24/2017

---
# <a name="isobject-class"></a>is_object 类
测试类型是否为对象类型。  
  
## <a name="syntax"></a>语法  
  
```  
template <class Ty>  
struct is_object;  
```  
  
#### <a name="parameters"></a>参数  
 `Ty`  
 要查询的类型。  
  
## <a name="remarks"></a>备注  
 如果类型 `Ty` 为引用类型、函数类型或 void、或其中之一的 `cv-qualified` 形式，则类型谓词的实例为 true，否则为 false。  
  
## <a name="example"></a>示例  
  
```cpp  
// std__type_traits__is_object.cpp   
// compile with: /EHsc   
#include <type_traits>   
#include <iostream>   
  
struct trivial   
    {   
    int val;   
    };   
  
struct functional   
    {   
    int f();   
    };   
  
int main()   
    {   
    std::cout << "is_object<trivial> == " << std::boolalpha   
        << std::is_object<trivial>::value << std::endl;   
    std::cout << "is_object<functional> == " << std::boolalpha   
        << std::is_object<functional>::value << std::endl;   
    std::cout << "is_object<trivial&> == " << std::boolalpha   
        << std::is_object<trivial&>::value << std::endl;   
    std::cout << "is_object<float()> == " << std::boolalpha   
        << std::is_object<float()>::value << std::endl;   
    std::cout << "is_object<void> == " << std::boolalpha   
        << std::is_object<void>::value << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
is_object<trivial> == true  
is_object<functional> == true  
is_object<trivial&> == false  
is_object<float()> == false  
is_object<void> == false  
```  
  
## <a name="requirements"></a>要求  
 **标头：**\<type_traits>  
  
 **命名空间：** std  
  
## <a name="see-also"></a>另请参阅  
 [<type_traits>](../standard-library/type-traits.md)   
 [is_function 类](../standard-library/is-function-class.md)
