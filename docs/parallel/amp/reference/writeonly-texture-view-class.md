---
title: "writeonly_texture_view 类 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- writeonly_texture_view
- AMP_GRAPHICS/writeonly_texture_view
- AMP_GRAPHICS/Concurrency::graphics::writeonly_texture_view
- AMP_GRAPHICS/Concurrency::graphics::writeonly_texture_view::set
- AMP_GRAPHICS/Concurrency::graphics::rank Constant
dev_langs: C++
ms.assetid: 8d117ad3-0a1c-41ae-b29c-7c95fdd4d04d
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 594a23113159c7d4afa9e3119952b001f8ee7ed4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="writeonlytextureview-class"></a>writeonly_texture_view 类
提供对纹理的 writeonly 访问。  
  
## <a name="syntax"></a>语法  
  
```  
template <
    typename value_type,  
    int _Rank  
>  
class writeonly_texture_view;  
 
template <
    typename value_type,  
    int _Rank  
>  
class writeonly_texture_view<value_type, _Rank> : public details::_Texture_base<value_type, _Rank>;  
```  
  
#### <a name="parameters"></a>参数  
 `value_type`  
 纹理中的元素的类型。  
  
 `_Rank`  
 纹理的秩。  
  
## <a name="members"></a>成员  
  
### <a name="public-typedefs"></a>公共 Typedef  
  
|名称|描述|  
|----------|-----------------|  
|`scalar_type`||  
|`value_type`|纹理中的元素的类型。|  
  
### <a name="public-constructors"></a>公共构造函数  
  
|名称|描述|  
|----------|-----------------|  
|[writeonly_texture_view 构造函数](#ctor)|初始化 `writeonly_texture_view` 类的新实例。|  
|[~ writeonly_texture_view 析构函数](#ctor)|销毁`writeonly_texture_view`对象。|  
  
### <a name="public-methods"></a>公共方法  
  
|名称|描述|  
|----------|-----------------|  
|[set](#set)|设置指定索引处的元素的值。|  
  
### <a name="public-operators"></a>公共运算符  
  
|名称|描述|  
|----------|-----------------|  
|[operator=](#operator_eq)|将复制指定`writeonly_texture_view`于此对象。|  
  
### <a name="public-constants"></a>公共常量  
  
|name|描述|  
|----------|-----------------|  
|[rank 常量](#rank)|获取的秩`writeonly_texture_view`对象。|  
  
## <a name="inheritance-hierarchy"></a>继承层次结构  
 `_Texture_base`  
  
 `writeonly_texture_view`  
  
## <a name="requirements"></a>惠?  
 **标头：** amp_graphics.h  
  
 **Namespace:** concurrency:: graphics  
  
##  <a name="dtor"></a>~ writeonly_texture_view 

 销毁`writeonly_texture_view`对象。  
  
```  
~writeonly_texture_view() restrict(amp,cpu);
```  
  
##  <a name="operator_eq"></a>运算符 = 

 将复制指定`writeonly_texture_view`于此对象。  
  
```  
writeonly_texture_view<value_type, _Rank>& operator= (
    const writeonly_texture_view<value_type, _Rank>& _Other) restrict(amp,cpu);
```  
  
### <a name="parameters"></a>参数  
 `_Other`  
 `writeonly_texture_view`要从复制的对象。  
  
### <a name="return-value"></a>返回值  
 对此引用`writeonly_texture_view`对象。  
  
##  <a name="rank"></a>级别 

 获取的秩`writeonly_texture_view`对象。  
  
```  
static const int rank = _Rank;  
```  
  
##  <a name="set"></a>设置 

 设置指定索引处的元素的值。  
  
```  
void set(
    const index<_Rank>& _Index,  
    const value_type& value) const restrict(amp);
```  
  
### <a name="parameters"></a>参数  
 `_Index`  
 元素的索引。  
  
 `value`  
 该元素的新值。  
  
##  <a name="ctor"></a>writeonly_texture_view 

 初始化 `writeonly_texture_view` 类的新实例。  
  
```  
writeonly_texture_view(
    texture<value_type, 
    _Rank>& _Src) restrict(amp);

 
writeonly_texture_view(
    const writeonly_texture_view<value_type,  
    _Rank>& _Src) restrict(amp,cpu);
```  
  
### <a name="parameters"></a>参数  
 `_Rank`  
 纹理的秩。  
  
 `value_type`  
 纹理中的元素的类型。  
  
 `_Src`  
 用于创建 `writeonly_texture_view` 的纹理。  
  
## <a name="see-also"></a>请参阅  
 [Concurrency::graphics 命名空间](concurrency-graphics-namespace.md)
