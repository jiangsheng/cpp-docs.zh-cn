---
title: "格式规范语法：printf 和 wprintf 函数 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apilocation:
- msvcr90.dll
- msvcr110_clr0400.dll
- msvcr100.dll
- msvcr110.dll
- msvcr80.dll
- msvcr120.dll
apitype: DLLExport
f1_keywords:
- wprintf
dev_langs:
- C++
helpviewer_keywords:
- format specification fields for printf function
- print flag directives
- printf function, precision
- type fields, printf function
- precision fields
- printf function, format specification fields
- flag directives printf function
- type fields
ms.assetid: 664b1717-2760-4c61-bd9c-22eee618d825
caps.latest.revision: 15
author: corob-msft
ms.author: corob
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
translationtype: Human Translation
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: c57231375c662134fb1f9bd0252fd3b70f051ba2
ms.lasthandoff: 04/01/2017

---
# <a name="format-specification-syntax-printf-and-wprintf-functions"></a>格式规范语法：printf 和 wprintf 函数
各种 `printf` 函数采用格式字符串和可选参数，并生成用于输出的格式化的字符序列。 格式字符串包含零个或多个指令，这些指令是用于输出的文本字符或描述如何在输出中设置参数格式的已编码的转换规范。 本主题介绍用于对格式字符串中的转换规范进行编码的语法。 有关这些函数的列表，请参阅[流 I/O](../c-runtime-library/stream-i-o.md)。  
  
一个转换规范由以下形式的可选和必需字段组成：  
  
**%**[[*标志*](#flags)][[*宽度*](#width)][.[*精度*](#precision)][[*大小*](#size)][*类型*](#type)  
  
转换规范的每个字段都是一个用于指示特定的格式选项或转换说明符的字符或数字。 必填的类型字段指定要应用于参数的转换类型。 可选的标志、宽度和精度字段控制格式的其他方面（如前导空格或前导零、对齐方式和显示的精度）。 大小字段指定使用和转换的参数的大小。  
  
一个基本的转换规范仅包含百分号和一个类型字符。 例如，`%s` 指定一个字符串转换。 若要打印百分号字符，请使用 `%%`。 如果百分号后跟一个没有任何意义的字符作为格式字段，则将调用无效的参数处理程序。 有关详细信息，请参阅[参数验证](../c-runtime-library/parameter-validation.md)。  
  
> [!IMPORTANT]
>  为了实现安全性和稳定性，请确保转换规范字符串不是用户定义的。 例如，考虑这样一个程序，它提示用户输入名称并将输入存储在一个名为 `user_name` 的字符串变量中。 若要打印 `user_name`，请勿执行下列操作：  
>   
>  `printf( user_name ); /* Danger!  If user_name contains "%s", program will crash */`  
>   
>  而应执行以下操作：  
>   
>  `printf( "%s", user_name );`  
  
## <a name="type"></a>类型转换说明符
类型转换说明符字符指定是否要将相应的参数解释为字符、字符串、指针、整数或浮点数。 类型字符是唯一必填的转换规范字段，它出现在任何可选字段之后。  
  
将根据相应的类型字符和可选的[大小](#size)前缀对紧跟格式字符串的参数进行解释。 将通过使用 **c** 或 **C**指定字符类型 `char` 和 `wchar_t` 的转换，将通过使用 **s** 或 **S** 指定单字节和多字节或宽字符字符串，具体取决于正在使用的格式设置函数。 通过使用 **c** 和 **s** 指定的字符和字符串参数将被 `printf` 系列函数解释为 `char` 和 `char*`，或被 `wprintf` 系列函数解释为 `wchar_t` 和 `wchar_t*`。 通过使用 **C** 和 **S** 指定的字符和字符串参数将被 `printf` 系列函数解释为 `wchar_t` 和 `wchar_t*`，或被 `wprintf` 系列函数解释为 `char` 和 `char*`。 此行为是 Microsoft 专用的。  
  
将通过使用 **d**、**i**、**o**、**u**、**x** 和 **X** 指定整数类型（如 `short`、`int`、`long`、`long long`）及其 `unsigned` 变体。将通过使用 **a**、**A**、**e**、**E**、**f**、**F**、**g** 和 **G** 指定浮点类型（如 `float`、`double` 和 `long double`）。默认情况下，除非由大小前缀进行修改，否则整数参数将被强制为 `int` 类型，浮点参数将被强制为 `double`。 在 64 位系统上，`int` 是 32 位的值；因此，确定 64 位整数的输出格式时，将把它截断，除非使用 **ll** 或 **I64** 的大小前缀。 由 **p** 指定的指针类型使用平台的默认指针大小。  
  
> [!NOTE]
>  与 `printf` 和 `wprintf` 函数一起使用时，**Z** 类型字符以及 **c**、**C**、**s** 和 **S** 类型字符的行为是 Microsoft 扩展。 在所有的格式设置函数中，ISO C 标准始终对窄字符和字符串使用 **c** 和 **s**，而对宽字符和字符串使用 **C** 和 **S**。   
  
### <a name="type-field-characters"></a>类型字段字符  
  
|类型字符|参数|输出格式|  
|--------------------|--------------|-------------------|  
|**c**|字符|与 `printf` 函数一起使用时，指定单字节字符；与 `wprintf` 函数一起使用时，指定宽字符。|  
|**C**|字符|与 `printf` 函数一起使用时，指定宽字符；与 `wprintf` 函数一起使用时，指定单字节字符。|  
|**d**|整数|带符号十进制整数。|  
|**i**|整数|带符号十进制整数。|  
|**o**|整数|无符号八进制整数。|  
|**u**|整数|无符号十进制整数。|  
|**x**|整数|无符号十六进制整数；使用“abcdef.”|  
|**X**|整数|无符号十六进制整数；使用“ABCDEF.”|  
|**e**|浮点|有符号的值，形式为 [-]*d.dddd*__e±__*dd*[*d*]，其中 *d* 是一个十进制数，*dddd* 是一个或多个十进制数（具体取决于指定的精度），或为默认的六个数，*dd*[*d*] 是两个或三个十进制数（具体取决于[输出格式](../c-runtime-library/set-output-format.md)和指数大小）。|  
|**E**|浮点|与 **e** 格式相同，只不过指数由 **E** 引入，而不是由 **e** 引入。|  
|**f**|浮点|有符号的值，形式为 [-]*dddd*__.__*dddd*，其中 *dddd* 是一个或多个十进制数。 小数点前的数字位数取决于数字的度量值，小数点后的数字位数取决于请求的精度，或为默认的六位数。|  
|**F**|浮点|与 **f** 格式相同，只不过 infinity 和 nan 输出为大写形式。|  
|**g**|浮点|有符号的值将显示为 **f** 或 **e** 格式，取其中对于给定的值和精度更为精简一个。 仅当值的指数小于 -4 或大于等于 *precision* 参数时，才使用 **e** 格式。 截去尾随零，仅当后跟一个或多个数字时，才会显示小数点。|  
|**G**|浮点|与 **g** 格式相同，只不过指数由 **E** 引入，而不是由 **e** 引入（如果适用）。|  
|**a**|浮点|有符号的十六进制双精度浮点值，形式为 [-]0x*h.hhhh*__p±__*dd*，其中 *h.hhhh* 是尾数的十六进制数（使用小写字母），*dd* 是一位指数或多位指数。 精度指定此点后的数字位数。|  
|**A**|浮点|有符号的十六进制双精度浮点值，形式为 [-]0X*h.hhhh*__P±__*dd*，其中 *h.hhhh* 是尾数的十六进制数（使用大写字母），*dd* 是一位指数或多位指数。 精度指定此点后的数字位数。|  
|**n**|指向整数的指针|目前成功写入流或缓冲区的字符数。 此值存储在地址作为自变量的整数中。 可通过参数大小规范前缀控制指向的整数的大小。 **n** 说明符默认为禁用；请参阅重要的安全说明了解相关信息。|  
|**p**|指针类型|将自变量显示为十六进制数中的地址。|  
|**s**|字符串|与 `printf` 函数一起使用时，指定单字节或多字节字符串；与 `wprintf` 函数一起使用时，指定宽字符字符串。 将于第一个空字符之前或达到精度值时显示字符。|  
|**S**|字符串|与 `printf` 函数一起使用时，指定宽字符字符串；与 `wprintf` 函数一起使用时，指定单字节或多字节字符串。 将于第一个空字符之前或达到精度值时显示字符。|  
|**Z**|`ANSI_STRING` 或 `UNICODE_STRING` 结构|将 [ANSI_STRING](http://msdn.microsoft.com/library/windows/hardware/ff540605.aspx) 或 [UNICODE_STRING](http://msdn.microsoft.com/library/windows/hardware/ff564879.aspx) 结构的地址作为参数传递时，会显示包含在由结构的 `Buffer` 字段指向的缓冲区中的字符串。 使用 **w** 的大小修饰符前缀指定 `UNICODE_STRING` 参数，例如 `%wZ`。 结构的 `Length` 字段必须设置为字符串的长度（以字节为单位）。 结构的 `MaximumLength` 字段必须设置为缓冲区的长度（以字节为单位）。<br /><br /> 通常情况下，**Z** 类型字符仅在使用转换规范的驱动程序调试函数（如 `dbgPrint` 和 `kdPrint`）中使用。|  
  
从 Visual Studio 2015 开始，如果对应浮点转换说明符（**a**、**A**、**e**、**E**、**f**、**F**、**g**、**G**）的参数为无穷大、不定或 NaN，格式化的输出则符合 C99 标准。 下表列出了格式化的输出：  
  
|值|输出|  
|-----------|------------|  
|infinity|`inf`|  
|静默 NaN|`nan`|  
|信号 NaN|`nan(snan)`|  
|不定 NaN|`nan(ind)`|  
  
可能以符号作为其中任何一个值的前缀。 如果浮点类型转换说明符字符是一个大写字母，则输出也将使用大写字母格式。 例如，如果格式说明符是 `%F`而不是 `%f`，则 infinity 的格式将被设置为 `INF`，而不是 `inf`。 `scanf` 函数也可以分析这些字符串，使这些值可以通过 `printf` 和 `scanf` 函数进行往返。
  
在 Visual Studio 2015 之前，CRT 使用一种不同的非标准格式作为无穷大、不定和 NaN 值的输出：  
  
|值|输出|  
|-----------|------------|  
|+ 无穷|`1.#INF` 随机数字|  
|- 无穷|`-1.#INF` 随机数字|  
|不定（与静默 NaN 相同）|*数字* `.#IND` 随机数字|  
|NaN|*数字* `.#NAN` 随机数字|  
  
其中任何一种都可能已采用符号作为前缀并且格式设置也可能略有不同，具体取决于字段宽度和精度，有时会起到不寻常的作用。 例如，`printf("%.2f\n", INFINITY)` 可以打印 `1.#J`，因为 #INF 会“四舍五入”到 2 位数的精度。

> [!NOTE]
>  如果与 `%s` 或 `%S` 对应的参数，或与 `%Z` 对应的参数的 `Buffer` 字段为空指针，则将显示“(null)”。  
  
> [!NOTE]
>  在所有的指数格式中，要显示的指数的位数最少为两位，仅在必要时使用三位。 通过使用 [_set_output_format ](../c-runtime-library/set-output-format.md) 函数，可以将显示的数字位数设置为三位，以确保与为 Visual Studio 2013 及更早版本编写的代码的后向兼容性。  
  
> [!IMPORTANT]
>  `%n` 格式在本质上是不安全的，因此它默认处于禁用状态。 如果在格式字符串中遇到 `%n`，则将调用无效的参数处理程序，如[参数验证](../c-runtime-library/parameter-validation.md)中所述。 若要启用 `%n` 支持，请参阅 [_set_printf_count_output](../c-runtime-library/reference/set-printf-count-output.md)。  
  
## <a name="flags"></a>标志指令
转换规范中的第一个可选字段包含标志指令、零个或多个标志字符，用于指定输出对齐方式以及控制符号、空白、前导零、小数点以及八进制和十六进制前缀的输出。 转换规范中可能会出现多个标志指令，并且标志字符可能会按任意顺序出现。  
  
### <a name="flag-characters"></a>标志字符  
  
|Flag|含义|默认|  
|----------|-------------|-------------|  
|**-**|在给定的字段宽度内左对齐结果。|右对齐。|  
|**+**|如果输出值为有符号的类型，则在该值前使用符号（+ 或 -）作为前缀。|只对有符号的负值 (-) 显示符号。|  
|**0**|如果将 **0** 作为宽度的前缀，则会在达到最小宽度前添加前导零。 如果 **0** 和 **-** 同时出现，**0** 则将被忽略。 如果为整数格式（**i**、**u**、**x**、**X**、**o**、**d**）指定了 **0**，并且还存在精度规范（例如 `%04.d`），**0** 则将被忽略。 如果为 **a** 或 **A** 浮点格式指定了 **0**，则会在 `0x` 或 `0X` 前缀后，在尾数前追加前导零。|不填充。|  
|**空白** (' ')|如果输出值为有符号的正值，则使用空白作为其前缀。 如果空白和 + 标志同时出现，空白则将被忽略。|没有显示空白。|  
|**#**|与 **o**、**x** 或 **X** 格式一起使用时，**#** 标志将分别使用 0、0x 或 0X 作为任何非零输出值的前缀。|没有显示空白。|  
||与**e**、**E**、**f**、**F**、**a** 或 **A** 格式一起使用时，**#** 标志将强制输出值包含小数点。|仅当小数点后紧跟数字时，才会显示小数点。|  
||与 **g** 或 **G** 格式一起使用时，**#** 标志将强制输出值包含小数点，并阻止截断尾随零。<br /><br /> 与 **c**、**d**、**i**、**u** 或 **s** 一起使用时，则将被忽略。|仅当小数点后紧跟数字时，才会显示小数点。 尾随零将被截断。|  
  
## <a name="width"></a>宽度规范
在转换规范中，可选宽度规范字段出现在任何标志字符之后。 宽度参数是控制输出的最小字符数量的非负十进制整数。 如果输出值中的字符数小于指定宽度，则将在值的左侧或右侧添加空白（具体取决于是否指定了左对齐标志 (**-**)），直到达到最小宽度为止。 如果 0 作为宽度的前缀，则将向整数或浮点转换添加前导零，直到达到最小宽度为止，但转换到 infinity 或 NaN 时除外。  
  
 宽度规范永远不会导致值被截断。 如果输出值中的字符数大于指定宽度，或如果未提供宽度，则将根据精度规范输出值中的所有字符。  
  
 如果宽度规范是一个星号 (`*`)，则参数列表中的 `int` 参数将提供此值。 宽度参数必须先于在参数列表中要设置其格式的值，如以下示例中所示：  
  
 `printf("%0*f", 5, 3);  /* 00003 is output */`  
  
 转换规范中缺少宽度值或此值较小将不会导致截断输出值。 如果转换结果的宽度大于宽度值，则字段将扩展以包含转换结果。  
  
## <a name="precision"></a>精度规范
在转换规范中，第三个可选字段是精度规范。 它包含一个句点 (.)，后跟一个非负十进制整数，指定字符串字符数、小数位数或要输出的有效数字位数，具体取决于转换类型.  
  
 与宽度规范不同的是，精度规范可能导致输出值截断或浮点值舍入。 如果将精度指定为 0 并且要转换的值为 0，则结果为无字符输出，如以下示例中所示：  
  
 `printf( "%.0d", 0 );      /* No characters output */`  
  
 如果精度规范是一个星号 (\*)，则参数列表中的某个 `int` 参数将提供此值。 在参数列表中，精度参数前必须先于要设置其格式的值，如以下示例中所示：  
  
 `printf( "%.*f", 3, 3.14159265 );  /* 3.142 output */`  
  
 如果省略精度，则类型字符将决定精度的解释或默认精度，如下表中所示。  
  
### <a name="how-precision-values-affect-type"></a>精度值如何影响类型  
  
|类型|含义|默认|  
|----------|-------------|-------------|  
|**a**、**A**|精度指定此点后的数字位数。|默认精度为 13。 如果精度为 0，除非使用了 **#** 标志，否则不会打印小数点。|  
|**c**、**C**|精度不产生任何影响。|打印字符。|  
|**d**、**i**、**o**、**u**、**x**、**X**|精度指定要打印的最小数字位数。 如果参数中的数字位数小于精度，则将在输出值的左侧使用零进行填充。 数字位数超过精度时，值将不会被截断。|默认精度为 1。|  
|**e**、**E**|精度指定此小数点后要打印的数字位数。 打印的最后一位数舍入。|默认精度为 6。 如果精度为 0，或者如果句点 (.) 后面不跟数字，则不会打印小数点。|  
|**f**、**F**|精度值指定此小数点后的数字位数。 如果出现小数点，则在它之前至少会显示一个数字。 该值舍入为适当数量的数字。|默认精度为 6。 如果精度为 0，或者如果句点 (.) 后面不跟数字，则不会打印小数点。|  
|**g**、**G**|精度指定打印的最大有效位数。|打印六个有效位数，并且任何尾随零都会被截断。|  
|**s**、**S**|精度指定要打印的最大字符数。 不会打印超过精度的字符。|在遇到 null 字符之前不会打印字符。|  
  
## <a name="size"></a>参数大小规范
在转换规范中，大小字段是类型转换说明符的参数长度修饰符。 大小字段作为类型字段（**hh**、**h**、**j**、**l**（小写的 L）、**L**、**ll**、**t**、**w**、**z**、**I**（大写的 i）、**I32** 和 **I64**）的前缀，根据它们修饰的转换说明符，指定对应参数的“大小”（长型或短型、32 位或 64 位、单字节字符或宽字符）。 这些大小前缀在 `printf` 和 `wprintf` 系列函数中与 *类型* 字符一起使用，以指定参数大小的解释（如下表中所示）。 大小字段对于某些参数类型是可选的。 未指定任何大小前缀时，格式化程序使用整数参数（例如，有符号或无符号的 `char`、`short`、`int`、`long` 和枚举类型）作为 32 位 `int` 类型，而使用 `float`、`double` 和 `long double` 浮点参数作为 64 位 `double` 类型。 这与变量自变量列表的默认自变量提升规则相匹配。 有关自变量提升的详细信息，请参阅[后缀表达式](../cpp/postfix-expressions.md)中的“省略号和默认自变量”。 在 32 位和 64 位系统上，64 位整数参数的转换规范必须包含 **ll** 或 **I64** 大小前缀。 否则，格式化程序的行为是不明确的。  
  
某些类型在 32 位和 64 位代码中具有不同大小。 例如，`size_t` 在针对 x86 编译的代码中是 32 位长，而在针对 x64 编译的代码中是 64 位。 若要为宽度可变的类型创建与平台无关的格式设置代码，可以使用宽度可变的参数大小修饰符。 或者，使用 64 位参数大小修饰符，并将宽度可变的参数类型显式提升为 64 位。 特定于 Microsoft 的 **I**（大写的 i）参数大小修饰符可处理宽度可变的整数参数，但我们建议使用特定于类型的 **j**、**t** 和 **z** 修饰符以确保可移植性。  
  
### <a name="size-prefixes-for-printf-and-wprintf-format-type-specifiers"></a>printf 和 wprintf 格式类型说明符的大小前缀  
  
|若要指定|使用前缀|及类型说明符|  
|----------------|----------------|-------------------------|  
|`char`<br />`unsigned char`|**hh**|**d**、**i**、**o**、**u**、**x** 或 **X**|  
|`short int`<br />`short unsigned int`|**h**|**d**、**i**、**o**、**u**、**x** 或 **X**|  
|`__int32`<br />`unsigned __int32`|**I32**|**d**、**i**、**o**、**u**、**x** 或 **X**|  
|`__int64`<br />`unsigned __int64`|**I64**|**d**、**i**、**o**、**u**、**x** 或 **X**|  
|`intmax_t`<br />`uintmax_t`|**j** 或 **I**（大写的 i）|**d**、**i**、**o**、**u**、**x** 或 **X**|  
|`long double`|**l**（小写的 L）或 **L**|**a**、**A**、**e**、**E**、**f**、**F**、**g** 或 **G**|  
|`long int`<br />`long unsigned int`|**l**（小写的 L）|**d**、**i**、**o**、**u**、**x** 或 **X**|  
|`long long int`<br />`unsigned long long int`|**ll**（小写的 LL）|**d**、**i**、**o**、**u**、**x** 或 **X**|  
|`ptrdiff_t`|**t** 或 **I**（大写的 i）|**d**、**i**、**o**、**u**、**x** 或 **X**|  
|`size_t`|**z** 或 **I**（大写的 i）|**d**、**i**、**o**、**u**、**x** 或 **X**|  
|单字节字符|**h**|**c** 或 **C**|  
|宽字符|**l**（小写的 L）或 **w**|**c** 或 **C**|  
|单字节字符串|**h**|**s**、**S** 或 **Z**|  
|宽字符字符串|**l**（小写的 L）或 **w**|**s**、**S** 或 **Z**|  
  
`intmax_t`、`uintmax_t`、`ptrdiff_t` 和 `size_t` 类型在 32 位平台上为 `__int32` 或 `unsigned __int32`，在 64 位平台上为 `__int64` 或 `unsigned __int64`。 **I**（大写的 i）、**j**、**t** 和 **z** 大小前缀采用平台的正确参数宽度。  
  
在 Visual C++ 中，虽然 `long double` 是互异的类型，但是它具有与 `double` 相同的内部表示形式。  
  
**hc** 或 **hC** 类型说明符与 `printf` 函数中的 **c** 以及 `wprintf` 函数中的 **C** 是同义的。 **lc**、**lC**、**wc** 或 **wC** 类型说明符与 `printf` 函数中的 **C** 以及 `wprintf` 函数中的 **c** 是同义的。 **hs** 或 **hS** 类型说明符与 `printf` 函数中的 **s** 以及 `wprintf` 函数中的 **S** 是同义的。 **ls**、**lS**、**ws** 或 **wS** 类型说明符与 `printf` 函数中的 **S** 以及 `wprintf` 函数中的 **s** 是同义的。  
  
> [!NOTE]
>  **I**（大写的 i）、**I32**、**I64** 和 **w** 参数大小修饰符前缀是 Microsoft 扩展，且不符合 ISO C。 **h** 前缀（在与 `char` 类型的数据一起使用时）和 **l** 前缀（在与 `double` 类型的数据一起使用时）是 Microsoft 扩展。  
  

## <a name="see-also"></a>另请参阅  
 [printf、_printf_l、wprintf、_wprintf_l](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [printf_s、_printf_s_l、wprintf_s、_wprintf_s_l](../c-runtime-library/reference/printf-s-printf-s-l-wprintf-s-wprintf-s-l.md)   
 [printf_p 位置参数](../c-runtime-library/printf-p-positional-parameters.md)   
