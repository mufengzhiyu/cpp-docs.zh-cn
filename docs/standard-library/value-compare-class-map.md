---
title: "value_compare 类（&lt;映射&gt;）| Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- std::value_compare
- std.value_compare
- map/std::value_compare
- value_compare
dev_langs: C++
helpviewer_keywords: std::value_compare
ms.assetid: ea97c1d0-04b2-4d42-8d96-23522c04cc41
caps.latest.revision: "21"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1e05f4e0f4431ac9911f98c10540b7aa03a3f486
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="valuecompare-class-ltmapgt"></a>value_compare 类（&lt;映射&gt;）
提供一个函数对象，它能通过比较其键的值来比较映射的元素，以确定其在映射中的相对顺序。  
  
## <a name="syntax"></a>语法  
  
```
class value_compare : public binary_function<value_type, value_type, bool>
{
public:
    bool operator()(const value_type& left, const value_type& right) const;
    value_compare(key_compare pred) : comp(pred);
protected:
    key_compare comp;
};
```  
  
## <a name="remarks"></a>备注  
 辅助类构造包含的相应元素的键之间的比较将引发一种比较条件，这种比较条件由 map 包含的整个元素的 **value_types** 之间的 `value_compare` 提供。 成员函数运算符使用 `value_compare` 提供的函数对象中存储的 `key_compare` 类型的 **comp** 对象，用于比较两个元素的排序键组件。  
  
 对于 set 和 multiset（二者均为键值与元素值完全相同的简单容器），`value_compare` 等效于 `key_compare`；对于 map 和 multimap，它们则不相等，因为类型 `pair` 元素的值与元素的键值不完全相同。  
  
## <a name="example"></a>示例  
  有关如何声明和使用 `value_compare` 的示例，请参阅 [value_comp](../standard-library/map-class.md#value_comp) 的示例。  
  
## <a name="requirements"></a>惠?  
 **Header:** \<map>  
  
 **命名空间：** std  
  
## <a name="see-also"></a>请参阅  
 [binary_function 结构](../standard-library/binary-function-struct.md)   
 [C++ 标准库中的线程安全性](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [C++ 标准库参考](../standard-library/cpp-standard-library-reference.md)



