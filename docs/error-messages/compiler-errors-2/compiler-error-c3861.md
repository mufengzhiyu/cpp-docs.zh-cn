---
title: "编译器错误 C3861 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3861
dev_langs: C++
helpviewer_keywords: C3861
ms.assetid: 0a1eee30-b3db-41b1-b1e5-35949c3924d7
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 82656822d408be4b2fc085abe8a007469c822a65
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3861"></a>编译器错误 C3861

> *标识符*： 找不到标识符  
  
即使使用自变量相关的查找，编译器也无法解析对标识符的引用。  
  
若要修复此错误，比较使用*标识符*到标识符声明的大小写和拼写。 验证[范围解析运算符](../../cpp/scope-resolution-operator.md)和命名空间[using 指令](../../cpp/namespaces-cpp.md#using_directives)的用法正确。 如果在标头文件中声明该标识符，请验证引用标识符之前已包含该头。 如果标识符旨在是外部可见的请确保它在使用它的任何源文件中声明。 此外请检查标识符声明或定义不排除通过[条件编译指令](../../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)。 

若要从 Visual Studio 2015 中的 C 运行时库中删除过时函数的更改可能会导致 C3861。 若要解决此错误，删除对这些函数的引用，或将它们替换为其安全的替代方法，如果有。 有关详细信息，请参阅[过时函数](../../c-runtime-library/obsolete-functions.md)。  

如果项目在迁移后显示从旧版本的编译器错误 C3861，则可能产生与支持的 Windows 版本相关的问题。 Visual C++ 不再支持面向 Windows 95、Windows 98、Windows ME、Windows NT 或 Windows 2000。 如果你 WINVER 或 _WIN32_WINNT 宏分配给 Windows 这些版本之一，则必须修改宏。 有关详细信息，请参阅[修改 WINVER 和 _WIN32_WINNT](../../porting/modifying-winver-and-win32-winnt.md)。
  
## <a name="example"></a>示例  

下面的示例生成 C3861，因为未定义标识符。  
  
```cpp  
// C3861.cpp  
void f2(){}  
int main() {  
   f();    // C3861  
   f2();   // OK  
}  
```  
  
## <a name="example"></a>示例  

下面的示例生成 C3861 因为标识符仅在其定义，文件作用域中可见，除非它在使用它的其他源文件中声明。  
  
```cpp  
// C3861_a1.cpp
// Compile with: cl /EHsc /W4 C3861_a1.cpp C3861_a2.cpp  
#include <iostream>
// Uncomment the following line to fix:
// int f();  // declaration makes external function visible
int main() {  
   std::cout << f() << std::endl;    // C3861
}  
```  
  
```cpp  
// C3861_a2.cpp  
int f() {  // declared and defined here
   return 42;  
}
```  
  
## <a name="example"></a>示例  

C + + 标准库中的异常类需要`std`命名空间。  
  
```cpp  
// C3861_b.cpp  
// compile with: /EHsc  
#include <iostream>  
int main() {  
   try {  
      throw exception("Exception");   // C3861  
      // try the following line instead  
      // throw std::exception("Exception");  
   }  
   catch (...) {  
      std::cout << "caught an exception" << std::endl;  
   }  
}  
```  
## <a name="example"></a>示例  

已从 CRT 库中删除过时函数。  
  
```cpp  
// C3861_c.cpp  
#include <stdio.h>  
int main() {  
   char line[21]; // room for 20 chars + '\0'  
   gets( line );  // C3861  
   // Use gets_s instead.  
   printf( "The line entered was: %s\n", line );  
}  
```
下面的示例生成 C3767，因为编译器不能用于 FriendFunc 依赖于自变量的查找：  
  
```  
namespace N {  
   class C {  
      friend void FriendFunc() {}  
      friend void AnotherFriendFunc(C* c) {}  
   };  
}  
  
int main() {  
   using namespace N;  
   FriendFunc();   // C3861 error  
   C* pC = new C();  
   AnotherFriendFunc(pC);   // found via argument-dependent lookup  
}  
```  
  
若要修复此错误，声明友元类作用域中的，并在命名空间范围中定义它：  
  

类 MyClass {  
   int m_private;  
   友元 void func();  
};  
  
void func() {  
   MyClass s;  
   s.m_private = 0;  
}  
  
int main （） {  
   func();  
}  