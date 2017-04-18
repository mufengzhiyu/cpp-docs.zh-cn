---
title: "CA2CAEX 类 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CA2CAEX
- ATLCONV/ATL::CA2CAEX
- ATLCONV/ATL::CA2CAEX::CA2CAEX
- ATLCONV/ATL::CA2CAEX::m_psz
dev_langs:
- C++
helpviewer_keywords:
- CA2CAEX class
ms.assetid: 388e7c1d-a144-474c-a182-b15f69a74bd8
caps.latest.revision: 20
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
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
ms.sourcegitcommit: d2d39abf526a58b8442107b5ee816f316ae841f5
ms.openlocfilehash: 9185bc18981898d699aa3f3eeb490c76bf5138fb
ms.lasthandoff: 03/31/2017

---
# <a name="ca2caex-class"></a>CA2CAEX 类
此类由字符串转换宏`CA2CTEX`和`CT2CAEX`，和 typedef **CA2CA**。  
  
> [!IMPORTANT]
>  此类及其成员无法在 Windows 运行时中执行的应用中使用。  
  
## <a name="syntax"></a>语法  
  
```
template<int t_nBufferLength = 128>  
class CA2CAEX
```  
  
#### <a name="parameters"></a>参数  
 `t_nBufferLength`  
 在转换过程中使用的缓冲区大小。 默认长度为 128 个字节。  
  
## <a name="members"></a>成员  
  
### <a name="public-constructors"></a>公共构造函数  
  
|名称|描述|  
|----------|-----------------|  
|[CA2CAEX::CA2CAEX](#ca2caex)|构造函数。|  
|[CA2CAEX:: ~ CA2CAEX](#dtor)|析构函数。|  
  
### <a name="public-operators"></a>公共运算符  
  
|名称|说明|  
|----------|-----------------|  
|[CA2CAEX::operator LPCSTR](#operator_lpcstr)|转换运算符。|  
  
### <a name="public-data-members"></a>公共数据成员  
  
|名称|描述|  
|----------|-----------------|  
|[CA2CAEX::m_psz](#m_psz)|将源字符串存储数据成员。|  
  
## <a name="remarks"></a>备注  
 除非需要额外功能，则使用`CA2CTEX`， `CT2CAEX`，或**CA2CA**你自己的代码中。  
  
 此类可以安全地在循环中使用和不会溢出堆栈。 默认情况下，ATL 转换类和宏将使用用于转换的当前线程的 ANSI 代码页。  
  
 在此类基于以下宏︰  
  
- `CA2CTEX`  
  
- `CT2CAEX`  
  
 以下 typedef 基于此类︰  
  
- **CA2CA**  
  
 这些文本转换宏的讨论，请参阅[ATL 和 MFC 字符串转换宏](string-conversion-macros.md)。  
  
## <a name="example"></a>示例  
 请参阅[ATL 和 MFC 字符串转换宏](string-conversion-macros.md)有关使用这些字符串转换宏的示例。  
  
## <a name="requirements"></a>要求  
 **标头︰** atlconv.h  
  
##  <a name="ca2caex"></a>CA2CAEX::CA2CAEX  
 构造函数。  
  
```
CA2CAEX(LPCSTR psz, UINT nCodePage) throw(...);
CA2CAEX(LPCSTR psz) throw(...);
```  
  
### <a name="parameters"></a>参数  
 `psz`  
 要转换的文本字符串。  
  
 `nCodePage`  
 在此类中未使用。  
  
### <a name="remarks"></a>备注  
 创建转换所需的缓冲区。  
  
##  <a name="dtor"></a>CA2CAEX:: ~ CA2CAEX  
 析构函数。  
  
```
~CA2CAEX() throw();
```  
  
### <a name="remarks"></a>备注  
 释放已分配的缓冲区。  
  
##  <a name="m_psz"></a>CA2CAEX::m_psz  
 将源字符串存储数据成员。  
  
```
LPCSTR m_psz;
```  
  
##  <a name="operator_lpcstr"></a>CA2CAEX::operator LPCSTR  
 转换运算符。  
  
```  
operator LPCSTR() const throw();
```  
  
### <a name="return-value"></a>返回值  
 返回文本字符串作为类型`LPCSTR`。  
  
## <a name="see-also"></a>另请参阅  
 [CA2AEX 类](../../atl/reference/ca2aex-class.md)   
 [CA2WEX 类](../../atl/reference/ca2wex-class.md)   
 [CW2AEX 类](../../atl/reference/cw2aex-class.md)   
 [CW2CWEX 类](../../atl/reference/cw2cwex-class.md)   
 [CW2WEX 类](../../atl/reference/cw2wex-class.md)   
 [类概述](../../atl/atl-class-overview.md)
