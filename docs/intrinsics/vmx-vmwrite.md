---
title: "__vmx_vmwrite |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: __vmx_vmwrite
dev_langs: C++
helpviewer_keywords:
- __vmx_vmwrite intrinsic
- VMWRITE instruction
ms.assetid: 88139792-fd3f-4210-97ca-9d84f43a0252
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 00bc9fe617144db7de3425c5732b3f655b30c790
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/03/2018
---
# <a name="vmxvmwrite"></a>__vmx_vmwrite
**Microsoft 专用**  
  
 将指定的值写入当前虚拟机控件结构 (VMCS) 中的指定字段。  
  
## <a name="syntax"></a>语法  
  
```  
unsigned char __vmx_vmwrite(   
   size_t Field,  
   size_t FieldValue  
);  
```  
  
#### <a name="parameters"></a>参数  
  
|参数|描述|  
|---------------|-----------------|  
|[in] `Field`|要写入的 VMCS 字段。|  
|[in] `FieldValue`|要写入的 VMCS 字段的值。|  
  
## <a name="return-value"></a>返回值  
 0  
 操作成功。  
  
 1  
 操作失败，当前 VMCS 的 `VM-instruction error field` 中提供了扩展状态。  
  
 2  
 操作失败，无可用状态。  
  
## <a name="remarks"></a>备注  
 `__vmx_vmwrite`函数等同于`VMWRITE`计算机指令。 值`Field`参数是 Intel 文档所述的编码的字段索引。 有关详细信息，搜索文档中，"Intel 虚拟化技术规范为 ia-32 Intel 体系结构，"在文档编号 C97063-002， [Intel Corporation](http://go.microsoft.com/fwlink/p/?linkid=127)站点，并请查阅的附录 C文档。  
  
## <a name="requirements"></a>惠?  
  
|内部函数|体系结构|  
|---------------|------------------|  
|`__vmx_vmwrite`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **标头文件** \<intrin.h >  
  
**结束 Microsoft 专用**  
  
## <a name="see-also"></a>请参阅  
 [编译器内部函数](../intrinsics/compiler-intrinsics.md)   
 [__vmx_vmread](../intrinsics/vmx-vmread.md)