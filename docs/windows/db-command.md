---
title: "db_command |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.db_command
dev_langs: C++
helpviewer_keywords: db_command attribute
ms.assetid: 714c3e15-85d7-408b-9a7c-88505c3e5d24
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 87209d673da47827723198697a26300d4056d3d0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="dbcommand"></a>db_command
创建 OLE DB 命令。  
  
## <a name="syntax"></a>语法  
  
```  
  
      [ db_command(   
   command,   
   name,   
   source_name,   
   hresult,   
   bindings,   
   bulk_fetch)  
]  
```  
  
#### <a name="parameters"></a>参数  
 `command`  
 包含 OLE DB 命令文本的命令字符串。 一个简单的例子是：  
  
```  
[ db_command ( command = "Select * from Products" ) ]  
```  
  
  命令语法如下：  
  
```  
binding parameter block 1  
   OLE DB command  
binding parameter block 2  
   continuation of OLE DB command  
binding parameter block 3  
...  
```  
  
  绑定参数块的定义如下：  
  
 **([** `bindtype` **]** *szVar1* [*, szVar2* [, *nVar3* [, ...]]] **)**  
  
 其中：  
  
 **(** 标记数据绑定块的开始位置。  
  
 **[** `bindtype` **]** 是以下不区分大小写的字符串之一：  
  
-   **[db_column]** 将每个成员变量绑定到行集中的列。  
  
-   **[bindto]** （与 **[db_column]**相同）。  
  
-   **[in]** 将成员变量绑定为输入参数。  
  
-   **[out]** 将成员变量绑定为输出参数。  
  
-   **[in,out]** 将成员变量绑定为输入/输出参数。  
  
 *SzVarX* 解析为当前范围内的成员变量。  
  
 **)** 标记数据绑定块的结束位置。  
  
 如果命令字符串包含一个或多个说明符（例如 [in]、[out] 或 [in/out]）， **db_command** 会生成参数映射。  
  
 如果命令字符串中包含一个或多个参数（例如 [db_column] 或 [bindto]）， **db_command** 会生成行集和取值函数映射以服务这些绑定变量。 有关详细信息，请参阅 [db_accessor](../windows/db-accessor.md) 。  
  
> [!NOTE]
>  在类级别使用`bindtype`db_command `bindings` 时，[ **] 语法和** 参数无效。  
  
 下面是一些绑定参数块的示例。 下面的示例分别将 `m_au_fname` 和 `m_au_lname` 数据成员绑定到 pubs 数据库中作者表的 `au_fname` 和 `au_lname` 列：  
  
```  
TCHAR m_au_fname[21];  
TCHAR m_au_lname[41];  
TCHAR m_state[3] = 'CA';  
  
[db_command (  
   command = "SELECT au_fname([bindto]m_au_fname), au_lname([bindto]m_au_lname) " \  
   "FROM dbo.authors " \  
   "WHERE state = ?([in]m_state)")  
```  
  
 ]  
  
  名称（可选）  
 用于处理行集的句柄名称。 如果指定名称 ， **db_command** 会生成具有指定名称 的类，可以用它来遍历行集或执行多个操作查询。 如果未指定名称 ，则无法向用户返回多个行的结果。  
  
  source_name（可选）  
 将 `CSession` 特性应用到其（在其上运行命令）的类的 `db_source` 变量或实例。 请参阅 [db_source](../windows/db-source.md)。  
  
 执行**db_command** 检查，确认用于 *source_name* 的变量有效，使指定的变量位于函数或全局范围内。  
  
 `hresult` （可选）  
 标识将接收此数据库命令的 `HRESULT` 的变量。 如果该变量不存在，属性将自动插入。  
  
  绑定（可选）  
 允许从 OLE DB 命令分离绑定参数。  
  
 如果指定 `bindings`的值， **db_command** 将分析相关联的值，但不会分析 [`bindtype`] 参数。 这种用法允许使用 OLE DB 提供程序语法。 若要禁用分析，但不绑定参数，请指定 **Bindings=""**。  
  
 如果未指定 `bindings`的值， **db_command** 将分析绑定参数块，查找“**(**”，后面依次是方括号内的 **[**`bindtype`**]** 、一个或多个以前声明的 C++ 成员变量和“**)**”。 将从生成的命令中去除括号间的所有文本，并且这些参数将用于为此命令构造列和参数绑定。  
  
 *bulk_fetch*（可选）  
 指定要提取的行数的整数值。  
  
 默认值为 1，指定单行提取（行集将为 [CRowset](../data/oledb/crowset-class.md)类型）。  
  
 大于 1 的值指定批量取行。 批量取行指提取多个行句柄的批量行集功能（行集将为 [CBulkRowset](../data/oledb/cbulkrowset-class.md) 类型，并将采用指定的行数调用 `SetRows` ）。  
  
 如果 *bulk_fetch* 小于 1， `SetRows` 将返回零。  
  
## <a name="remarks"></a>备注  
 **db_command** 创建 [CCommand](../data/oledb/ccommand-class.md) 对象，OLE DB 使用者使用该对象来执行命令。  
  
 可以将 **db_command** 与类或函数范围一起使用，主要差异在于 `CCommand` 对象的范围。 使用函数范围，绑定等数据终止于函数末端。 类和函数范围用法涉及到 OLE DB 使用者模板类**CCommand <>**，但模板自变量的函数和类的用例的区别。 在函数事例中，将绑定包含本地变量的 **取值函数** ，而类用法将推断 `CAccessor`派生的类作为参数。 用作类属性时， **db_command** 和 **db_column**配合使用。  
  
 **db_command** 可用于执行不返回结果集的命令。  
  
 当使用者特性提供程序应用于类时此属性时，编译器将该类重命名为\_*类名*访问器，其中*类名*是你为指定的名称类，并且编译器还将创建一个名为类*类名*，它派生自\_*类名*访问器。  将在类视图中看到这两个类。  
  
## <a name="example"></a>示例  
 本示例定义一个命令，该命令从状态列与“CA”匹配的表格中选择第一个和最后一个名称。 **db_command** 创建并读取行集，在行集上可以调用向导生成的函数（例如 [OpenAll 和 CloseAll](../data/oledb/consumer-wizard-generated-methods.md)）和 `CRowset` 成员函数（例如 [MoveNext](../data/oledb/crowset-movenext.md)）。  
  
 请注意，此代码要求提供自己连接到 pubs 数据库的连接字符串。 有关如何在开发环境中执行此操作的信息，请参阅 [How to: Connect to a Database from Server Explorer](http://msdn.microsoft.com/en-us/7c1c3067-0d77-471b-872b-639f9f50db74) 和 [How to: Add New Data Connections in Server Explorer/Database Explorer](http://msdn.microsoft.com/en-us/fb2f513b-ddad-4142-911e-856bba0054c8)。  
  
```  
// db_command.h  
#include <atlbase.h>  
#include <atlplus.h>  
#include <atldbcli.h>  
  
#pragma once  
  
[  db_source(L"your connection string"),  
   db_command(L" \  
      SELECT au_lname, au_fname \  
      FROM dbo.authors \  
      WHERE state = 'CA'")  ]  
  
struct CAuthors {  
   // In order to fix several issues with some providers, the code below may bind  
   // columns in a different order than reported by the provider  
  
   DBSTATUS m_dwau_lnameStatus;  
   DBSTATUS m_dwau_fnameStatus;  
   DBLENGTH m_dwau_lnameLength;  
   DBLENGTH m_dwau_fnameLength;  
  
   [ db_column("au_lname", status="m_dwau_lnameStatus", length="m_dwau_lnameLength") ] TCHAR m_au_lname[41];  
   [ db_column("au_fname", status="m_dwau_fnameStatus", length="m_dwau_fnameLength") ] TCHAR m_au_fname[21];  
  
   [ db_param("7", paramtype="DBPARAMIO_INPUT") ] TCHAR m_state[3];  
  
   void GetRowsetProperties(CDBPropSet* pPropSet) {  
      pPropSet->AddProperty(DBPROP_CANFETCHBACKWARDS, true, DBPROPOPTIONS_OPTIONAL);  
      pPropSet->AddProperty(DBPROP_CANSCROLLBACKWARDS, true, DBPROPOPTIONS_OPTIONAL);  
   }  
};  
```  
  
## <a name="example"></a>示例  
  
```  
// db_command.cpp  
// compile with: /c  
#include "db_command.h"  
  
int main(int argc, _TCHAR* argv[]) {  
   HRESULT hr = CoInitialize(NULL);  
  
   // Instantiate rowset  
   CAuthors rs;  
  
   // Open rowset and move to first row  
   strcpy_s(rs.m_state, sizeof(rs.m_state), _T("CA"));  
   hr = rs.OpenAll();  
   hr = rs.MoveFirst();  
  
   // Iterate through the rowset  
   while( SUCCEEDED(hr) && hr != DB_S_ENDOFROWSET ) {  
      // Print out the column information for each row  
      printf("First Name: %s, Last Name: %s\n", rs.m_au_fname, rs.m_au_lname);  
      hr = rs.MoveNext();  
   }  
  
   rs.CloseAll();  
   CoUninitialize();  
}  
```  
  
## <a name="example"></a>示例  
 此示例使用数据源类 `db_source` 上的 `CMySource`以及命令类 `db_command` 和 `CCommand1` 上的 `CCommand2`。  
  
```  
// db_command_2.cpp  
// compile with: /c  
#include <atlbase.h>  
#include <atlplus.h>  
#include <atldbcli.h>  
// class usage for both db_source and db_command  
  
[  db_source(L"your connection string"),  
   db_command(L" \  
      SELECT au_lname, au_fname \  
      FROM dbo.authors \  
      WHERE state = 'CA'")  ]  
struct CMySource {  
   HRESULT OpenDataSource() {  
      return S_OK;  
   }  
};  
  
[db_command(command = "SELECT * FROM Products")]  
class CCommand1 {};  
  
[db_command(command = "SELECT FNAME, LNAME FROM Customers")]  
class CCommand2 {};  
  
int main() {  
   CMySource s;  
   HRESULT hr = s.OpenDataSource();  
   if (SUCCEEDED(hr)) {  
      CCommand1 c1;  
      hr = c1.Open(s);  
  
      CCommand2 c2;  
      hr = c2.Open(s);  
   }  
  
   s.CloseDataSource();  
}  
```  
  
## <a name="requirements"></a>惠?  
  
### <a name="attribute-context"></a>特性上下文  
  
|||  
|-|-|  
|**适用对象**|**类**、 `struct`、成员、方法、本地|  
|**可重复**|否|  
|**必需的特性**|无|  
|**无效的特性**|无|  
  
 有关特性上下文的详细信息，请参见 [特性上下文](../windows/attribute-contexts.md)。  
  
## <a name="see-also"></a>请参阅  
 [OLE DB 使用者特性](../windows/ole-db-consumer-attributes.md)   
 [独立特性](../windows/stand-alone-attributes.md)   
