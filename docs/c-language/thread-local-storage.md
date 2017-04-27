---
title: "线程本地存储 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "存储, 线程本地存储"
  - "线程存储类特性"
  - "线程本地存储区"
  - "线程局部变量"
  - "TLS（线程本地存储）"
ms.assetid: a0f1b109-c953-4079-aa10-e47f5483173d
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# 线程本地存储
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 专用**  
  
 线程本地存储 \(TLS\) 是给定的多线程进程中的每个线程为线程特定的数据分配存储时所采用的机制。  在标准多线程程序中，数据在给定进程的所有线程间共享，而线程本地存储是用于分配每个线程数据的机制。  有关线程的完整讨论，请参阅 [!INCLUDE[winsdkshort](../atl/reference/includes/winsdkshort_md.md)] 中的[进程和线程](http://msdn.microsoft.com/library/windows/desktop/ms684841)。  
  
 Microsoft C 语言包括扩展的存储类特性 thread，可将它与 \_\_declspec 关键字一起使用来声明线程局部变量。  例如，以下代码声明了一个整数线程局部变量，并用一个值对其进行初始化：  
  
```  
__declspec( thread ) int tls_i = 1;  
```  
  
 在声明静态绑定线程局部变量时，必须遵守这些准则：  
  
-   **\_\_declspec\(thread\)** 的使用可能会影响 DLL 导入的[延迟加载](../build/reference/linker-support-for-delay-loaded-dlls.md)**。**  
  
-   您只能将 thread 特性应用于数据声明和定义。  它不能用于函数声明或定义。  例如，下面的代码生成一个编译器错误：  
  
    ```  
    #define Thread   __declspec( thread )  
    Thread void func();      /* Error */  
    ```  
  
-   只能在具有静态存储持续时间的数据项上指定 thread 特性。  这包括全局数据（静态的和外部的）和本地静态数据。  不能使用 thread 特性声明自动数据。  例如，下面的代码将生成编译器错误：  
  
    ```  
    #define Thread   __declspec( thread )  
    void func1()  
    {  
        Thread int tls_i;            /* Error */  
    }  
  
    int func2( Thread int tls_i )    /* Error */  
    {  
       return tls_i;  
    }  
    ```  
  
-   必须将 thread 特性用于线程本地数据的声明和定义，无论声明和定义是出现在同一文件中还是单独的文件中。  例如，下面的代码将生成错误：  
  
    ```  
    #define Thread   __declspec( thread )  
    extern int tls_i;     /* This generates an error, because the   */  
    int Thread tls_i;     /* declaration and the definition differ. */  
    ```  
  
-   无法将 thread 特性用作类型修饰符。  例如，下面的代码生成一个编译器错误：  
  
    ```  
    char *ch __declspec( thread );      /* Error */  
    ```  
  
-   不将线程局部变量的地址视为常数，并且涉及此类地址的任何表达式不会被视为常量表达式。  这意味着，无法将线程局部变量的地址用作指针的初始值设定项。  例如，编译器会将下面的代码标记为错误：  
  
    ```  
    #define Thread   __declspec( thread )  
    Thread int tls_i;  
    int *p = &tls_i;      /* Error */  
    ```  
  
-   C 允许使用涉及对自身的引用的表达式来初始化变量，但只适用于非静态范围的对象。  例如:  
  
    ```  
    #define Thread   __declspec( thread )  
    Thread int tls_i = tls_i;             /* Error */  
    int j = j;                            /* Error */  
    Thread int tls_i = sizeof( tls_i )    /* Okay  */  
    ```  
  
     请注意，包含正在初始化的变量的 sizeof 表达式不构成对自身的引用，并且允许使用该表达式。  
  
-   **\_\_declspec\(thread\)** 的使用可能会影响 DLL 导入的[延迟加载](../build/reference/linker-support-for-delay-loaded-dlls.md)**。**  
  
 有关使用 thread 特性的详细信息，请参阅[多线程主题](../parallel/multithreading-support-for-older-code-visual-cpp.md)。  
  
 **结束 Microsoft 专用**  
  
## 请参阅  
 [C 扩展的存储类特性](../c-language/c-extended-storage-class-attributes.md)