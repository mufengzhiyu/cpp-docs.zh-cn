---
title: "__addfsbyte、 __addfsword、 __addfsdword |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- __addfsbyte_cpp
- __addfsdword
- __addfsword_cpp
- __addfsbyte
- __addfsword
- __addfsdword_cpp
dev_langs: C++
helpviewer_keywords:
- __addfsdword intrinsic
- __addfsword intrinsic
- __addfsbyte intrinsic
ms.assetid: 706c70df-6b52-4401-9268-2977ed8ad715
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ac2285eb0a140a942a42c7543d458172bcf890f7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="addfsbyte-addfsword-addfsdword"></a>__addfsbyte, __addfsword, __addfsdword
**Microsoft 专用**  
  
 将值添加到指定的偏移量相对于开始的内存位置`FS`段。  
  
## <a name="syntax"></a>语法  
  
```  
void __addfsbyte(   
   unsigned long Offset,   
   unsigned char Data   
);  
void __addfsword(   
   unsigned long Offset,   
   unsigned short Data   
);  
void __addfsdword(   
   unsigned long Offset,   
   unsigned long Data   
);  
```  
  
#### <a name="parameters"></a>参数  
 [in] `Offset`  
 从开始处的偏移量`FS`。  
  
 [in] `Data`  
 要添加到的内存位置的值。  
  
## <a name="requirements"></a>惠?  
  
|内部函数|体系结构|  
|---------------|------------------|  
|`__addfsbyte`|x86|  
|`__addfsword`|x86|  
|`__addfsdword`|x86|  
  
## <a name="remarks"></a>备注  
 这些例程只能用作内部函数不可用。  
  
**结束 Microsoft 专用**  
  
## <a name="see-also"></a>请参阅  
 [__incfsbyte、 \__incfsword， \__incfsdword](../intrinsics/incfsbyte-incfsword-incfsdword.md)   
 [__readfsbyte， \__readfsdword， \__readfsqword， \__readfsword](../intrinsics/readfsbyte-readfsdword-readfsqword-readfsword.md)   
 [__writefsbyte， \__writefsdword， \__writefsqword， \__writefsword](../intrinsics/writefsbyte-writefsdword-writefsqword-writefsword.md)   
 [编译器内部函数](../intrinsics/compiler-intrinsics.md)